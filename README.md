# 機能

- ユーザーがブログを投稿できる。
- ユーザーが自分のブログを編集できる。
- ユーザーが自分のブログを削除できる。
- ログインしていなくても、全てのブログを閲覧できる。

# 画面イメージ

![miniblog](https://user-images.githubusercontent.com/40832190/62202310-075ce080-b3c4-11e9-9b6f-8b53010d2ddb.png)

# DB 設計

## users table

|  Column  |  Type  |          Options          |
| :------: | :----: | :-----------------------: |
|   name   | string | null: false, unique: true |
|  email   | string | null: false, unique: true |
| password | string |        null: false        |

### Association

- has_many :articles

## articles table

| Column  |  Type   |      Options      |
| :-----: | :-----: | :---------------: |
|  text   |  text   |                   |
|  title  | string  |                   |
| user_id | integer | foreign_key: true |

### Association

- belongs_to :user

# 使用 Gem

- bootstrap
  - css フレームワーク
- font-awesome-rails
  - アイコン
- pry-rails
  - デバッグツール
- devise
  - ユーザー機能補助
- devise-i18n
- devise-i18n-views
  - devise の日本語化
- kaminari
  - ページネーション
- kaminari-bootstrap
  - ページネーションで bootstrap の使用補助
