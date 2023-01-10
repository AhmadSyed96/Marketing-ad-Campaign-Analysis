# Marketing-Ad Campaign Analysis
this project focuses on resolving inconsistencies found in our dataset and scaling the losses incurred due to it

for more detailed analysis, open the jupyter notebook which breaks down into the following structure:

1. after taking a look at segments of conversion rates we see that the house ads marketing team has an issue with it after the 11th

2. after finding ut day of week had nothing to do with the issue we find that the language is where the issue is

3. after investigating the language we find that only english ads were served after the 11th 

4. to see how many subscribers were lost due to this error, we tracked the sub rate other languages went at per english sub and applied that to the error period and found a loss of 32 subs due to the error

---

we are given the following table describing customer data

|---------------------|---------|
|       column        |  type   |
|---------------------|---------|
| userid              | numeric |
| date_served         | date    |
| marketing_channel   | text    |
| variant             | text    |
| converted           | numeric |
| language_displayed  | text    |
| language_preferred  | text    |
| age_group           | text    |
| date_subscribed     | date    |
| date_canceled       | date    |
| subscribing_channel | text    |
| is_retained         | numeric |
| day_of_week         | text    |
| channel_code        | text    |
|---------------------|---------|

upon exploratory analysis we can see that there is a problem with conversion rates, particularly with the house ads conversion channel

```
daily_conversion_rate_by_channel = conversion_rate(marketing, ['date_served', 'subscription_channel'])
plotting_csv(daily_conversion_rate_by_channel.unstack(level=1))
```