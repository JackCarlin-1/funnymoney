# Funny Money: zip 10 (balance fits beside the buttons)

New: a Subscriptions button above Wishlist. Add a subscription with a name, price per month and renewal date
(defaults to today). Each one has "Pay with funny money" (subtracts it from your balance and adds an expense)
and "Already paid" (marks it green without touching your balance). Paid ones turn green, move to the bottom,
and reset by themselves after the renewal date passes. Tap a subscription to edit, delete, or mark it unpaid.

## Update steps
1. Unzip. On github.com open your funnymoney repo > Add file > Upload files.
2. Drag in ALL the files from inside the unzipped folder (not the folder itself). They replace the old ones.
3. Click Commit changes. Vercel redeploys in about a minute.
4. Fully close the Home Screen app and reopen it (maybe twice) to load the new version.

No new Firestore rules are needed. If you have not yet published the wishlist-sharing rules from zip 8,
the Share button needs them (see the zip 8 README).
