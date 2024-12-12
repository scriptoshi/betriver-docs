---
description: >-
  While the software could theorectically run on shared hosting , we don't
  advice it for production, since a few things will not work out of the box
---

# Cpanel/Plesk installation

### KNOWN ISSUES ON SHARED HOSTING.

1. The software require the laravel artisan queue worker to be monitored and running. It can be challenging to set this up on shared hosting since you need sudo privileges to setup supervisord.  If you have sudo privileges , you add the command , _**(see the end of the page for more**_). to your supervisord conf.
2. Like the queue:worker above laravel reverb needs to be monitored and run. Fortunately you can replace reverb for pusher.com since its a drop in subsitute.

### Betriver maintains a strict standard Laravel folder structure. This makes it easy for any laravel developer to customize, update or modify the software.

### Directory Structure

* **Pre Built CSS Files:** `/../public/assets/css`
* **Source code CSS Files:** `/../resources/css`
* **Source code Js Files**`/../resources/js`
* **Pre Built JavaScript Files:** `/../public/assets/js`
* **Pre Built Fonts, images, components:** `/../public/assets/`

&#x20;All Dependencies and  assets have been installed  built and exported, unless you need to make changes to the source code, you don’t have to install or update anything.\
[**Learn more about Laravel**](https://laravel.com/docs/)

### 1. Create a Database

Create a fresh database, choose `utf8mb4_general_ci` character encoding and add a user to the database, then grant this user all permissions to that database. Note the **database name**, **username**, and **password**.  It will be needed during installation

### 2. Unzip and upload server files

Extract the file you downloaded. In the extracted directory find **betriver-server.zip,** upload this to the root folder of your domain. Extract the contents of **betriver-server.zip** here.

### 3. **Change Your Document Root**

* Go back to cPanel main page
* Look for "Domain" or "Domains" section
* Click on "Domains" or "Domain Manager"
* Find your domain and click "Manage" or the gear/settings icon
* Look for "Document Root" or "Directory"
* Add `/public` to the end of your current path
* Example: If current path is `/home/username/public_html`, change it to `/home/username/public_html/public`
* Save changes

**Alternative Method** (if above option isn't available):

* Contact your hosting provider
* Ask them to change the document root to point to the `/public` folder inside the uploaded files.

**Important Notes:**

* This change may take a few minutes to take effect
* Make sure all your Betriver files are properly uploaded before making this change
* If your site shows errors, double-check the path is correct

### 3. Run the installer.

Visit your site in the browser. The installer should load. &#x20;

Follow the instructions on the screen.

<figure><img src="../../.gitbook/assets/Screenshot 2024-11-06 at 10.19.08 PM.png" alt="Betn installerr welcome screen" width="563"><figcaption><p>Installer Step 1</p></figcaption></figure>

#### The installer will check if your system meets some minimum requirements 

<figure><img src="../../.gitbook/assets/Screenshot 2024-11-06 at 10.19.26 PM.png" alt="Betn System Requirements" width="563"><figcaption><p>System Requirements</p></figcaption></figure>

#### If all is fine, the installer will verify if your folder permissions are fine. Ensure that storage  and cache are writeable before proceeding.

<figure><img src="../../.gitbook/assets/Screenshot 2024-11-06 at 10.19.36 PM.png" alt="Betn folder permissions setup" width="563"><figcaption><p>Folder permissions</p></figcaption></figure>

#### Next the installer will require your Database settings. 

<figure><img src="../../.gitbook/assets/Screenshot 2024-11-06 at 10.20.24 PM.png" alt="" width="563"><figcaption></figcaption></figure>

Here are some common settings for MySQL.\


```properties
MySQL
Database_HOST=localhost
Database_PORT=3306
```



#### Once You configure database. The site should be ready to go.

<figure><img src="../../.gitbook/assets/Screenshot 2024-11-07 at 3.31.55 AM.png" alt="" width="563"><figcaption></figcaption></figure>

Start and wait for migrations. (there are no SQL files)\


<figure><img src="../../.gitbook/assets/Screenshot 2024-11-07 at 3.31.16 AM.png" alt="" width="563"><figcaption></figcaption></figure>

#### Finally Click Complete installation, to update final configurations.

<figure><img src="../../.gitbook/assets/Screenshot 2024-11-07 at 3.31.43 AM.png" alt="" width="563"><figcaption></figcaption></figure>

\


## Setting up Laravel Scheduler Cron Job in cPanel



#### 1. Find Your Project Path

First, determine the full path to your Laravel project. Typically, it will be something like:

```
/home/username/public_html/your-project
```

You can verify this by connecting via SSH or using cPanel's File Manager.

#### 2. Access Cron Jobs in cPanel

1. Log into your cPanel account
2. Scroll down to the "Advanced" section
3. Click on "Cron Jobs" or "Cronjobs"

#### 3. Configure the Cron Job

In the "Add New Cron Job" section:

**Common Settings**

* Set the frequency to run every minute:
  * Select \* for minute
  * Select \* for hour
  * Select \* for day
  * Select \* for month
  * Select \* for weekday

**Command to Add**

Use one of these commands based on your setup:

**Option 1: Using PHP from system path:**

```bash
php /home/username/public_html/your-project/artisan schedule:run >> /dev/null 2>&1
```

**Option 2: Using specific PHP version (recommended):**

```bash
/usr/local/bin/php /home/username/public_html/your-project/artisan schedule:run >> /dev/null 2>&1
```

**Option 3: Using `cd` command (if path issues occur):**

```bash
cd /home/username/public_html/your-project && php artisan schedule:run >> /dev/null 2>&1
```

### Monitor the cron settings.

* Regularly check cron job status in cPanel
* Monitor Laravel logs for scheduled task execution
* Update command paths if you move your application





## Process workers.

Running Laravel's queue worker on shared hosting presents unique challenges since you typically don't have access to supervisor or system-level services. This guide presents several approaches to run and monitor a queue worker within these limitations.

### Understanding the Challenges

1. Shared hosting limitations:
   * No access to Supervisor
   * Limited background process control
   * Resource restrictions
   * Process lifetime limitations
   * Potential random process termination

### Approach 1: Cron-Based Queue Processing

This approach runs the queue worker periodically through cron jobs. While not ideal, it's often the most reliable method on shared hosting.

#### Basic Setup

1. After uploading the extracted files, Find the included shell script `process_queue.sh` in your project root folder.&#x20;
2. Login via ssh and make the file executable . Make the script executable: (Can be skipped on some web hosts.)

```bash
chmod +x process_queue.sh
```

3. Add a cron job in cPanel:

```bash
* * * * * /home/username/public_html/your-project/process_queue.sh >> /dev/null 2>&1
```





### Alternative Approaches to running the queue worker.

#### 1. Using Database Queue Driver

If your hosting provider restricts background processes, consider using the database queue driver with frequent cron execution:

1. Configure `.env`:

```
QUEUE_CONNECTION=database
```

2. Create jobs table:

```bash
php artisan queue:table
php artisan migrate
```

3. Create a more frequent cron job:

```bash
* * * * * php /path/to/artisan queue:work --stop-when-empty --max-time=58
```

#### 2. Using Redis (if available)

Some shared hosts provide Redis. If available:

1. Install predis:

```bash
composer require predis/predis
```

2. Configure `.env`:

```
QUEUE_CONNECTION=redis
REDIS_CLIENT=predis
```



## WEBSOCKETS

Betriver comes with a websoket setup using laravel reverb. but like the queue:worker, you need to run an monitor the command reverb:start. SO set in the same way  you setup your websockets above only replace this queue:work with reverb:start. EG

```
* * * * * php /path/to/artisan reverb:start --stop-when-empty --max-time=58
```



