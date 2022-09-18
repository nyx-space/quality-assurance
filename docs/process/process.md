This process is heavily inspired by agile software development with a twist to accommodate space-related software. **For each version of the software, a number of requirements are chosen are these are worked until the next version is released.**

The overall quality assurance process can be broken down into these procedures. Click on the relevant sections in the table of contents to read the detail of each procedure. Note that a dotted line means it's an asynchronous process, enabling engineers to work on another task.

``` mermaid
graph TD
  A[[Requirements & <br/> test plans]] --> B[[Detailed design, <br/>incl. API & ICD]] --> C[[TDD: Tests and code  <br/>development]] -->D[[Final review & release]]
  D --> |Select requirements <br/> for next version| A

  click A "/process/requirements/"
  click B "/process/design/"
  click C "/process/development/"
  click D "/process/release/"
```

## Legend

### Engineer

An action or a decision performed by an engineer is highlighted in blue.

```mermaid
graph LR
    Dec{"Decision by<br/>engineer"}:::engr --> Act("Action by<br/>engineer"):::engr
    classDef engr fill:dodgerblue,opacity:0.6,stroke:navy,stroke-width:2px,color:black
```

### Lead or chief engineer

An action or a decision performed by the team lead or the chief engineer is highlighted in green.

```mermaid
graph LR
    Dec{"Decision<br/>by lead"}:::lead --> Act("Action<br/>by lead"):::lead
    classDef lead fill:green,opacity:0.6,stroke:darkgreen,stroke-width:2px,color:black
```

### Stakeholder

An action or a decision performed by a stakeholder is highlighted in orange.

```mermaid
graph LR
    Dec{"Decision by<br/>stakeholder"}:::sh --> Act("Action by<br/>stakeholder"):::sh
    classDef sh fill:orange,opacity:0.6,stroke:darkorange,stroke-width:2px,color:black
```