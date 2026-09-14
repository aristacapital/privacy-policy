# Wishlist

A Chrome extension for saving things you want to buy, ranking them, and seeing
where your monthly budget cuts the list off.

## Installing it

1. Open `chrome://extensions` in Chrome.
2. Turn on **Developer mode** (top right).
3. Click **Load unpacked** and pick this folder.
4. Pin Wishlist to the toolbar so the button is always visible.

If you downloaded the `.zip`, unzip it first and point step 3 at the unzipped
folder.

## The on-page panel

A small jade tab sits on the right edge of every page. Click it and a panel
slides out with the current product, a price box, a Save button, and your ranked
list with the budget line drawn in. Before you save, it tells you where the item
would land: fits above the line with money to spare, or below it by a given
amount.

A white dot on the tab means a price was detected on the page. The panel never
opens on its own.

**Hide on this site** in the panel footer removes it from that domain for good.
Hidden domains are listed under `wl_hidden` in storage; clearing the extension's
data brings them all back.

This is the part that needs broad access. The content script runs on every
http/https page you visit, which is why Chrome will warn about reading site
data on install. It reads the page for a name, price and image, and writes
nothing anywhere except your own local storage.

## Using it

**First run.** Either type in a monthly budget you already have in mind, or
answer five questions and get one worked out for you.

**Saving.** On a product page, click the Wishlist button. The extension reads
the page for a name, price and image, you confirm the price, and it saves. You
can also right-click anywhere on the page and choose **Save to Wishlist**.

**The cap.** Ten items, hard. The eleventh makes you choose what to let go of.

**Ranking.** Drag rows, or use the Up and Down links. The order is your order of
wanting.

**The budget line.** It runs across the list wherever the budget stops stretching.
Everything above floats. Everything below is submerged, gets darker the deeper it
sits, and shows how many months of budget away it is. Reorder the list and the
line moves — put something cheap first and two more things surface.

**Bought.** Press *Bought* on a row and its price comes off this month's budget,
which pushes the line up. The month's spending resets on the 1st.

## How the budget question is worked out

Between 5% and 10% of take-home pay, set by how much cushion is already in the
bank:

| Savings, measured in months of essentials | Starting rate |
| --- | --- |
| Under 1 month | 5% |
| 1 to 3 months | 6% |
| 3 to 6 months | 8% |
| Over 6 months | 10% |

Then: high-interest debt caps it at 5%; a big goal inside a year takes a point
off; and the whole thing is capped at half of whatever is left after essentials,
so a tight month can never produce a silly number. Rounded to the nearest 5.

It is a rule of thumb rather than financial advice, and the number is editable at
any point in Settings.

## Appearance

Jade, white and grey, with light and dark modes. Settings has a System, Light,
Dark switch; System follows whatever Chrome and your OS are doing. The on-page
panel follows the same setting.

## Where the data lives

In `chrome.storage.local`, on your machine. Nothing is sent anywhere and there is
no account. The on-page panel means the extension can read every page you visit,
so it is worth knowing that reading is all it does — page contents never leave
your browser.

## Files

| File | What it does |
| --- | --- |
| `manifest.json` | Manifest V3 config |
| `icons/` | The toolbar icon, with two alternates in `icons/alternates/` |
| `popup.html` / `popup.css` / `popup.js` | Everything you see and interact with |
| `extract.js` | Finds name, price and image on a page |
| `widget.js` | The on-page tab and slide-out panel |
| `background.js` | Right-click menu and the badge count |

## Worth knowing

- Price detection reads schema.org structured data first, then Open Graph tags,
  then scores visible price-like elements on the page. Most large retailers
  work. Anything unusual, type the price in.
- Prices are stored as plain numbers in one currency. Saving from a site in a
  different currency will not convert.

## Swapping the icon

Three designs ship with it. `icons/icon16.png`, `icon48.png` and `icon128.png` are
the ones in use. To switch, copy the three files out of `icons/alternates/option-b/`
or `option-c/` into `icons/`, overwriting what's there, then reload the extension
from `chrome://extensions`.
