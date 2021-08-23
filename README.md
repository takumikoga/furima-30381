# DB 設計

## users table

| Column             | Type                | Options                 |
|--------------------|---------------------|-------------------------|
| email              | string              | null: false             |
| password           | string              | null: false             |
| nickname           | string              | null: false             |

### Association

* has_many :products
* has_many :addresses

## products table

| Column             | Type                | Options                 |
|--------------------|---------------------|-------------------------|
| image              | text                | null: false             |
| name               | string              | null: false             |
| explanation        | text                | null: false             |
| category           | text                | null: false             |
| status             | text                | null: false             |
| delivery fee       | text                | null: false             |
| area               | text                | null: false             |
| days               | text                | null: false             |
| price              | text                | null: false             |
| user               | references          | foreign_key: true       |

### Association

- belongs_to :user
- belongs_to :address

## addresses table

| Column             | Type                | Options                 |
|--------------------|---------------------|-------------------------|
| postal code        | text                | null: false             |
| prefectures        | text                | null: false             |
| municipalities     | text                | null: false             |
| house number       | text                | null: false             |
| telephone number   | text                | null: false             |

### Association

* has_many :products
* has_many :users