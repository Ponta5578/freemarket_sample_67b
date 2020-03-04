# freemarket_sample_67b
- フリマアプリ「メルカリ」のクローンサイト。
- ER図 
- 本番環境にデプロイ
- 商品出品ページの実装
- 商品出品機能
- 商品詳細表示
- 商品情報編集
- 商品削除
- 商品詳細ページ
- 商品情報編集
- 商品削除
- ユーザーマイページ
- ユーザー新規登録
- カテゴリ機能
- 商品購入確認ページ
- 商品一覧表示
- 商品詳細ページ
- 商品購入機能
- ユーザー新規登録/ログインページ
- トップページ
![F2B210DF-CF8E-4A4E-849D-DDB93E661BA5](https://user-images.githubusercontent.com/59057488/75450290-dc665980-59b1-11ea-98d3-3a825f07c8c3.jpeg)
![54AC681C-081C-4BC4-8C50-946A2AC52E0C_1_105_c](https://user-images.githubusercontent.com/59057488/75450401-15063300-59b2-11ea-9c1d-bc69a1a3606f.jpeg)
![68C72DDD-9ACD-4D0B-80AA-36184CB34547_1_105_c](https://user-images.githubusercontent.com/59057488/75450406-18012380-59b2-11ea-90d9-10f42ff7c699.jpeg)
![22F47B82-7181-40E8-84F6-9E5DE6638323_4_5005_c](https://user-images.githubusercontent.com/59057488/75450588-74fcd980-59b2-11ea-839a-ef4d40faa6bc.jpeg)
![8F0376C6-23BC-4D35-83E2-3041330A3022_4_5005_c](https://user-images.githubusercontent.com/59057488/75450779-c73dfa80-59b2-11ea-84a9-94cf27d98d8c.jpeg)
![F4869A3D-FD8A-47DF-BA33-562B7A35A4ED_1_105_c](https://user-images.githubusercontent.com/59057488/75450890-f5bbd580-59b2-11ea-9caf-08586b320f45.jpeg)


## commentsテーブル
|Column|Type|Options|
|------|----|-------|
|text|string|null: false|
|user_id|references|null: false, foreign_key: true|
|item_id|references|null: false, foreign_key: true|
### Association
- belongs_to :user
- belongs_to :item

## usersテーブル
|Column|Type|Options|
|------|----|-------|
|nickname|string|null: false,limit:10|
|emall|string|null: false|
|password|string|null: false|
|first_name|string|null: false,limit:10|
|last_name|string|null: false,limit:10|
|first_kane|string|null: false,limit:10|
|last_kane|string|null: false,limit:10|
|post_number|interger|null: false|
|prefecture|string|null: false|
|city|string|null: false|
|house_number|string|null: false|
|building_name|string||
|phone_number|string||
|birthday|date|null: false|
|card|date|null: false|
|profile|string|null: false|
### Association
- has_many :comments
- has_many :items

## itemsテーブル
|Column|Type|Options|
|------|----|-------|
|buyer_id|references|foreign_key: true|
|seller_id|references|null: false, foreign_key: true|
|name|string|null: false|
|price|integer|null: false|
|status|text|null: false|
|cost|string|null: false|
|delivery|string|null: false|
|category_id|references|null: false, foreign_key: true|
|brand|string||
|deal|boolean||
|send_address|string|null: false|
|send_date|string|null: false|
|condition|string|null: false|
### Association
- belongs_to :category
- belongs_to :size
- belongs_to :brand
- belongs_to :user
- has_many :images
- has_many :comments

## categorysテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|

### Association
- has_many :items
- has_many :sizes, through: :categorys_sizes

## imagesテーブル
|Column|Type|Options|
|------|----|-------|
|image_name|string|null: false|
|item_id|reference|null: false, foreign_key: true|

### Association
- belongs_to :item

## brandsテーブル
|Column|Type|Options|
|------|----|-------|
|name|string|null: false|
### Association
- has_many :items

## cardsテーブル
|column|Type|Options|
|------|----|-------|
|card_id|string|null: false|
|customer_id｜string|null: false|
|user|references|null: false, foreign_key: true|

### Association
- belongs_to :user


This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...
