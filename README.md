# tovartech-php-contact-form
this is a zip containing the contact form and php file for tovartech.org
I created the complete **TovarTech.org contact-form package** for you, using the same working Gmail SMTP approach as TovarBooks. It sends visitor messages directly to **[noetovar5@gmail.com](mailto:noetovar5@gmail.com)**, and I included the `php-mbstring` fix in the installer from the start.

[**Download TovarTech-Contact-Form.zip**](sandbox:/mnt/data/TovarTech-Contact-Form.zip)

The ZIP contains `contact.html`, `send-contact.php`, `setup-contact.sh`, `.htaccess`, a safe configuration example, and a detailed `README-FIRST.txt`. The new page uses the darker Tovar Tech enterprise look with blue/cyan technology accents, and the form includes technology-specific subjects such as **Linux / Red Hat, Windows Server, SQL Server, Cloud / Virtualization, Automation / Scripting, Training / Tutorial Questions, Business / Collaboration**, and more.

After uploading the contents with WinSCP into the same directory where your TovarTech `index.html` resides, SSH into the server and run:

```bash
cd /path/to/your/tovartech/web/root
sudo bash setup-contact.sh
```

It will install everything needed:

```text
PHP
php-mbstring
Apache PHP module
PHPMailer
```

Then it will ask for the Google App Password for:

```text
noetovar5@gmail.com
```

Since you're using the **same Gmail account as TovarBooks**, you can use the same valid Google App Password that is already working for your TovarBooks setup. You do **not** need to give that password to me.

The TovarTech credential is stored separately and securely here:

```bash
/etc/tovartech/contact-config.php
```

rather than inside your public web directory.

Once the installer finishes, open:

```text
https://tovartech.org/contact.html
```

and send yourself a test message. The email subject will look something like:

```text
[Tovar Tech Contact] Linux / Red Hat - John Smith
```

and when you click **Reply** in Gmail, it will reply directly to the visitor's email address.

One thing I noticed while checking the public site is that `tovartech.org` currently redirects outside visitors to a **Cloudflare Access login page**. ([TovarTech][1]) If that protection is intentional, that's perfectly fine, but visitors will need to pass Cloudflare Access before they can reach `contact.html`. If your goal is for **anyone on the internet** to be able to use the TovarTech contact form, we'll want to adjust the Cloudflare Access policy so `contact.html` and `send-contact.php` are publicly reachable while the protected parts of the site remain private.

[1]: https://tovartech.org/ "Sign in ・ Cloudflare Access"
