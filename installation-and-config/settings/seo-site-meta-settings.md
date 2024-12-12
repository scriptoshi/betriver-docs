---
icon: sitemap
---

# SEO Site Meta Settings

<figure><img src="../../.gitbook/assets/-Betriver (2).jpg" alt=""><figcaption></figcaption></figure>

The Site Meta page allows you to configure SEO meta tags for your website. It has the following key sections:

Meta Tags:

* This section shows the meta tags that will be rendered on all pages of the site, except for game pages.
* It includes fields for tracking total games, total bets, and site settings app name.

Site Generation Settings:

* This section allows you to configure how the site sitemap is generated.
* You can set the number of leagues and games to include in the sitemap.
* There are buttons to generate the sitemap and delete the current sitemap.

Games Listing Page:

* This section configures the meta tags for the games listing pages.
* It includes fields for total games, total bets, and total winnings.

Show Game Details Page:

* This section configures the meta tags for the individual game details pages.
* It includes fields for the game name, kickoff time, and site settings app name.

To update the site meta settings, fill out the relevant fields and click the "Save Meta Settings" button at the bottom of the page.

The inputs support using variables shown above them, that will be replaced with actual values when rendering the meta data: Eg writing : "Bet on over :games\_count games today " will render  "Bet on over 60 games today"

* `:games_count` - The Total Number of games pending
* `:total_bets` - The Total Number of bets placed so far
* `:wins` - The Total amount of winnings distributed so far
* `:appname` - Site Settings App Name

You can include these variables  and they will be substituted with the appropriate data.
