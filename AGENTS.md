# AI Development Agents & Workflow

This project utilizes a structured approach to manage development and data processing.

## 1. Data Architect Agent
* **Responsibility:** Manages the Firebase Firestore schema. Ensures consistency between `players_directory` (seeded from API-Football) and betting data.
* **Workflow:** Executes the initial seed script to pull team/player data from API-Football and performs monthly refresh cycles to capture transfers.

## 2. Admin Settlement Agent (Cloud Functions)
* **Responsibility:** Securely processes match results and distributes **GoalCoins**.
* **Workflow:** Triggered via the Admin Dashboard.
    * Validates user bets against the chosen match result.
    * Distributes winnings (Multipliers for FriendBets, flat 15 GC for WorldBets).
    * Updates the `balance` field in the `users` Firestore collection.

## 3. UI/UX Interaction Agent
* **Responsibility:** Manages the frontend experience (React/Mobile).
* **Workflow:**
    * Provides search/autocomplete functionality using the local Firestore `players_directory`.
    * Displays user `balance` in real-time.
    * Handles the "Bailout" notification logic when balance reaches 0 GC.
