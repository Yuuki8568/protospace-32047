# テーブル設計

## users テーブル

| Column     | Type   | Options     |
| ---------- | ------ | ----------- |
| email      | string | NOT:  NULL  |
| password   | string | NOT:  NULL  |
| name       | string | NOT:  NULL  |
| profile    | text   | NOT:  NULL  |
| occupation | text   | NOT:  NULL  |
| position   | text   | NOT:  NULL  |

### Association

- has_many :comments
- has_many :prototypes

## prototypes テーブル

| Column     | Type       | Options     |
| ---------- | ---------- | ----------- |
| title      | string     | NOT:  NULL  |
| catch_copy | text       | NOT:  NULL  |
| concept    | text       | NOT:  NULL  |
| user       | references | null: false |

### Association

- belongs_to :users
- has_many :comments

## comments テーブル

| Column     | Type       | Options     |
| ---------- | ---------- | ----------- |
| text       | text       | NOT:  NULL  |
| user       | references | null: false |
| prototype  | references | null: false |

### Association

- belongs_to :prototypes
- belongs_to :user