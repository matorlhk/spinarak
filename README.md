# Spinarak, a semi-automated booking bot for Tokyo's Pokemon Cafe

## What it'll do:
1. Regularly check for days with open slots. This is controlled by a GitHub Action
2. If a day with availability is found, an email is sent to you with the booking link

You still have to manually complete the last step in the booking process. For this reason, I highly recommend having push notifcations enabled on your phone email app. This way you can click the reservation link that gets automatically emailed to you ASAP.

Spinarak uses Selenium WebDriver to get around the Pokemon Cafe's site anti-automation controls. You won't be able to easily parse the server responses using curl or similar.

For fun, Spinarak stores hits and misses under the `/hits/` and `/nodice/` directories of the repo.


## How to set Spinarak up
1. Fork this repo
2. Create [Gmail app password](https://myaccount.google.com/apppasswords)
3. Store your GMail settings as GitHub Action secrets on your own repo as follows:
  - `GMAIL_APP_PW`
  - `GMAIL_RECIPIENT`
  - `GMAIL_RECIPIENT_2`
  - `GMAIL_SENDER`
4. Update the `cron` line on `spinarak.yml` to suit your needs. The more frequent the action runs, the more likely Spinarak will find an open slot

Please note that you may go above your free GitHub Actions minutes which means you'll be billed.

If everything goes well, you'll book your slot and get to meet Pikachu just like we did!

https://github.com/user-attachments/assets/8a33b716-2799-4efc-826d-a184892d3b1a