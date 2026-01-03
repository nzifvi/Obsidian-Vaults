[[1,2,1 - SQL DDL]] <- Back

---
# 1) SQL Types

## 1.1) String Types

| Name       | Default Size                  | Modifiable Size? |
| ---------- | ----------------------------- | ---------------- |
| VARCHAR    | No default, one must be given | Yes              |
| CHAR       | Default = 8 bits (<= 255)     | Yes              |
| TEXT       | 2^16 bytes (64KB)             | No               |
| TINYTEXT   | 2^8 bytes                     | No               |
| MEDIUMTEXT | 2^24 bytes                    | No               |
| LONGTEXT   | 2^32 bytes                    | No               |

## 1.2) Numeric Types

| Name           | Default                       | Modifiable Size |
| -------------- | ----------------------------- | --------------- |
| INT            | 4 byte                        | No              |
| TINYINT        | 1 byte                        | No              |
| SMALLINT       | 2 byte                        | No              |
| BIGINT         | 8 byte                        | No              |
| BIT            | No default, one must be given | Yes             |
| FLOAT / DOUBLE | Unknown                       | No              |
| DECIMAL        | Unknown                       |                 |


## 1.3) Other Types

| Name     | Default | Modifiable Size |
| -------- | ------- | --------------- |
| DATE     |         |                 |
| TIME     |         |                 |
| DATETIME |         |                 |
| BLOB     |         |                 |
| TINYBLOB |         |                 |
| LONGBLOB |         |                 |
