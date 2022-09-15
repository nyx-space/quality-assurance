The overall quality assurance process can be broken down into these procedures, executed by different parties. Click on the relevant sections in the table of contents (on the left) to read the detail of each procedure.

``` mermaid
graph TD
  A[[Requirements & test plans]] --> B[[Detailed design, incl. API & ICD]] --> C[[Development via TDD]] --> D[[Unit and Integration Testing]] --> E[[Verif. and validation testing]] --> F[[Final review & sign-off]]
  F --> |Select requirements <br/> for next version| A
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