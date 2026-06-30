# GoalCoins: Fantasy Betting App

GoalCoins is a friends-only prediction and betting application built for fun and competitive engagement.

## Core Features
* **GoalCoins Currency:** Earn and wager virtual currency on football outcomes.
* **FriendBets (P2P Challenges):** Users send direct "Bet Requests" to friends. Requests appear as pop-ups with (Amount, Choice, Subject) and require an ACCEPT/DECLINE action to finalize.
* **WorldBets:** A risk-free, daily prediction mechanic to help users rebuild their balance (15 GC reward).
* **Secure Admin Portal:** Simplifies match result confirmation to automatically trigger settlement across all bets.

## Tech Stack
* **Database & Auth:** Google Firebase (Firestore + Authentication).
* **Backend Logic:** Firebase Cloud Functions (Node.js).
* **Data Source:** API-Football (Used for initial seeding to ensure data integrity/no typos).
* **Frontend:** Standard web/mobile framework with searchable player selection.

## Architecture
1.  **Authentication:** Firebase Auth (Email/Google).
2.  **Challenge System:** Peer-to-peer requests stored as 'pending_bets' in Firestore with listener-based notifications.
3.  **Settlement Engine:** Server-side Cloud Functions prevent client-side tampering and process results.

## Getting Started
1.  **Seed Data:** Run the initial `seed_players.js` script to populate your `players_directory` collection.
2.  **Environment:** Configure Firebase CLI and ensure Security Rules are active.
3.  **Development:** Build the challenge UI (Request -> Accept/Decline -> Active Bet).
