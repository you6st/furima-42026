users　テーブル
| Column              | Type            | Options            |
|                     |                 |                    |
| email               | integer         | NOT NULL, unique   |
| encrypted_password  | string          | NOT NULL           |
| name                | string          | NOT NULL           |
|                     |                 |                    |
|                     |                 |                    |
|                     |                 |                    |


items テーブル
| Column              | Type            | Options            |
|                     |                 |                    |
| title               | string          | NOT NULL           |
| price               | integer         | NOT NULL           |
| description         | text            | NOT NULL           |
| user_id             | reference       | foreign key(users) |
|                     |                 |                    |
|                     |                 |                    |
|                     |                 |                    |


item_images テーブル
| Column              | Type            | Options            |
|                     |                 |                    |
| item_id             | reference       | foreign key(users) |
| image_url           | string          | NOT NULL           |
|                     |                 |                    |
|                     |                 |                    |
|                     |                 |                    |
|                     |                 |                    |
|                     |                 |                    |


purchases テーブル
| Column              | Type            | Options            |
|                     |                 |                    |
| user_id             | reference       | foreign key(users) |
| item_id             | reference       | foreign key(items) |
|                     |                 |                    |
|                     |                 |                    |
|                     |                 |                    |
|                     |                 |                    |
|                     |                 |                    |


address テーブル
| Column              | Type            | Options            |
|                     |                 |                    |
| user_id             | reference       | foreign key(users) |
| postal_code         | string          | NOT NULL          |
| prefecture          | string          | NOT NULL           |
| city                | string          | NOT NULL           |
| address_line        | string          | NOT NULL           |
| tel_num             | string          | NOT NULL           |
|                     |                 |                    |


- `users` 1 : N `items`（1人のユーザーは複数の商品を出品できる）
- `users` 1 : 1 `addresses`（1人のユーザーが1つの配送先住所を持つ）
- `items` 1 : 1 `purchases`（1つの商品は1回のみ購入される）
- `items` 1 : N `item_images`（1つの商品に複数の画像を持てる）
- `purchases` 1 : 1 `addresses`（1回の購入につき1つの配送先が紐づく）

