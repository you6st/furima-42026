users テーブル
| Column              | Type            | Options     |
|                     |                 |             |
| email               | string          | null: false, unique: true |
| encrypted_password  | string          | null: false |
| nickname            | string          | null: false |
| family_name         | string          | null: false |
| first_name          | string          | null: false |
| family_katakana     | string          | null: false |
| first_katakana      | string          | null: false |
| birth_date          | date            | null: false |

Association
- has_many :items


items テーブル
| Column                 | Type            | Options     |
|                        |                 |             |
| title                  | string          | null: false |
| detail                 | text            | null: false |
| price                  | integer         | null: false |
| category_id            | integer         | null: false |
| status_id              | integer         | null: false |
| shipping_fee_id        | integer         | null: false |
| shipping_prefecture_id | integer         | null: false |
| shipping_date_id       | integer         | null: false |
| user                   | references      | foreign_key: true |

Association
- has_one :purchase


purchases テーブル
| Column              | Type            | Options           |
|                     |                 |                   |
| user                | references      | foreign_key: true |
| item                | references      | foreign_key: true |

Association
- has_one :address
- belongs_to :item
- belongs_to :user


addresses テーブル
| Column              | Type            | Options           |
|                     |                 |                   |
| purchase            | references      | foreign key: true |
| postal_code         | string          | null: false       |
| prefecture          | integer         | null: false       |
| city                | string          | null: false       |
| address_line        | string          | null: false       |
| building_name       | string          |                   |
| tel_num             | string          | null: false       |


Association
- belongs_to :purchase





