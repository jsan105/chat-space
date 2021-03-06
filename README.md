# README

## usersテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
|email|string|null: false|
|password|string|null: false|

### Association
- has_many :tweets
- has_many :groups_users
- has_many :groups, through: :groups_users



## messageテーブル
|Column|Type|Options|
|------|----|-------|
|text|string|
|image|string|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :user
- belongs_to :group


## groupテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
|user_id|integer|null: false, foreign_key: true|
|tweet_id|integer|null: false, foreign_key: true|

### Association
- has_many :tweets
- has_many :groups_users
- has_many :users, through: :groups_users



## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user