# Excess Cost Approval Process Flow


```mermaid
graph TD
    A[Start: Request for Excess Cost Approval] --> B{1) Is the procedure lifesaving?};

    B -- No --> C{2) What is the current functional limitation?};
    B -- Yes --> D{Is the prognosis after the procedure fair?};

    D -- Yes --> E[Approve];
    D -- No --> F[Reject.];
    subgraph Footnote_1_Example
        F -- "Example: no life support after brain death; no ICU in end stage cancer" --> G[End];
    end

    C -- "None or mild" --> F;
    C -- "Moderate or Severe" --> H{3) At what degree ADL are impaired?};
    subgraph Footnote_2_Assessment
        C -- "Assessment supported by: i. Detailed specialist report; ii. IOM physician’s examination; iii. Observation by IOM staff (incl. unannounced/casual observations by CHC)." --> G_placeholder_2;
    end

    H -- "Not at all or mild" --> F;
    H -- "Moderate to Severe" --> I{Is it a Diagnostic Procedure?};
    subgraph Footnote_3_Remark
        H -- "Remark: Not all conditions requiring intervention affect ADL. Applies only to conditions affecting mobility, mental health, development and sensory (vision, hearing) sphere. Observations of the staff (medical and non-medical) and CHC should be the main supporting evidence for this question." --> G_placeholder_3;
    end

    I -- Yes (Diagnostic) --> J{4) Has the procedure been done before?};
    I -- No (Treatment) --> S{6a) For treatment: Is the treatment indicated?};

    J -- No --> K{5) Is the result likely to impact the treatment?};
    J -- Yes --> L{Record: how many times, last time, why repeat.};
    L --> M{4a) Is there a significant worsening of the condition?};
    subgraph Footnote_4_RepeatInfo
        L -- "Footnote: Record: how many times, when was the last time and why it needs to be repeated." --> G_placeholder_4;
    end

    M -- No --> F;
    M -- Yes --> K;

    K -- Yes --> P[Approve provisionally.];
    K -- No --> F;
    subgraph Footnote_5_Example
        K -- "Example: MRI is unlikely to provide information that would change management of a child with microcephaly." --> G_placeholder_5;
    end
    P --> Q{7) Does the cost appear standard for the type and level of care?};

    S -- No --> F;
    S -- Yes --> T{6b) Does the proposed treatment follow standards of care for a given condition and its severity?};

    T -- No --> U[Reject or seek further clarifications];
    T -- Yes --> V{6c) What are the consequences of NOT administering this treatment?};

    V -- "Decreased life expectancy, significant complications, requiring more expensive treatment, loss of organ or function affecting ADL, impairment of schooling or ability to work" --> W{6d) Is there a simpler and cheaper treatment?};
    V -- "None of the above" --> F;

    W -- Yes --> X{6e) What are the disadvantages of alternative treatment compared with the proposed one?};
    W -- No --> E_approve;

    X -- "None or some inconvenience" --> Y[Reject the proposed treatment and offer the alternative one];
    X -- "Significantly less effective" --> P_provisional;

    Q -- Yes --> Z[Approve definitively];
    Q -- No --> AA[Seek clarification,
