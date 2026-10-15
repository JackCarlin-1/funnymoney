# Funny Money: zip 8 (wishlist sharing)

New in this version: a Share button on the Wishlist page that makes a read-only link you can send to anyone.
The link shows only your open wishlist items (name, price, note). No balance, no transactions, no sign-in needed.
It updates by itself when you change your wishlist, and you can turn it off any time.

## Update steps (do them in this order)

### 1. Publish the new Firestore rules (required, or Create link will fail)
Firebase console > Firestore Database > Rules tab. Replace everything with this, then click Publish:

    rules_version = '2';
    service cloud.firestore {
      match /databases/{database}/documents {
        match /users/{uid}/{document=**} {
          allow read, write: if request.auth != null && request.auth.uid == uid;
        }
        match /shared/{token} {
          allow get: if true;
          allow create: if request.auth != null
            && request.resource.data.uid == request.auth.uid
            && request.resource.data.items.size() <= 300;
          allow update: if request.auth != null
            && resource.data.uid == request.auth.uid
            && request.resource.data.uid == request.auth.uid
            && request.resource.data.items.size() <= 300;
          allow delete: if request.auth != null && resource.data.uid == request.auth.uid;
        }
      }
    }

Your private data is still locked to your account. The only new thing is that someone who has the exact long
link can read that one shared wishlist (nobody can browse or list them).

### 2. Upload the files to GitHub
Unzip, then in your repository use Add file > Upload files and drop in ALL the files from this zip
(index.html, share.html, sw.js and the rest). Replace the old ones. Commit changes. Vercel redeploys in about a minute.
Note share.html is new, and it must sit at the top level next to index.html.

### 3. Reopen the app
Fully close the Home Screen app (swipe it away) and open it again, maybe twice, so the new version loads.

### 4. Share
Wishlist page > Share > Create link > Copy link or Share... to send it.
"Stop sharing" deletes the shared copy and the old link stops working. Creating a new link later gives a new address.

## Good to know
- Notes on wishlist items are visible to people with the link, and web addresses in notes become tappable. Keep private notes off shared items.
- Items you mark as bought disappear from the shared list.
- Anyone you send the link to can forward it. Stop sharing if it spreads further than you want.
