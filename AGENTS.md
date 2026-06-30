# AI Development Agents & Workflow

## 1. Data Architect Agent
* **Responsibility:** Manages the Firestore schema. 
* **Workflow:** Maintains `players_directory`, `users`, and the `bets` collection (which now includes a 'status' field: `pending`, `accepted`, `rejected`, `completed`).

## 2. Admin Settlement Agent (Cloud Functions)
* **Responsibility:** Securely processes match results and distributes **GoalCoins**.
* **Workflow:** Triggered after match conclusion. Validates results against the `bets` collection (filtering for `status: accepted`) and updates user balances.

## 3. UI/UX Interaction Agent
* **Responsibility:** Manages the frontend experience (React/Mobile).
* **Workflow:**
    * **Challenge Engine:** Handles the logic for sending bet requests and displaying the (User/Amount/Choice/Subject) pop-up.
    * **Real-time Listeners:** Uses Firestore snapshots to immediately notify the recipient of a new "Bet Request."
    * **Bailout System:** Handles the "WorldBets" tab for risk-free GC recovery.
