FunTrip

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