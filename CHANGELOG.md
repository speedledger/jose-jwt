0.7.8
-----

* Switch from EitherT to ExceptT to allow compiling with latest version of 'either' package.

0.7.7
-----

* User ByteArray and ScrubbedBytes from memory package in preference to ByteString in internal crypto code.

0.7.6
-----

* Fixed exception when JWT contained invalid Base64 (issue #15).
* Add generateSymmetricKey utility function to Jwk module.

0.7.5
-----

* A JWT parser is now used to separate parsing and decoding into separate stages (internal change).

0.7.4
-----

* Stricter checking of AES key lengths when looking for a valid JWK to encode/decode an AES-KW JWT.

0.7.3
-----

* Add JSON test data to extra-source-files.

0.7.2
-----

* Remove test dependency on aeson-qq

0.7.1
-----

* Update cryptonite version to 0.19 to avoid security issues
* Fix broken benchmark code
* Better error message for invalid key length when using AES keywrap

0.7
---

* Add support for AES key wrap in JWEs.
* Support A192GCM and A192CBC-HS384 algorithms.
* Switch to cryptonite library.

0.6.2
-----

* Remove dependency on `errors` package.

0.6.1
-----

* Minor internal changes to fix build on GHC 7.10.

0.6
---

* Change KeyId type to allow use of a UTCTime string for the identifier.
* Internal crypto fixes to prevent exceptions from external libraries.

0.5
---

* Add JwtEncoding type. Changes API of `Jwt.encode` and `Jwt.decode`.

0.4.2
-----

* Fix in the code for finding suitable JWKs for encoding/decoding.

0.4.1.1
-------

* Added `doctest` flag to cabal file to allow doctests to be disabled.

0.4.1
-----

* Add cprng-aes dependency to doctests to stop test failure on travis and nixos hydra builds.

0.4
---

* Changed use of `Jwt` type to represent an encoded JWT.
* Introduced `Payload` type to allow setting the `cty` header value correctly for nested JWTs.
* Added an explicit `Unsecured` type for a decoded JWT, to make it obvious when the content is not signed or encrypted.
* Fixed some bugs in JSON encoding and decoding of EC JWKs.

0.3.1
-----

Changed the signature of `Jwt.encode` to take a list of `Jwk` rather than a single key. The key will be selected from
the list based on the specified algorithms.

0.3
---

* New support for JWS validation using elliptic curve algorithms.
* Added `Jwt.encode` function which takes a JWK argument, allowing key data (currently the key ID) to be encoded in the token header.
