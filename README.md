users テーブル
| Column              | Type            | Options            |
|                     |                 |                    |
| email               | integer         | NOT NULL, unique   |
| encrypted_password  | string          | NOT NULL           |
| family_name         | string          | NOT NULL           |
| first_name          | string          | NOT NULL           |
| family_katakana     | string          | NOT NULL           |
| first_katakana      | string          | NOT NULL           |
| birth_year          | string          | NOT NULL           |
| birth_month         | string          | NOT NULL           |
| birth_day           | string          | NOT NULL           |

Association
- `users` 1 : N `items`（1人のユーザーは複数の商品を出品できる）


items テーブル
| Column              | Type            | Options            |
|                     |                 |                    |
| title               | string          | NOT NULL           |
| price               | integer         | NOT NULL           |
| category            | string          | NOT NULL           |
| status              | string          | NOT NULL           |
| shipping_fee        | string          | NOT NULL           |
| user_id             | reference       | foreign key(users) |
| image_url           | string          | NOT NULL           |

Association
- `items` 1 : 1 `purchases`（1つの商品は1回のみ購入される）


purchases テーブル
| Column              | Type            | Options            |
|                     |                 |                    |
| user_id             | reference       | foreign key(users) |
| item_id             | reference       | foreign key(items) |

Association
- `purchases` 1 : 1 `addresses`（1回の購入につき1つの配送先が紐づく）

addresses テーブル
| Column              | Type            | Options            |
|                     |                 |                    |
| user_id             | reference       | foreign key(purchases) |
| postal_code         | string          | NOT NULL           |
| prefecture          | string          | NOT NULL           |
| city                | string          | NOT NULL           |
| address_line        | string          | NOT NULL           |
| building_name       | string          |                    |
| tel_num             | string          | NOT NULL           |







