FunTrip

### 概要
観光地にスポットをあてた画像投稿サイト

### URL
未デプロイ

### 利用方法
ユーザー未登録者は画像の閲覧のみ可能
ユーザー登録者は画像の投稿、コメントの投稿が可能

### 目指した課題解決
Twitterよりも観光に特化したアプリケーションの作成
簡単な観光気分を味わえるものを作ることで、今のこのご時世の息苦しさ解消に少しでも貢献したい。
将来的には、このアプリケーションに投稿された内容を元に現地に足を運んでもらいたいという期待感も込めている。

## Usersテーブル

| Column   | Type   | Options                   |
| -------- | ------ | ------------------------- |
| nickname | string | null: false               |
| email    | string | null: false, unique: true |
| password | string | null: false               |
| name     | string | null: false               |

### Association
- has_many :pictures
- has_many :comments

## Picturesテーブル

| Column        | Type      | Options                        |
| ------------- | --------- | ------------------------------ |
| title         | string    | null: false                    |
| prefecture_id | integer   | null: false                    |
| description   | text      |                                |
| image         |           |                                |
| user          | reference | null: false, foreign_key: true |

### Association
- belongs_to :user
- has_many :comments

## Commentsテーブル

| Column  | Type      | Options                        |
| --------| --------- | ------------------------------ |
| user    | reference | null: false, foreign_key: true |
| picture | reference | null: false, foreign_key: true |
| comment | text      | null: false                    |