---
description: >-
  This guide explains how to enable and configure social login settings for your
  platform, allowing users to authenticate using their Google, GitHub, or
  Facebook accounts.
icon: left-from-bracket
---

# Social Login Configuration Guide

<figure><img src="../../.gitbook/assets/Screenshot 2024-11-22 at 8.46.20 AM.png" alt=""><figcaption></figcaption></figure>

***

**Overview**

Social login allows users to log in quickly using their existing social media accounts. This feature can be toggled on or off for each provider. The `.env` values will override settings entered here.

***

#### Providers Supported

1. **Google One Tap**
2. **GitHub**
3. **Facebook**

***

#### Configuration Fields

**1. Google One Tap Settings**

[**https://console.cloud.google.com/apis/credentials/consent**](https://console.cloud.google.com/apis/credentials/consent)

* **Google Client ID**: Enter the Client ID from your Google Cloud Console.
* **Google Client Secret**: Enter the Client Secret associated with your Google project.
* **Google Project ID (Optional)**: Provide the Project ID for additional context or use.

To activate Google login, toggle the **Google Active** button.

***

**2. GitHub Login Settings**

[**https://github.com/settings/developers**](https://github.com/settings/developers)

* **GitHub Client ID**: Enter the Client ID from your GitHub Developer Settings.
* **GitHub Client Secret**: Provide the Client Secret associated with the GitHub application.
* **GitHub Redirect URL**: The callback URL for GitHub authentication. Example: `http://localhost/callback/github`.

To activate GitHub login, toggle the **GitHub Active** button.

***

**3. Facebook Login Settings**

* **Facebook Client ID**: Enter the Client ID from your Facebook App Dashboard.
* **Facebook Client Secret**: Provide the Client Secret associated with your Facebook app.
* **Facebook Redirect URL**: The callback URL for Facebook authentication. Example: `http://localhost/callback/facebook`.

To activate Facebook login, toggle the **Facebook Active** button.

***

#### Steps to Configure Social Login

1. **Enable the Provider**: Toggle the corresponding switch (e.g., Google Active, GitHub Active, or Facebook Active).
2. **Fill Out the Fields**:
   * Obtain the necessary credentials (Client ID, Client Secret, Redirect URL) from the respective provider's developer portal.
   * Enter these details in the relevant fields.
3. **Save Settings**: Click the "Save \[Provider] Settings" button to apply changes.

***

#### Notes

* Ensure the redirect URLs match those configured in the provider’s developer portal to avoid authentication errors.
* If `.env` variables are set for any provider, they will take precedence over the values entered here.

***

#### Troubleshooting

* **Invalid Credentials**: Double-check your Client ID and Client Secret for typos or errors.
* **Redirect Mismatch**: Ensure the redirect URL in your settings matches the one configured in the provider's dashboard.
* **Provider Not Working**: Verify that the Active toggle for the provider is enabled.

***

Would you like to add more information, such as links to the provider setup guides or screenshots?
