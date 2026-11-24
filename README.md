# Shopping List

One shopping list for everything: the supplies Household Diary says you're running low on, the products on Skin Diary's To buy list, the groceries for the meals you planned in Meal Planner, and anything you type in. A sister app to [Household Diary](https://github.com/nurnhe/household-diary), [Skin Diary](https://github.com/nurnhe/skin-diary) and [Meal Planner](https://github.com/nurnhe/meal-planner), with its own look: warm paper, deep teal and apricot, Bricolage Grotesque and Figtree.

**Use it as a phone app:** open https://nurnhe.github.io/shopping-list/ in Chrome on Android, then tap ⋮ → **Install app** (or **Add to Home screen**). It opens full screen with its own icon and works offline.

## How it connects

All the apps live on nurnhe.github.io, so they share the browser's storage on your phone. Shopping List reads the other apps' saved data directly; there are no accounts and nothing is sent anywhere.

- **Household Diary:** supplies marked "Running low" and items added to its shopping list. Ticking one off here marks it bought there, so it still learns how long things last. A **Running out soon** card shows supplies due to run out within 5 days, with **Add to list**. Supplies in the Personal care area go under Skin & personal care.
- **Skin Diary:** the To buy list. Ticking a restock puts the finished product back in use; ticking a new product puts it on your shelf (add it to your routine in Skin Diary).
- **Meal Planner:** the groceries for the meals planned from today to Sunday (or next week, in Settings), added up and grouped by aisle exactly like Meal Planner's own list. Ticking one ticks it there too.
- **Your own items:** type anything in the box at the top (separate several with commas). Category chips appear under the box with a guess already picked (from what you filed it under before, a built-in product list, and English and Serbian keywords); tap another chip to choose. Tap an item later to move it.
- **Suggestions while typing:** things you've bought or listed before (most used first), supplies and products from the other apps, and about 300 everyday products from Serbian shops with common sizes, like Coca-Cola Zero 1.5 l. Tap one, or use the arrow keys and Enter.
- **Your other apps:** cards at the bottom show chores due today, skincare products to replace and how much of the week is planned, and open each app.

- **Prices and quantities:** tap any item to set how many and the price each. The list shows each item's cost and an estimated total per group. The last price you paid for something is remembered and suggested next time (shown with ≈).
- **Spending:** the Spending tab totals what you bought each month by category (Household, Skin & personal care, Groceries, Other), with a bar for each, last month's total for comparison, and every purchase by day. Tap a category to see only its purchases, tap a purchase to fix its price, quantity or category, or add a purchase you made without the list. The currency (RSD by default) is in Settings.

Every tick has **Undo**, and **In the basket today** lists what you've bought. The share button copies or shares the whole list, grouped.

It only sees data saved by the installed apps on the same phone, not their Claude artifact versions.

## Files

- `shopping-list.html` is the page itself. Its ingredient reading and adding-up code is copied from Meal Planner so the totals match; if Meal Planner's shopping maths changes, copy it again.
- `build.py` wraps it into `index.html` with the app manifest and offline support. Run `python3 build.py` after editing `shopping-list.html`, and bump the cache name in `sw.js` on every change.
- `manifest.webmanifest`, `sw.js` and `icons/` make it installable and work offline.

## Data

The app's own items, prices, purchase history and settings are saved under `shopping-list-v1` in the browser's `localStorage`. The colour theme uses `nurnhe-theme`, shared with the other apps, so switching it in one switches them all.

## Credits

Icons are inlined SVG from [Tabler Icons](https://github.com/tabler/tabler-icons) (MIT License). Fonts: Bricolage Grotesque and Figtree, from Google Fonts (SIL Open Font License).
