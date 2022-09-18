Once all of the requirements for a given iteration have been developed, tested, and reviewed, the lead should create a dedicated branch for the _freeze_. The purpose of the freeze is to test what cannot be automatically tested in the CI pipeline, such as hardware integration testing, and allow time for the team to provide bug fixes for the upcoming release. No new features should be allowed onto the dedicated freeze branch. The lead and the chief engineer are also to review that the process has been followed correctly throughout this release.

!!! note
    If this is purely a software project where all of the tests are automated and run every time, as is the case with Nyx, then a dedicated _freeze_ branch is not required.

## Lessons learned

If there was any rejection at the _lead review_ decision points, learned lessons must be captured as described here.

Supporting continuous improvement requires closed-loop capture of specific lessons learned by each member of the team. This is akin to the _retrospective_ of a SCRUM process. Any insight learned about a better way to do something is considered a lesson. Formally identifying and sharing these lessons has a long-term effect on the quality of the software. Lessons shall outline the problem encountered and the recommended solution.

## Versioning

Along with a new software version, a new detailed design version shall be published, preferably with the same version number, cf. the [versioning guidelines](/guidelines/versioning/). The release notes should point to each revision of the documentation and the code.

## Defects

Software is provided as-is after the chief engineer sign-off. If any defects are later identified, these shall lead to return to the "Stakeholder need" phase of the process as it will necessarily lead to an update of either the requirements, the detailed design, or the tests, or a combination thereof.