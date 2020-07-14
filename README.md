# 開発について
### 私は長く介護業界にいました。どの業界でも情報の共有は大切でとても重要な物だと思います。
### 介護、医療の現場では情報共有不足によって命を落とす危険すらあります。
### 全スタッフが（年齢や機械が強い弱いにかかわらず）簡単に情報共有ができるものを目指しています。


# DB設計
## usersテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
|email|string|null: false|
|password|string|null: false|
ra
## Association
has_many : messages
has_many : groups_users
has_many : groups, through: groups_users

## groupsテーブル
|Column|Type|Options|
|------|----|-------|
|title|string|null: false|

## Association
has_many : messages
has_many : groups_users
has_many : users, through: groups_users


## messagesテーブル 
|Column|Type|Options|
|------|----|-------|
|body|text|
|image|string|
|group_id|integer|null: false, foreign_key: true|
|user_id|integer|null: false, foreign_key: true|

## Association
- belongs_to :group
- belongs_to :user


## groups_usersテーブル

|Column|Type|Options|
|------|----|-------|
|user_id|integer|null: false, foreign_key: true|
|group_id|integer|null: false, foreign_key: true|

## Association
- belongs_to :group
- belongs_to :user
