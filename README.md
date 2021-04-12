## users テーブル

| Column | Type | Options |
| ---------- | -------- | -------- |
| name | string | null: false |
| nickname | string | null: false|

- has_many :comments
- has_many :pictures, through: :comments

## pictures テーブル

| Column | Type | Options |
| ---------- | -------- | -------- |
| title      | string | null: false |
| catch_copy | text | null: false |
| concept      | text | null: false |
| image    | ActiveStorage | ------- |
| genre    |  integer |  null: false |
| age   |  integer |  null: false |
| user | references | null: false  |

- has_many : comments
- has_many : users, through: :comments


## commentsテーブル

|  Column | Type | Options |
| ------------ | ------- | ---------- |
| text      | text | null: false |
| user | references | null: false |
| picture_book |  references  | -------- | 

- belongs_to :users
- belongs_to :pictures

## nice_functionテーブル

|  Column | Type | Options |
| ------------ | ------- | ---------- |
| user_id | references | null: false |
| picture_book_id |  references  | null: false | 

- belongs_to :users
- belongs_to :pictures