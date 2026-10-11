# pandas-datetime-practice
This repository provides practice notebooks and examples for working with date and time data in Pandas.

It includes a Jupyter Notebook with hidden solution cells and practice cells, that helps in actively testing data engineering skills — from extracting year/month to calculating busiest weekdays, rolling average and resampling by week.


🔧 Functions Covered

| Task              | Syntax |
|-------------------|--------|
| Convert to datetime | `pd.to_datetime(df["col"])` |
| Parse on read       | `pd.read_csv("f.csv", parse_dates=["col"])` |
| Custom format       | `pd.to_datetime(df["col"], format="%Y-%m-%d")` |
| Handle bad dates    | `pd.to_datetime(df["col"], errors="coerce")` |
| Extract year        | `df["col"].dt.year` |
| Extract month       | `df["col"].dt.month` |
| Extract day         | `df["col"].dt.day` |
| Day of week         | `df["col"].dt.dayofweek` |
| Set as index        | `df.set_index("date")` |
| Filter by year      | `df.loc["2018"]` *(with datetime index)* |
| Filter by range     | `df.loc["2018-01":"2018-06"]` |
| Filter by time      | `df.between_time("09:00", "17:00")` |
| Resample monthly    | `df.resample("M")["col"].count()` |
| Rolling average     | `df.resample("M")["col"].count().rolling(3).mean()` |
| Group by weekday    | `df.groupby(df["date"].dt.day_name())["col"].mean()` |
| Busiest week        | `df.resample("W")["col"].count().idxmax()` |
| Weekend vs weekday  | `df["date"].dt.dayofweek >= 5` *(boolean mask)* |

