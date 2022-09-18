This process is heavily inspired by agile software development with a twist to accommodate space-related software. **For each version of the software, a number of requirements are chosen are these are worked until the next version is released.**

The overall quality assurance process can be broken down into these procedures. Click on the relevant sections in the table of contents to read the detail of each procedure. Note that a dotted line means it's an asynchronous process, freeing engineers to work on another task.

``` mermaid
graph TD
  A[[Requirements & <br/> test plans]] --> B[[Detailed design, <br/>incl. API & ICD]] --> C[[TDD: Tests and code  <br/>development]] -->D[[Final review & release]]
  D --> |Select requirements <br/> for next version| A

  click A "/process/requirements/"
  click B "/process/design/"
  click C "/process/development/"
  click D "/process/release/"
```
<hr/>

The full process diagram is below.

```mermaid
graph TD
    RN("Receive stakeholder needs"):::sh --> GR("Gather requirements"):::lead
    GR --> TP("Test plan development"):::engr
    TP --> ReqApproval{"Lead approval"}:::lead
    ReqApproval --> |Revision<br/>required| GR

    ReqApproval --> |Approved| AlgDemo("Algorithm demo"):::engr
    AlgDemo --> ApiIcd("API & ICD definition"):::engr
    ApiIcd --> PR1{"Peer review"}:::lead
    PR1 --> |Revision<br/>required| ApiIcd
    PR1 --> |Approved| DD(Detailed design):::engr
    DD --> PR2{"Peer review"}:::engr
    PR2 --> |Revision<br/>required| DD
    PR2 --> |Approved| LR1{"Lead Design<br/>Approval"}:::lead
    LR1 -.-> |Algorithm revision<br/>required| AlgDemo
    LR1 --> |API/ICD revision<br/>required| ApiIcd
    LR1 --> |Design revision<br/>required| DD

    LR1 --> |Approved| TDD("Tests development<br/>(TDD)"):::engr
    TDD --> PR3{"Peer review<br/> of tests"}:::engr
    PR3 --> |Revision<br/>required| TDD
    PR3 --> |Approved| CD(Code development):::engr
    CD --> PR4{"Code, unit, integr. <br/>review"}:::engr
    PR4 --> |Revision<br/>required| CD
    PR4 -.-> |Approved| LR2{"Lead review &<br/> Chief engr.<br/> sign-off"}:::lead
    PR4 -.-> |Requirement<br/>or design defect| LR3{"Defect<br/>identification"}:::lead
    LR3 -.-> |Design defect| AlgDemo
    LR3 --> |Requirement<br/>defect| GR
    LR2 -.-> |Revision<br/>required| TDD
    LR2 -.-> |Approved| C[[Release]]

    classDef lead fill:green,opacity:0.6,stroke:darkgreen,stroke-width:2px,color:black
    classDef engr fill:dodgerblue,opacity:0.6,stroke:navy,stroke-width:2px,color:black
    classDef sh fill:orange,opacity:0.6,stroke:darkorange,stroke-width:2px,color:black
```