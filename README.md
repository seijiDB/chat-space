## usersテーブル

|Column|Type|Option|
|------|----|------|
|name|string|null: false, index:true|
|e-mail|string|null: false|
|password|string|null: false|

### Asosiation
- has_many :groups_users
- has_many :groups, through: :groups_users
- has_many :messages

## groupsテーブル

|Column|Type|Option|
|------|----|------|
|name|string|null: false|

### association
- has_many :groups_users
- has_many :users, through: :groups_users
- has_many :messages

## messageテーブル

|Column|Type|Option|
|------|----|------|
|message|text|null:false|
|image|text|
|user_id|references|null: false, foreign_key: true|
|group_id|references|null: false, foreign_key: true|

### Association
- belongs_to :user
- belongs_to :group

## groups_usersテーブル

|Column|Type|Option|
|------|----|------|
|user_id|references|null: false, foreign_key: true|
|group_id|references|null: false. foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user