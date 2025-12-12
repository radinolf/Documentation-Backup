# Versions of the DACs API

### Version

DACs API versioning JS APIs have a 3-digits version syntax x.y.z, with a life cycle independent from the version of the DAC.

* **x:** removes deprecated api
* **y:** adds new APIs or introduces deprecations
* **z:** fix bug in the existing api - no changes in signatures.

**z** does not change the behaviours of the APIs, except for the buggy ones; y adds new functions or declare new deprecations, but do not change behaviours of the APIs; x might introduce breaking changes.

Updating from a version to the following patch or minor should be safe, no breaking changes should be introduced; updating to a major requires listing the change log to see if anything would break.

### Deprecation

API Deprecation are allowed with minor changes (y, at least): that is to say, no deprecation can be done in patch.

A deprecation must be documented and declare the major version in which will be removed.

A deprecated API can be removed in a major version only, and a major release of the JS API must come with the release of a new major of the DAC.

### Change Log

For each version update, there is a corresponding Change Log where all changes made are specified and explained in detail. This log provides a comprehensive record of the variations between versions, including resolved bugs, newly introduced features, and deprecated APIs. Additionally, it offers developers clear guidance on how the changes might affect their existing code and what actions they need to take to adapt to the new API versions.

The documentation regarding the Change Log of the DAC's APIs is available at the following link:

[API Changelog](https://dac-documentation-1.gitbook.io/dac-api)



<br>

<br>
