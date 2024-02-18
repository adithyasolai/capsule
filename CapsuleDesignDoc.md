## Capsule Design

_Owner: Adithya Solai_

___

**One Liner:** Capsule is a low-cost personal storage service with just a few features.

___

## Executive Summary

The market aim is to siphon customers of popular personal storage services (Google One, Apple iCloud, Dropbox, etc) that really just want to park their data somewhere in the cloud and never look at it again until they really need to.

The business model is a subscription model that is **never tiered** and sets a storage limit that accurately divides reasonable personal storage use from enterprise needs. The subscription fee will have to be a bare minimum margin on infrastructure costs to compete. Money can be made if the majority of customers only use well below the average expected storage that served as an input for the subscription price.

___

## Existing Products

- pCloud offers 2 TB for a one-time payment of $400 that lasts a lifetime. They offer only infrequent access like this business idea. They also offer 10 TB for a one-time payment of $1200. **pCloud invalidates the Capsule business idea.**
  - https://www.pcloud.com/lifetime/

**All of these products also offer immediate retrieval of data, unlike the S3 Glacier plans I mention below.**

- Microsoft Office 365 Personal offers 1 TB for $5.83/month **while also including all other Microsoft products like Word, Powerpoint, etc.**
- Apple iCloud offers 2 TB for $11.99/month. However, this integrates well with their walled garden of products, which is where the value-add comes from.
- Google offers 2 TB for $8.30/month via Google One. Google One doesn't have too many extra important features, but they are including Gemini Advanced (AI) with this tier of Google One soon. Not really relevant to this business study, however.
- Dropbox offers 2 TB for $10/month.
- Box offers 100 GB for $10/month. But they emphasize file sharing/collaboration. It's not just a vault.

## Calculations & Conclusion

For all subscription plans, there will be a limit of 2 TB as a reasonable stopping point for personal use cases. That is what the market currently seems to limit at as well. Plans in the market for above 2 TB are typically marketed as family plans or enterprise plans.

### AWS S3

From https://aws.amazon.com/s3/pricing/:
>Amazon S3 storage usage is calculated in binary gigabytes (GB), where 1 GB is 2^30 bytes. This unit of measurement is also known as a gibibyte (GiB), defined by the International Electrotechnical Commission (IEC). Similarly, 1 TB is 2^40 bytes, i.e. 1024 GBs.

- AWS S3 charges $0.004/GB/month for S3 Glacier Instant Retrieval 
  - For long-lived archive data accessed once a quarter with instant retrieval in milliseconds.
  - If S3 Glacier Instant Retrieval is used, it would cost `$8.19200/customer/month` to support 2 TB.
- AWS S3 charges $0.0036/GB/month for S3 Glacier Flexible Retrieval 
  - For long-term backups and archives with retrieval option from 1 minute to 12 hours.
  - If S3 Glacier Flexible Retrieval is used, it would cost `$7.3728/customer/month` to support 2 TB.
- AWS S3 charges $0.00099/GB/month for S3 Glacier Deep Archive
  - For long-term data archiving that is accessed once or twice in a year and can be restored within 12 hours.
  - If S3 Glacier Deep Archive is used, it would cost `$2.02752/customer/month` to support 2 TB.

___