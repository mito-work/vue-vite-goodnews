<script setup lang="ts">
import { isTemplateNode } from "@vue/compiler-core";
import { ref, computed } from "vue";
const newsList = ref([
  {
    id: 0,
    description: "新しい靴を買ったこと",
  },
  {
    id: 1,
    description: "好きなアニメの続編が公開された",
  },
]);
const disabled = ref<boolean>(true);

const limitInputCheck = computed(() => {
  if (inputDescriotion.value.length >= 30 || inputDescriotion.value.length <= 0) {
    disabled.value = true;
  } else {
    disabled.value = false;
  }
  return inputDescriotion.value.length >= 20 ? "20文字以内でお願いします😮" : "";
});
const inputDescriotion = ref<string>("");

const input = () => {
  const news = { id: Date.now(), description: inputDescriotion.value };
  newsList.value.push(news);
  inputDescriotion.value = "";
};
const deleteItem = (id: number) => {
  newsList.value = newsList.value.filter((value) => {
    return value.id != id;
  });
};
</script>

<template>
  <div>
    <h1>🎉Post Good News of the week🎉</h1>
    <div class="l-container">
      <div class="l-container__form">
        <label for="post">今週のうれしかったこと、楽しかったことを共有してください</label>
        <input type="text" id="post" v-model="inputDescriotion" />
        <p v-if="limitInputCheck.length > 0" class="p-alert">{{ limitInputCheck }}</p>
        <button type="button" class="p-btn-post" @click="input" :disabled="disabled">Post</button>
      </div>
      <div class="l-container__list">
        <p v-if="newsList.length <= 0">投稿お待ちしています～😉</p>
        <ul class="p-list">
          <li v-for="item in newsList" :ley="item.id">
            <p>{{ item.description }}</p>

            <button type="button" class="p-btn-delete" @click="deleteItem(item.id)">Delete</button>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<style scoped>
input[type="text"] {
  padding: 0.5rem;
  font-size: 1.5rem;
  width: 500px;
}
.l-container__form {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 1rem;
}
.p-btn-post {
  background-color: #f70a8d;
  color: #fff;
}
.p-btn-delete {
  padding: 0 2rem;
  background-color: rgb(128, 194, 233);
  color: #fff;
}
.p-list {
  list-style: none;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-between;
  gap: 0.5rem;
}
.p-list li {
  padding: 1rem 0.5rem;
  background-color: rgb(203, 240, 252);
  font-weight: bold;
  width: 500px;
  display: flex;
  justify-content: space-between;
}
.p-alert {
  color: #f70a8d;
  font-weight: bold;
}
</style>
