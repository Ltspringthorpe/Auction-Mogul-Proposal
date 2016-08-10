# Auction Mogul
Auction Mogul will be a site to help with buying and selling on World of Warcraft's Auction House.

## MVP
- Integrates with Blizzard's authentication to connect to Battle.net
- Rails database for users login info and watched items / preferences
- Lets users search database or inventory for items to add to watchlist
- Uses Blizzard's auction house and inventory API
- Shows market information for watched and inventory items

## Components
- Form to add/remove watchlist items
- Index view of all watchlist items
- Index view of all popular items
- Index view of all good deals
- Show view of item
- Index view of your inventory/bank
- Index view of good deals specific to your watchlist and inventory/bank

## Schema

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

## Rough Timeline

### Week 1
- Rails authentication
- Blizzard authentication
- Setup Auction House API
- Watchlist form component
- Item-show component
- Item-index components

### Week 2
- Styling and CSS
- More CSS
- Oh my god there's so much CSS to be done

## Future Features
- Gets list of pets/mounts/recipes that your character doesn't know and adds them to the watchlist
- Sends email notifications if there's an awesome deal
