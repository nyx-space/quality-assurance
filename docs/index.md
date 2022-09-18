This website serves a documentation for the quality assurance process followed all Nyx tools, including Nyx itself, hifitime, and ANISE.

## Audience

This documentation is provided to help the reader gain confidence in the tools developed under the Nyx Space umbrella. It is a good read for would-be contributors to the software suite so they can understand the development process.

In fact, the process outlined here removes the need for a dedicated QA role: most of the quality is assured through automated processes and supplemental QA is done by every engineer in the team. **This process is designed to not get in the way of engineers**: most reviews are asynchronous enabling engineers the pick up the next requirement to work on. In the case of the Nyx tools, all of the roles are typically fulfilled by a single person, me[^1]: what's important is that I bring a critical to each review step.

## Ultimate objective

This QA policy provides an easily-understood, easily-audited development arc, tracing requirements through code, unit test, integration, and validation. I've followed a similar process for a number of space projects in the past few years. I'm publishing it under a Creative Commons license in hopes that the broader space community finds this useful and hopefully even proposes enhancements to the process.

More generally, this website provides a free-to-use quality assurance process for spacecraft applications, with a focus on GNC, FSW, and astrodynamics quality assurances. The quality assurance of GNC and FSW teams is often limited, typically because no one is assigned to [specific quality assurance roles](/summary/roles/). I hope this documentation can help teams write better and more tested software for space applications.

[^1]: Chris Rabotin

*[GNC]: Guidance, Navigation, and Control
*[FSW]: Flight Software
*[QA]: Quality Assurance