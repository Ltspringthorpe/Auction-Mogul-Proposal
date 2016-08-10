## Schema Information

### users
column name      | data type | details
-----------------|-----------|-----------------------
id               | integer   | not null, primary key
username         | string    | not null, indexed, unique
password_digest  | string    | not null
session_token    | string    | not null, indexed, unique

### watchlist
column name | data type | details
------------|-----------|-----------------------
id          | integer   | not null, primary key
user_id     | integer   | not null, foreign key (references users), indexed
wow_id      | integer   | not null, foreign key (references Blizzard's database), indexed
WTB         | boolean   | not null, default true
WTS         | boolean   | not null, default true

### toon
column name | data type | details
------------|-----------|-----------------------
id          | integer   | not null, primary key
user_id     | integer   | not null, foreign key (references users), indexed
wow_id      | integer   | not null, foreign key (references Blizzard's database), indexed
