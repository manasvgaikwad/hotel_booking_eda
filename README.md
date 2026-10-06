# Hotel Booking Demand: Exploratory Data Analysis

An end-to-end exploratory data analysis (EDA) of hotel booking data using Python. The project cleans a messy real-world dataset and answers business questions about bookings, cancellations, pricing and guest behaviour.

## Dataset

- **Source:** [Hotel Booking Demand on Kaggle](https://www.kaggle.com/datasets/jessemostipak/hotel-booking-demand) (originally from Antonio, Almeida and Nunes, *Data in Brief*, 2019)
- **Content:** bookings for a City Hotel (Lisbon) and a Resort Hotel (Algarve), Portugal, from July 2015 to August 2017
- **Size:** 119,390 rows and 32 columns before cleaning, 86,637 rows and 35 columns after cleaning

## Tools

Python, pandas, NumPy, Matplotlib, Seaborn, Jupyter Notebook

## Data Cleaning

| Step | Action |
|---|---|
| Duplicates | Removed 31,994 duplicate rows |
| Missing values | Filled `children` and `agent` with 0, `country` with "Unknown", dropped `company` (about 94% missing) |
| Data types | Converted `children` and `agent` to int, `reservation_status_date` to datetime |
| Invalid rows | Removed 166 zero-guest bookings and 2 bookings with negative or extreme ADR |
| Zero-night stays | Removed bookings with no nights stayed |
| New columns | `total_guests`, `total_nights`, `arrival_date`, `revenue` |
| Month order | Set `arrival_date_month` as an ordered category (January to December) |

## Business Questions

1. How many bookings does each hotel get, and what share is cancelled?
2. Which months are busiest, and which earn the most revenue?
3. How does lead time relate to cancellation?
4. Which market segments and distribution channels bring the most bookings and cancellations?
5. Does deposit type affect cancellation?
6. How does ADR (Average Daily Rate) change across months and between the two hotels?
7. What is the typical length of stay, and does it differ by hotel?
8. Which countries do guests come from?
9. Do repeat guests cancel less?
10. Do special requests or parking spaces relate to cancellation?

## Key Findings

- **27.7%** of all bookings are cancelled. City Hotel cancels more (30.2%) than Resort Hotel (23.7%).
- Cancelled bookings were made about **35 days earlier** on average (105.8 days vs 70.5 days).
- Online travel agents are the biggest booking source and cancel more than Direct, Corporate and Offline TA/TO bookings.
- **Repeat guests** cancel far less: 8.2% vs 28.4% for new guests.
- ADR is strongly seasonal, peaking in August (about 150) and lowest in winter (about 70). City Hotel has a higher average ADR than Resort Hotel.
- **Summer is peak season:** August and July are the busiest months (11,194 and 9,988 bookings) and earn the most revenue (about 4.6M and 3.8M).
- The typical stay is **3 nights**. Resort Hotel guests stay longer on average than City Hotel guests.
- **Portugal** is the main source market (31% of bookings), and the top 5 countries are all European (about 68%).
- Cancellation falls as special requests rise (about 33% with none, about 5% with five), and guests who required a parking space virtually never cancelled.
- "Non Refund" bookings show a 94.7% cancellation rate, a known oddity in this dataset, so it is not read as a cause.

## Recommendations

- Ask for deposits or send reminders on bookings made far in advance.
- Encourage direct and repeat bookings, which cancel far less.
- Monitor online travel agent bookings, the largest group but the least reliable.

## Limitations

- The data covers two hotels in Portugal over about two years, so the findings may not apply elsewhere.
- July and August appear in three years of data and other months in two, so they look busier partly for that reason.
- The analysis shows relationships, not causes.

## Files

- `hotel_booking.ipynb`: the full notebook (cleaning and EDA)
- `hotel_bookings.csv`: the raw dataset

## Author

**Manas**
