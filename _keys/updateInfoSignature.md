---
name: Secure Update Signature
key: updateInfoSignature
type: String
description: A digital signature for the update info.
available: 10
group: Updates

links:
  - top: /plist

---

Before begining an update Stacks will use the [Secure Update Public Key](../updateInfoPublicKey) to verify that the Secure Update Signature matches the [Secure Update Data](../updateInfo). This ensures that the data is unaltered from the data that you provided.  If stacks cannot verify the signature no request will be made.

Please see [Secure Updates](https://github.com/yourhead/s3/blob/master/secure_stack_API/README.md) document for more information.
