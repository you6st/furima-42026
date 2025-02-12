users テーブル
| Column              | Type            | Options            |
|                     |                 |                    |
| email               | integer         | null: false, unique: true   |
| encrypted_password  | string          | null: false        |
| family_name         | string          | null: false        |
| first_name          | string          | null: false        |
| family_katakana     | string          | null: false        |
| first_katakana      | string          | null: false        |
| birth_date          | date            | null: false        |

Association
- has_many :items


items テーブル
| Column              | Type            | Options            |
|                     |                 |                    |
| title               | string          | null: false        |
| price               | integer         | null: false        |
| category_id         | integer         | null: false        |
| status_id           | integer         | null: false        |
| shipping_fee_id     | integer         | null: false        |
| shipping_prefecture | string          | null: false        |
| shipping_date       | string          | null: false        |
| user                | reference       | foreign_key: true  |

Association
- has_one :purchases


purchases テーブル
| Column              | Type            | Options            |
|                     |                 |                    |
| user                | reference       | foreign_key: true  |
| item                | reference       | foreign_key: true  |

Association
- has_one :addresses

addresses テーブル
| Column              | Type            | Options            |
|                     |                 |                    |
| user                | reference       | foreign key: true  |
| postal_code         | string          | null: false        |
| prefecture          | string          | null: false        |
| city                | string          | null: false        |
| address_line        | string          | null: false        |
| building_name       | string          |                    |
| tel_num             | string          | null: false        |







