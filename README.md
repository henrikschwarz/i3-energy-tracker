# I3 blocks kW/h price for energy

Provides a script for showing how much energy costs right now. This is done using the [Enrgi West API](https://nrgi.dk/api/common/pricehistory?region=DK1&date=2022-8-24). It returns the price for the current hour and stores it in a JSON object. Maybe changing it later to be a SQLite database.

# Example
![2022-08-26T07:54:32 CEST](https://user-images.githubusercontent.com/18546761/186832156-ad1099d4-094f-4e8c-8e4f-28a7e7d47348.png)

# Using
Clone the repo into your i3blocks folder (typically `~/.config/i3blocks/` or `~/.config/i3blocks/scripts`). Then add the block below into your `config` file:

```
[Energy]
markup=pango
command=~/.config/i3blocks/i3-energy-tracker/main.py now
background=#000000
interval=600
```

refresh your i3 bar (`alt+shift+r`)

# Todo:


Some todo items:
- [x] Pick some better colors for the block (Maybe use RGBA?).
- [ ] Add configuration for selecting ranges.
  - [ ] Add cli configuration for cutoffs (setting COLOR_MIN and COLOR_MAX via cli).
  - [ ] Add a setting for selecting coloring based on percentage of highest and lowest price for the day.
- [ ] Add an on click event that shows a table of prices for the whole day.
  - [x] Write the pango element code.
  - [x] Get it to show with Rofi.
  - [ ] Make the on click event + Rofi work.
- [ ] Add support for selecting more markets (eg. Denmark Eastern Market or custom variable ones.)
  - [ ] Added in a comment thje east market price data.
  - [ ] Add a check so that the JSON file is the correct market data if you switch.
