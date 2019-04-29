# Overview

The data sources for each table are located inside the `raw_data/` directory as CSV files.


# _Kapten_ Data Description

## Users Table
| column | definition |
| --- | ------- |
| `user_id` | *unique user id, primary key* |
| `loyalty_status` | *user loyalty status stored as integer: 0 = red, 1 = silver, 2 = gold, 3 = platinum* |
| `loyalty_status_txt` | *user loyalty status stored as text: red, silver, gold, platinum* |


## Rides Table
| column | definition |
| --- | ------- |
| `ride_id` | *unique ride id, primary key* |
| `user_id` | *user id* |
| `from_zipcode` | *zip code of the ride start location* |
| `to_zipcode` | *zip code of the ride end location* |
| `state` | *state of the ride: completed, not_completed: whether the ride was completed or not (for whatever possible reason)* |
| `quote_date` | *local date when the user sees the price of a ride in his app before ordering it* |
| `completed_date` | *local date when the ride is actually completed successfully* |
| `price_nominal` | *price of the ride* |
| `loyalty_points_earned` | *loyalty points awarded by the ride if elligible (=payed with real money, without discount or loyalty points). Only completed rides are eligibles.* |


## Python Pandas

From the `raw_data/*.csv` CSV files, answer the following questions using the Python Pandas library:
1. Write a function which returns a dataframe listing all the users, by computing (if needed) the following columns:
* user_id
* loyalty_status
* loyalty_status_txt
* daily_date: date of ride day
* nb_rides: number of completed rides made by the user for the given day
* total_price: total ride price spent by the user for the given day
2. Write a function which returns a dataframe listing the average basket per day. The average basket is the average completed ride price for a given period of time.
3. Write a function which returns a dataframe listing the 5 days with the lowest number of completed rides, ordered chronologically.
4. Create a chart plotting the number of completed rides per week for each loyalty status.


## SQL

Write the equivalent SQL queries answering the first three previous Pandas questions (ignore the chart question), if needed you can load data into a SQLite database to try your queries for instance.


## How to answer

1. Send us back your updated project as a zip/tar.gz archive or push it to [GitHub](https://github.com/), [Bitbucket](https://bitbucket.org/), etc. and send us the repository address.
