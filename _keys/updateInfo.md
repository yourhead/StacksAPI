---
name: Secure Update Data
key: updateInfo
type: string (JSON format)
description: Any data in JSON format.
available: 10
group: Updates

links:
  - top: /plist

---

Before begining an update Stacks will use the [Secure Update Public Key](../updateInfoPublicKey) to verify that the [Secure Update Signature](../updateInfoSignature) matches the Secure Update Data. This ensures that the data is unaltered from the data that you provided.  If stacks cannot verify the signature no request will be made.

The data can contain any information that you like. It should be a valid JSON dictionary object.

Please see [Secure Updates](https://github.com/yourhead/s3/blob/master/secure_stack_API/README.md) document for more information.