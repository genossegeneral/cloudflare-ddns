# cloudflare DDNS python script

A tiny python script that updates a cloudflare dns record with your current ip.

You need to put an `.env` file into the `cloudflare-ddns` folder that looks like `.env-example`.

Run `make` to install dependecies.

You can then register a cronjob executing `ddns.sh` in an interval of choice.

## Env file

ZONE_ID: The Zone ID displayed on the domain info page in Cloudflare

RECORD_ID: Accessible through the Cloudflare API:

```
 curl -X GET "https://api.cloudflare.com/client/v4/zones/<ZONE_ID>/dns_records"      -H "Authorization: Bearer <API_KEY>"      -H "Content-Type:application/json"
```

RECORD_NAME: Accessible through the API

USER_EMAIL: Email of the cloudflare account

API_KEY: Actually an API token. Create one at https://dash.cloudflare.com/profile/api-tokens
