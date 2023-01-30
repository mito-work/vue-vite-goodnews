# Vite Good News App

Vue+Vite で作るテキスト投稿アプリ

## Step1

・[ファイルで作成する]
(./goodnews-step1)

### 実装する機能

#### 入力フォームについて

![画像](./assets/img/step1/step1-1.png)

・デフォルトで 2 件表示されるようにする
・文字が入力されていないとボタンが非活性

![画像](./assets/img/step1/step1-2.png)

・テキストエリアに文字を入力できる
・文字を入力後「Post」を押すとリストに入力内容が反映される

![画像](./assets/img/step1/step1-3.png)

・入力文字数が 20 文字以内の場合は「20 文字以内でお願いします！」とエラーメッセージがでる

![画像](./assets/img/step1/step1-4.png)

・リストの値を削除することができる

![画像](./assets/img/step1/step1-5.png)

・すべて削除すると「投稿を待ちしています～」というメッセージが表示される

#### リスト表示について

・「Delete」を押すとリストからデータが削除される
・リストのデータがなくなった場合「投稿お待ちしています」というテキストが表示される

## Step2

・[コンポーネント単位に分ける]
(./goodnews-step2)

## Step3

・[DB に値を保存する]
(./goodnews-step3)

## step4

・[投稿に対して投票する]
(./goodnews-step4)

## step5

・[投稿を並び替える]
(./goodnews-step5)
