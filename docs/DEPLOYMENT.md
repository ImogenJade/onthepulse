# Deployment

## [ASAP] Create a Hosted Zone and get DNS to point at it

ℹ️ This could take up to 72 hours, so it's better to get it done asap. Although, sometimes 1 hour will do.

1. Go to Route53 and manually create a Hosted Zone. Two records will get created out of the box. Take note of the nameservers.
1. In Namecheap.com, add the nameservers (CustomDNS) to point to the recently created hosted zone.
1. Also take note of the HostedZone Id. This will be needed for the production deployment step.

Tip: You can monitor the progress of this with these commands:

```sh
dig example.com any
# or:
nslookup example.com
```

## Temp deployment

Meant for when the domain name is not available yet. The bucket name can be set in `deploy/parameters.json`.

```sh
auto/create-stack
```

## Production deployment (with domain name)

1. Update the file `deploy/parameters.json` with the `HostedZoneId` and domain name. Then run:

   ```sh
   auto/create-acm-certificate
   ```

   Take note of the ACM ARN.

1. Update the file `deploy/parameters.json` with the `CertificateArn` and then run:

   ```sh
   auto/update-stack
   ```

## Regular deployment

New changes to main will trigger a new deployment as part of CI:

```sh
auto/deploy
```
