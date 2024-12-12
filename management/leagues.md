---
description: >-
  This guide explains how to manage football leagues in the Betriver Admin
  Panel, covering enabling/disabling leagues, loading games and odds, and
  customizing league settings for frontend display.
icon: user-ninja
---

# Leagues

***

### Accessing the Leagues Management Page

<figure><img src="../.gitbook/assets/Screenshot 2024-11-24 at 5.44.49 AM.png" alt=""><figcaption></figcaption></figure>

1. Navigate to the **Leagues** section in the sidebar menu.
2. Select the specific sport (e.g., **Football**) to view its leagues.

***

### Features Overview

#### 1. **Enable/Disable Leagues**

* Toggle the **Active** switch to enable or disable a league.
  * **Enabled**: Games within the league are visible and operational for users.
  * **Disabled**: All existing games in the league are deactivated. New games from the API will not be loaded for this league.
* To manage multiple leagues quickly:
  * Use the **Enable All** or **Disable All** buttons at the top.

***

#### 2. **Loading Games from the API**

* Click the **Load from API** button to fetch new games for active leagues.
* Ensure the league is **Active** to allow loading of new games.

***

#### 3. **Odds Management**

The Green Odds Icon indicates that the api has Odds for the league. The **Has Odds** toggle can you filter only league that have odds available from the API.

<figure><img src="../.gitbook/assets/Screenshot 2024-11-24 at 5.45.16 AM.png" alt=""><figcaption></figcaption></figure>

* Odds are only necessary if:
  * You have enabled **bookie-based bets** (users betting against the admin).
* To load odds for a league:
  1. Click the **Odds** button next to the league name.
  2. The system will fetch odds data from the API for available games in the league.

***

#### 4. **Submenu Configuration**

* The **Submenu** toggle determines whether the league is displayed as a menu item in the frontend sidebar.
* Enable this option if:
  * The league is popular.
  * You want to promote or highlight a specific league.

***

#### 5. **Country and Search Filters**

* Use the **Select a Country** dropdown to filter leagues by region.
* The **Search** bar allows you to quickly find leagues by name.

***

### Best Practices

1. **Limit Active Leagues**:
   * Keep only 10-50 leagues active to optimize API costs.
2. **Enable Submenus Sparingly**:
   * Use this feature only for high-profile leagues to avoid cluttering the frontend sidebar.
3. **Load Odds Only When Necessary**:
   * Skip loading odds if bookie-based bets are disabled in your platform.

***

### Example Workflow

1. **Set Up a New League manually**
   * Click the **New League** button to add a league manually.
2. **Or Load the list of available leagues for the sport from api**:
   * Click **Load from API** to fetch leagues.
   * Toggle **Active** to enable or disable the league.
3. **Enable Odds**:
   * Ensure bookie-based bets are active.
   * Load odds using the **Odds** button.
4. **Display League in Sidebar**:
   * Toggle **Submenu** to showcase the league on the frontend sidebar.

***
