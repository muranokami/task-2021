README

アプリ名				
ToDoList

概要
①タスクに写真を貼り付けたりやり終えたタスクを削除していきとても使いように構築した。
②タスクにURLを入れるとそのページに飛ぶように考えました。
③タスクが多すぎても見づらくならないようにページ移動や、検索機能をつけました。
④ログイン機能もついているので自分だけのスケジュール管理ができる。
⑤rails c をすることで最初のユーザーを登録したり、そのユーザーのidを使ってタスクを100部増やすことができる
⑥管理者権限に印をつけないとタスク機能が使えないようにしました。

本番環境

制作背景
①仕事やプライベートなどでやることがたくさんある人や、物忘れが多い人にやるべきことを整理して行動してほしいと思い作成しました。
②タスクを書き出すことで自分のやることがわかりやすいので物忘れが少なくります。
③私自身も物忘れが多いので整理したい時に使おうと思いました。
④紙に書いていくよりかはタスク機能を使ってまとめたり写真を載せることでやることを明白にするのがいいと思いました。
⑤優先順位をつけて効率的に活用できる。
⑥削除機能があることから何度も同じことをしないようにしている。

どんな課題や不便なことを解決するためにこのアプリを作ったのか。
①忘れごとが多い友達や高齢者の人に使っていたくと認知症対策や忘れごとが減っていくと思い制作しました。
②仕事とプライベートがすごく忙しくて大変な人に使ってもらいたいと思いました。
③優先順位を決めるのが苦手な人

・DEMO
トップページ
https://gyazo.com/ee96132bd2a4308ec5d91a7bbd72e07d
タスク機能をトップページにしてあります。
ユーザー登録をしたら何もタスクのない状態で開きます。
タスクの新規登録や検索機能がありどんどんタスクを増やしたり、タスクを探しやすく設計してあります。
ぜひタスクを増やしていきましょう！

新規登録画面
https://gyazo.com/a7858d13ad0a8d697bb3503b37cb0470
至ってシンプルな設計ですが、ユーザー登録することで自分だけのタスク管理ができます。
ユーザーの新規登録画面から登録するとユーザー一覧画面に遷移します。
管理者権限の印にチェックしないとタスク機能が使えないようにしました。

ユーザー一覧画面
https://gyazo.com/bd920e94408767ce953ea17f91f1f3a1
ユーザー登録した人が載っています。
ユーザーを編集したり削除することができます。

ログイン画面
https://gyazo.com/06322c48bc610ff7e69155bbe0263154
ログインには、パスワードとメールアドレスが載っています。
ログインしたらトップページに遷移し自分が登録したタスクが載っています。

詳細表示画面
https://gyazo.com/5c633da33aba710ba6ac25b1e4aa8ec2
https://gyazo.com/4c860995aab1979700273f0cbb3f5bfd
詳細画面は、ユーザー登録とタスクの詳細の２つあります。
詳細にいくことでタスク機能の削除や編集ができます。
タスク機能の詳細画面には画像をつけたら、大きく写真が写っています。


編集画面
https://gyazo.com/98aede36f1a97faa170f86287089c7db
https://gyazo.com/46f3d46b25fd201ebb51abe705a4a1f3
編集画面にもタスクとユーザーがあります。
更新するボタンを押すと、編集した部分が反映されます。
タスクの編集画面には画像フォルダもあります。

ログアウトを押したらログイン画面に遷移します。

工夫したポイント
①csvを導入する時にうまくファイルを読み込めなかったのでホームページで調べたりすることで改善することはできました。
②最初ユーザー登録する時にrails cでユーザーを作らないといけないことを知らなかったので一から制作し直したりした。
③ログインした時に、他のユーザーが書いたタスクが見えていたのでそれを改善するのに時間がかかりました。
④gemでslimを使っていたので少しでもコードがずれていると構文エラーにつながったのでコードの起き位置を考える必要があ利ました。

・使用技術(開発環境)
バックエンド
Ruby on Rails

フロントエンド
html,css,javascript

データベース
sql,Sequel Pro

テスト
RSpec

エディタ
VSCode

課題や追加したい機能
①エラーが出るとなかなか解決できなかったら諦めてしまうところ
②エラーが出ると解決できずにまた一から制作し直すことがある
③ToDoListにカレンダーをつけてみたい
④ToDoList意外にもホームページを自分で考えて制作してみたい（時間があったら）

# DB設計

##  users table

| Column             | Type   | Options     |
|--------------------|--------|-------------|
| name               | string | null: false |
| email              | string | null: false |
| password_digest    | string | null: false |

### Association

belongs_to :user

## tasks table

| Column             | Type   | Options     |
|--------------------|--------|-------------|
| name               | string | null: false |
| description        | text   |             |
        
### Association

has_many :tasks

