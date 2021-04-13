# README

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


# テーブル設計

## users テーブル

| Column             | Type   | Options                  |
| ----------------- -| ------ | ------------------------ |
| nickname           | string | NOT NULL                 |
| email              | string | unique: true, null: false|
| encrypted_password | string | NOT NULL                 |
| last_name          | string | NOT NULL                 |
| first_name         | string | NOT NULL                 |
| last_name_kana     | string | NOT NULL                 |
| first_name_kana    | string | NOT NULL                 |
| birthday           | date   | NOT NULL                 |

### Association

- has_many :property
- has_many :agreements

## properties テーブル

| Column        | Type       | Options                       |
| ------------- | ---------- | ----------------------------  |
| prefecture_id | integer    | NOT NULL                      |
| price         | integer    | NOT NULL                      |
| layout_id     | integer    | NOT NULL                      |
| period_id     | integer    | NOT NULL                      |
| user_id       | integer    | foreign_key:true, null: false |
### Association

- belongs_to :user
- has_one :agreement

## agreements テーブル

| Column             | Type       | Options                      |
| ------------------ | ---------- | ---------------------------- |
| user_id            | integer    | foreign_key:true, null: false|
| property_id        | integer    | foreign_key:true, null: false|
| phone_number       | string     | NOT NULL                     |


### Association

- belongs_to :property
- belongs_to :user








