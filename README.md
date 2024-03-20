# README

# テーブル設計

##　usersテーブル
| カラム名            | データ型  | オプション                  |
| ------------------ | -------- | ------------------------- |
| email              | string   | null: false, unique: true |
| encrypted_password | string   | null: false               |
| name               | string   | null: false               |
| profile            | text     | null: false               |
| occupation         | text     | null: false               |
| position           | text     | null: false               |

- has_many :prototype
- has_many :comments

## prototypesテーブル
| カラム名    | データ型    | オプション                       |
| ---------- | ---------- | ------------------------------ |
| title      | string     | null: false                    |
| catch_copy | text       | null: false                    |
| concept    | text       | null: false                    |
| user       | references | null: false, foreign_key: true |

- has_many :comments
- belongs_to :user

## commentsテーブル
| カラム名   | データ型    | オプション                       |
| --------- | ---------- | ------------------------------ |
| content   | text       | null: false                    |
| prototype | references | null: false, foreign_key: true |
| user      | references | null: false, foreign_key: true |

- belongs_to :users
- belongs_to :prototypes