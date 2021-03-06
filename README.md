# アプリ名
sugar-ken9

# 概要
<p>オンライン将棋大会の対戦記録が行えます。総当たりリーグ戦の結果を手軽に記入し、棋譜も保存できます。また、その棋譜をAIで解析することもできます。</p>

# 本番環境
## Heroku
https://sugar-ken-7.herokuapp.com/
<p>ユーザー名：zengoma</p>
<p>パスワード：114514</p>

# 制作背景
<p>藤井聡太プロの影響で、将棋界が盛り上がっています。ところが、最近では将棋大会が中止になるばかりです。そこで、オンライン将棋大会の機会が増えてきましたが、対戦結果や棋譜の共有が困難で、紙に書いて写メを送ったりしていると手間がかかります。そこで、Webアプリケーションで運営を自動化できると考え、総当たりリーグのアプリケーションを開発しました。</p>

# 工夫したポイント
<p>リーグ戦の結果記入をクリックだけで済むように実装しました。例えば、AさんがBさんに勝利した場合、AさんとBさんの対戦のマス目をクリックすると「○」が付き、反対側のマス目に「●」が自動で付きます。そして、棋譜入力欄も設け、入力後は「○」か「●」をクリックすると、その対戦棋譜を閲覧することができます。さらに、その棋譜をAIに接続して解析することもできるので、高度な振り返りも可能です。</p>

# 使用技術（開発環境）
Ruby/Ruby on Rails/HTML/CSS/MySQL/Github/Visual Studio Code

# DB設計

## members テーブル

| Column      | Type   | Options     |
| ----------- | ------ | ----------- |
| name        | string | null: false |
| account     | string |             |
| achievement | text   |             |


### Association

- has_many :results

## results テーブル

| Column      | Type       | Options     |
| ----------- | ---------- | ----------- |
| member      | references | null: false |
| op_id       | integer    | null: false |
| result      | string     |             |

### Association

- belongs_to :member

## kifus テーブル

| Column    | Type    | Options     |
| --------- | ------- | ----------- |
| date      | date    | null: false |
| sente_id  | integer | null: false |
| gote_id   | integer | null: false |
| result_id | integer | null: false |
| kifu      | text    | null: false |

# CLEARDB_DATABASE_URL
mysql://bd49cc3e67dde7:88c303cc@us-cdbr-east-02.cleardb.com/heroku_5c145a604fe580d?reconnect=true

## ホスト
us-cdbr-east-02.cleardb.com

## ユーザー名
bd49cc3e67dde7

## パスワード
88c303cc

## データベース
heroku_5c145a604fe580d