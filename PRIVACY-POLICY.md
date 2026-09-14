# Privacy Policy — Wishlist

_Last updated: [DATE]_

## The short version

Wishlist stores everything on your own computer and sends nothing anywhere.
There is no account, no server, no analytics, and no third parties.

## What the extension stores

All of it lives in `chrome.storage.local` on your device:

- The monthly budget you set, and your chosen currency and appearance setting.
- If you use the budget questions: your answers (take-home pay, essential costs,
  savings, whether you carry high-interest debt, and what you are saving toward).
  These are used once to calculate a suggested figure and are kept only so the
  questions can be re-opened with your previous answers.
- The items you save: page title, price, product image URL, page URL, and the
  date you saved it.
- Items you mark as bought, with their price and date, for the current month.
- Domains where you have chosen to hide the on-page panel.

## What the extension reads

When you open the popup or the on-page panel, Wishlist reads the current page to
find a product name, price, and image. It looks at structured product data,
page metadata, and visible price text.

That reading happens in your browser and the result is only used to fill in the
save form. Page content is never transmitted, logged, or stored except for the
specific fields listed above, and only for pages where you press Save.

## How this maps to the Chrome Web Store disclosures

The store listing declares three data categories. Each is stored on your device
only:

- **Financial information** — the optional budget questions ask for take-home
  pay, essential monthly costs, savings, and whether you carry high-interest
  debt. Kept so the questions reopen with your previous answers. No payment
  methods or card details are ever involved.
- **Web history** — saved and purchased items are recorded as a page URL, title
  and date. Only pages you explicitly save. General browsing is never logged.
- **Website content** — the product name, price and image read from a page to
  fill in the save form.

## What is never collected

- No browsing history.
- No form contents, passwords, payment details, or personal identifiers.
- No analytics, telemetry, crash reporting, or advertising identifiers.
- No data is sold, shared, or transferred to anyone, for any purpose.

## Permissions and why they exist

| Permission | Why |
| --- | --- |
| `storage` | To save your budget and list on your device. |
| `activeTab` | To read the page you are on when you open the popup. |
| `scripting` | To run the product-detection code on that page. |
| `contextMenus` | To add the right-click "Save to Wishlist" item. |
| Access to all websites | The on-page panel appears on any site you shop on. Shopping happens on thousands of domains, so the panel cannot be limited to a fixed list without failing on most of them. |

## Removing your data

Settings → Erase everything deletes the lot. Uninstalling the extension also
removes all stored data. Since nothing is held anywhere else, that is the end of it.

## Contact

[YOUR EMAIL]
