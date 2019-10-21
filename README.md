# README
# C-Space

# Normal tables

## users table
|column|Type|Options|
|------|----|-------|
|name|string|add_index, null: false|
|passwords|string|null: false|
|email|string|null: false, unique: true|

### users Association
- has_many :messages
- has_many :groups, through: :groups_users

## messages table
|column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|body|text|null: false|
|image|text||

### messages Association
- belongs_to :users
- belongs_to :groups

## groups table
|column|Type|Options|
|------|----|-------|
|title|string|add_index, null: fase|

## groups Association
- has_many :users through: :groups_users
- has_many :messages

# Intermediate table

## groups_users table
|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

### groups_users Association
- belongs_to :group
- belongs_to :user





