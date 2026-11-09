# foxguard-keepwarm

Pings FoxGuard's public `/health` endpoint every 10 minutes so the Render free tier doesn't put it to sleep.

- No secrets, no checkout, no third-party actions. The job token has no permissions.
- One GET to `https://foxguard-api.onrender.com/health`. It always exits 0.
- **Off by default.** Turn it on or off with the repo variable `FOXGUARD_KEEPWARM` (`on` / `off`; unset means off):

```bash
gh variable set FOXGUARD_KEEPWARM --body on  -R SirDariusIsCoding/foxguard-keepwarm
gh variable set FOXGUARD_KEEPWARM --body off -R SirDariusIsCoding/foxguard-keepwarm
```

GitHub turns off scheduled workflows in a public repo after 60 days with no commits; re-enable it from the Actions tab if that happens.
