# DB 設計

## users table

| Column             | Type   | Options                   |
|--------------------|--------|---------------------------|
| nickname           | string | null: false, unique: true |
| email              | string | null: false, unique: true |
| encrypted_password | string | null: false               |


### Association

* has_many :tweets
* has_many :comments

## tweets table

| Column  | Type       | Options           |
|---------|------------|-------------------|
| user    | references | foreign_key: true |
| tweet   | references | foreign_key: true |

* belongs_to :user
* has_many :comments

## comments table

| Column  | Type       | Options           |
|---------|------------|-------------------|
| text    | text       | null: false       |
| user    | references | foreign_key: true |
| product | references | foreign_key: true |


### Association

* belongs_to :user
* belongs_to :tweet