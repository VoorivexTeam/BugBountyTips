# BugBountyTips


## Authentication Class
- Account takeover: Using the same key in various regions [[original tweet](https://x.com/_jensec/status/1292846852010721280), [our analysis](./Authentication/shared-secret-key/README.md)].
    - Sign up in the **EU region** with `victim@gmail.com`
    - Sign in to the account, grab the JWT token or session, use it in the **US region**
- Email verification bypass: token is bound to the user not the email [[original tweet](https://x.com/Jayesh25_/status/1725429962931335599), [our analysis](/email-verification-bypass)]
    - Log in to your attacker account and change your email address to an attacker-controlled email (e.g., `attacker@gmail.com`).
    - You'll likely receive an email confirmation link on your attacker-controlled email (Do not verify it yet)
    - Change your email to the unregistered email or domain you wish to HIJACK (e.g., `victim@gmail.com`)
    - This action will send an email verification link to `victim@gmail.com`, which you don't have access to
    - Try clicking on the "Email" verification link sent earlier to `attacker@gmail.com`. If the system fails to revoke the previous email verification link, the link for `attacker@gmail.com`.com could end up verifying the email for `victim@gmail.com`, allowing you to claim it as verified