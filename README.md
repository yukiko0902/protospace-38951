
## users テーブル
| Column             | Type       | Options                  |
| -------------------| ---------- | -------------------------|
| email              | string     | null: false, unique:true |
| encrypted_password | string     | null: false              |

### Association

-has_many :prototypes
-has_many :comments

## prototypes テーブル
| Column     | Type        | Options                         |
| -----------| ------------|---------------------------------|
| title      | string      | null: false                     |
| catch_copy | text        | null: false                     |
| concept    | text        | null: false                     |
| user       | references  | null: false, foreign_key: true  |

### Association
-has_many :comments
-belongs_to :user

## comments テーブル
| Column    | Type         | Option                          |
| ----------| -------------| --------------------------------|
| content   | text         | null: false                     |
| prototype | references   | null: false, foreign_key: true  |
| user      | references   | null: false, foreign_key: true  |

### Association
-belongs_to :user
-belongs_to :prototype

