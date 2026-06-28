# GoalCoins: Fantasy Betting App

GoalCoins is a friends-only prediction and betting application built for fun and competitive engagement.

## Core Features
* **GoalCoins Currency:** Earn and wager virtual currency on football outcomes.
* **FriendBets:** Direct competition with friends with variable wager amounts.
* **WorldBets:** A risk-free, daily prediction mechanic to help users rebuild their balance (15 GC reward).
* **Secure Admin Portal:** Simplifies match result confirmation to automatically trigger settlement across all bets.

## Tech Stack
* **Database & Auth:** Google Firebase (Firestore + Authentication).
* **Backend Logic:** Firebase Cloud Functions (Node.js).
* **Data Source:** API-Football (Used for initial seeding to ensure data integrity/no typos).
* **Frontend:** Standard web/mobile framework with searchable player selection.

## Architecture
1.  **Authentication:** Firebase Auth (Email/Google).
2.  **State Management:** Real-time listeners on Firestore.
3.  **Settlement Engine:** Server-side Cloud Functions prevent client-side tampering.

## Getting Started
1.  **Seed Data:** Run the initial `seed_players.js` script to populate your `players_directory` collection from API-Football.
2.  **Environment:** Configure Firebase CLI and ensure Security Rules are active to restrict `admin` access.
3.  **Development:** Build the betting interface and verify balance updates through Firestore's realtime updates.
