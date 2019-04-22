# DB設計

## membersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null:false,foreign_key:true|
|group_id|integer|null:false,foreign_key:true|

### Association
- belongs_to :group
- belongs_to :user

## messageテーブル
|Column|Type|Options|
|------|----|-------|
|body|text||
|image|string||
|group_id|integer|null:false,foreign_key:true|
|user_id|integer|null:false,foreign_key:true|

### asociation
- belongs_to :group
- belomgs_to :user

## Groupsテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null:false,unique:true,index|

### asociation
- has_many :messages
- has_many :manbers
_ has_many :users through::group_users


## usersテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null:false,unique:true|
|e-mail|string|null :false,unique:true|


### asociation
- has_many :messages
- has_many :manbers
_ has_many :group, through::group_users

