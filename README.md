# MTA-STS Policy for Synkope

This repository hosts the MTA-STS (Mail Transfer Agent Strict Transport Security) policy for synkope.io.

## What is MTA-STS?

MTA-STS is a security standard that helps prevent man-in-the-middle attacks on email delivery by requiring TLS encryption.

## Deployment

This repository is deployed via GitHub Pages at: `https://mta-sts.synkope.io`

### DNS Configuration Required

1. **CNAME Record**: `mta-sts.synkope.io` → `synkope.github.io`
2. **TXT Record**: `_mta-sts.synkope.io` → `v=STSv1; id=20250110000000`

### Policy Details

The policy file is located at `/.well-known/mta-sts.txt` and specifies:
- Email delivery must use TLS encryption
- Valid mail servers for synkope.io
- Cache duration for the policy

## Testing

Test your MTA-STS configuration:
- [Hardenize](https://www.hardenize.com/)
- [MXToolbox MTA-STS](https://mxtoolbox.com/mta-sts.aspx)

## Updating the Policy

1. Edit `.well-known/mta-sts.txt`
2. Update the `id` in the DNS TXT record (use a new timestamp)
3. Commit and push changes

## More Information

- [RFC 8461 - MTA-STS](https://tools.ietf.org/html/rfc8461)
- [Google's MTA-STS Guide](https://support.google.com/a/answer/9261504)
