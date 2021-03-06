# テーブル設計

## users テーブル

| Column     | Type   | Options  |
|------------|--------|----------|
| email      | string | NOT NULL |
| password   | string | NOT NULL |
| name       | string | NOT NULL |
| profile    | text   | NOT NULL |
| occupation | text   | NOT NULL |
| position   | text   | NOT NULL |

### Association

has_many :prototypes
has_many :comments

## prototypes テーブル

| column     | Type   | options      |
|------------|--------|--------------|
| title      | string     | NOT NULL |
| catch_copy | text       | NOT NULL |
| concept    | text       | NOT NULL |
| user       | references |          |

### Association

has_many :comments
belongs_to :user

## comments テーブル

| Column    | Type       | options  |
|-----------|------------|----------|
| text      | text       | NOT NULL |
| user      | references |          |
| prototype | references |          |

## Association

belong_to :comments
belongs_to :user