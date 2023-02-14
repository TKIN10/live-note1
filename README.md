# テーブル設計

## users テーブル

| Column             | Type   | Options     |
| ------------------ | ------ | ----------- |
| name               | string | null: false |
| email              | string | null: false |
| encrypted_password | string | null: false |

### Association

- has_many :rooms
- has_many :messages


## rooms テーブル

| Column | Type   | Options     |
| ------ | ------ | ----------- |
| name   | string | null: false |

### Association

- belongs_to :user
- has_many :posts


## posts テーブル

| Column  | Type       | Options                        |
| ------- | ---------- | ------------------------------ |
| title   | string     | null: false                    |
| text    | string     | null: false                    |
| image   | string     | null: false                    |
| user    | references | null: false, foreign_key: true |

### Association

- belongs_to :room
- belongs_to :user
