The version number is incredibly important as any stakeholder should be able to point precisely to the version being used and there should be no ambiguity as to what documentation and code is being referenced.

For utmost clarity, Semantic Versioning is strongly recommended. A version has three numbers `major.minor.patch`, e.g. `1.3.37` means that there has been `1` major release, `3` minor releases and `37` pull requests merged since version `1.3.0`. Every iteration of the process should trigger a new `minor` release. After a given iteration, the software _and_ API/ICD should have either a new minor version or a new major version, and the patch number shall be set to zero.

New projects should start at version `0.1.0` until the API and ICD is stabilized enough for the software to be used in a production environment.[^1] As per [the SemVer guidelines](https://semver.org/#faq), any _breaking change_ to the public API or ICD should lead to a new major release once version `1.0.0` has been reached.[^2]

!!! tip
    To ensure uniqueness, just after the code review approval and just before merging into the main branch, the last commit on each pull request should be a version update.

## Release notes

At a minimum, the release notes should provide a link to the latest documentation. At best, these release notes should include the link to all of the issues that were tackled in a given process iteration and should be stored in a `CHANGELOG.md` file.

[^1]: Here, "used in a production environment" is defined as the software can be used as a black box while producing results useful to the stakeholder.
[^2]: Exceptions can be made to this if there is a unique stakeholder and they have been made aware that the upcoming minor version change will require use of the updated ICD.

*[SemVer]: Semantic Versioning