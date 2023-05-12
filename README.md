## usersテーブル

| Column              | Type       | Options                        |
| ------------------  | ---------- | ------------------------------ |
| email               | string     | not null  ユニーク制約           |
| encrypted_password  | string     | not null                       |
| name                | string     | not null                       |
| profile             | text       | not null                       |
| occupation          | text       | not null                       |
| position            | text       | not null                       |

### Association
- has_many :prototypes
- has_many :comments

## prototypesテーブル
| Column              | Type       | Options                        |
| ------------------  | ---------- | ------------------------------ |
| title               | string     | not null                       |
| catch_copy          | text       | not null                       |
| concept             | text       | not null                       |
| user                |references  | not null 外部キ-                |

### Association
- belongs_to :user
- has_many :comments
- has_one_attached :image

## commentsテーブル
| Column              | Type       | Options                        |
| ------------------  | ---------- | ------------------------------ |
| content             |text        | not null                       |
| prototype           |references  | not null 外部キ-                |
| user                |references  | not null 外部キ-                |

### Association
- belongs_to :user
- belongs_to :comments