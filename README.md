# ハッカソン

## 依存関係
- フロントエンド
  - HTML
  - CSS
  - Bootstrap
  - Javascript
    - jQuery
- バックエンド
  - XAMPP
  - firebase

## 画面構成
![ScreenTransitionDiagram.png](img/ScreenTransitionDiagram.png)
- ログインページ<br>
アカウント名を入力するとサイトにアクセスすることが出来ます。
- メインページ<br>
過去に多くの絵師が投稿したイラストがリストアップすることがされます。<br>
画像のクリックをすることで拡大したのち投げ銭を行うことができます。<br>
また、ここからイラストのマイページ及び評価ページへの遷移が行えます。<br>
- マイページ<br>
ここでは自分が過去に投稿した画像を確認することができます。<br>
画像には画像の画像に対する状態が「合格」「申請待ち」「不合格」の3つから与えられます。<br>
この評価が「合格」の場合のみメイン画面に表示される画像としてPOST可能です。<br>
このページの遷移先にPOSTのページがあります。
- 投稿ページ<br>
ここでは画像を審査対象として投稿することが出来ます。<br>
ここから投稿された画像はマイページの投稿済み画像として登録され、「審査待ち」のstateが与えられます。<br>
そして、この投稿後、画像は評価ページにて審査されます。
- 評価ページ<br>
ここで審査待ちのイラストを評価することが出来ます。<br>
ここで言って以上の評価を受けるとそのい内容が作成者のマイページに反映されます。<br>

## 要件定義
### ログインページ<br>
トリッピーさんの実装をほぼそのまま適用
### メインページ<br>
マイページ及び、評価ページへの遷移方法の実装。<br>
(ハンバーガーかスピードダイアルのいずれかで実装)<br>
任意の数の画像を表示。それらの画像をサーバー側から取得することを理想とする。<br>
### マイページ<br>
ここに過去の投稿した画像の名前のリストを表示する。<br>
  - (理想１：アカウントに紐づける)
  - (理想２：サーバー上にアカウントとは関係ないDBを作成しておきどのアカウントでも共通で利用するできるようにする)

メインページと投稿ページへの遷移ボタンの作成<br>
(理想機能)リストをクリックした際にその画像が表示され、`Chart.js`で評価の結果を確認できる。

### 投稿ページ<br>
inputでローカルデバイス上のフォルダ内の画像をDBに投稿できるようにする。
### 評価ページ<br>
評価待ちのが画像がランダムで5つ表示され、その画像を評価する。<br>
(それらの画像はサーバー上に全てのアカウント共有のDBを作成しておきそこから引っ張る)