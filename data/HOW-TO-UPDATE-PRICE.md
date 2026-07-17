# How to update the price — daily reference

Edit `data/price.json` each day. Do not touch `index.html` for this — it reads from this file automatically.

## Formula

```
Change % = ((Today - Yesterday) / Yesterday) x 100
```

**Example:**
- Yesterday = 27900 (per 100kg)
- Today = 28200 (per 100kg)
- (28200 - 27900) / 27900 x 100 = 1.08% → round to 1.1
- direction = "up"

## Fields in price.json

| Field | Meaning |
|---|---|
| `price` | Today's rate in ₹ per **kg** (many sources quote per 100kg — divide by 100 first) |
| `change_percent` | Result of the formula above, rounded to 1 decimal |
| `direction` | `"up"`, `"down"`, or `"flat"` |
| `last_updated` | Today's date, format `YYYY-MM-DD` |

## Where to check today's price

- commoditymarketlive.com/rubber-price/kottayam-market
- rubberindiaonline.com

Both usually show today's price next to the previous day's price on the same page — use those two numbers directly in the formula above.
