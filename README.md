## usersテーブル

|Column|Type|Option|
|------|----|------|

|name|string|null: false|
|e-mail|string|null: false, foreign_key: true|
|password|string|null: false, foreign_key: true|

### Asosiation
- has_many :groups_users
- has_many :groups, through: groups_users

## groupsテーブル

|Column|Type|Option|
|------|----|------|

|name|string|null: false|
|menber|integer|null: false|

### association
- has_many :groups_users
- has_many :users, through: groups_users

## messageテーブル

|Column|Type|Option|
|------|----|------|

|message|text|null:false|

### Association
- belongs_to :user
- belongs_to :group

## groups_usersテーブル

|Column|Type|Option|
|------|----|------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false. foreign_key: true|

### Association
- belongs_to :group
- belongs_to :user