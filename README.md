# Create and use an email on a custom domain name

- buy a domain name on [Cloudflare](https://cloudflare.com)
- create a free account of [Zoho mail](https://zohomail.com)
- in cloudflare:
  - enable `email routing`
  - add a `routing rule` that links an email on the custom domain, to the zoho mail previously created
  - now, you will be able to send email to `user@custom_domain.tldr` and they will reach your zoho email
  - [OPTIONAL] you can add a DMARC record in cloudflare (should help avoid emails being flagged as spam):
    - type: `TXT`
    - name: `_dmarc`
    - content: `v=DMARC1; p=none; rua=mailto:postmaster@<ZOHO_EMAIL_DOMAIN>` (use your zoho mail domain here)
- in zohomail:
  - in `settings`, `send email as`:
    - click `external from addresses`
    - choose `other` for a custom domain
    - choose a `display name` (whatever you want)
    - in `email address` insert the `user@custom_domain.tldr` email
    - in `choose the SMTP server` pick the `zoho server`
    - you will receive a confermation email through zoho (cloudflare already redirects emails to zoho!!!)

- DONE!!! YOU NOW CAN USE ZOHO MAIL TO BOTH RECEIVE AND SEND EMAIL FROM THAT CUSTOM DOMAIN. AS EASY AS THAT!
    
