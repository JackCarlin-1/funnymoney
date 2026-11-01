# Funny Money: zip 11

New since zip 10:
- Wishlist: star to prioritize an item (yellow highlight, moves to the top).
- Wishlist: fund items with 5%, 10% or a custom percent. The money comes out of your balance and is set aside.
  At 100% the item turns gold and shows Bought it! (moves it to Spent). Reset returns the money to your balance.
- Wishlist notes: links are clickable.
- Subscriptions page with Pay with funny money / Already paid.
- Subscriptions and Wishlist buttons now sit above Earned/Spent, so they never overlap the balance.

## Update steps
1. Unzip. On github.com open your funnymoney repo > Add file > Upload files.
2. Drag in ALL the files from inside the unzipped folder (not the folder itself). They replace the old ones.
3. Click Commit changes. Vercel redeploys in about a minute.
4. Fully close the Home Screen app and reopen it (maybe twice) to load the new version.

No new Firestore rules are needed beyond the sharing rules from zip 8.
