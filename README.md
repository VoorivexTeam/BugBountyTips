# **Bug Bounty Tips**

## Authentication Class
- **Account Takeover via Same Key in Different Regions** [[original tweet](https://x.com/_jensec/status/1292846852010721280), [our analysis](./Authentication/shared-secret-key/README.md)].
  - Sign up for an account in the EU region with `victim@gmail.com`
  - Log in, grab the JWT token or session
  - Use this token/session in the **US region** to see if it works
- **Email Verification Bypass via Token Binds to User not the Email** [[original tweet](https://x.com/Jayesh25_/status/1725429962931335599), [our analysis](https://github.com/VoorivexTeam/white-box-challenges/tree/main/email-verification-bypass)]
  - Log in to your attacker account and change your email address to an attacker-controlled email (e.g., `attacker@gmail.com`).
  - You’ll receive a confirmation email but **don’t verify** it yet
  - Change your email to the unregistered email or domain you wish to HIJACK (e.g., `victim@gmail.com`)
  - Click the confirmation link sent earlier to `attacker@gmail.com`. If the system hasn’t revoked it, this link could verify `victim@gmail.com`
- **Account Takeover via OAuth Scope Manipulation** [[original tweet](https://x.com/intigriti/status/1158383750490800128), [our analysis](./Authentication/oauth-scope/README.md)].
  - Go to the OAuth provider's authorization page.
  - Remove `email` from the scope in the URL.
  - See what happens!
