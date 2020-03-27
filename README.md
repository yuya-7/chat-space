# README

## chat-space
## usersテーブル
|Column|Type|Options|
|------|----|-------|
|email|string|null: false, unipue: true|
|password|string|null: false|
|name|string|null: false|
### Association
- has_many :groups_users
- has_many :groups, through: groups_users
- has_many :messeges

## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
### Association
- has_many :groups_users
- has_many :users, though: groups_users
- has_many :messeges

## groups_usersテーブル
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false,foreign_key: true|
### Association
belongs_to :user
belongs_to :group

## messegesテーブル
|Column|Type|Options|
|------|----|-------|
|body|text||
|image|string||
|group_id|integer|null: false, foreign_key: true|
|user_id|integer|null: false, foreign_key: true|
### Association
belongs_to :group
belongs_to :user