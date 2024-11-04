# Logic Order of Processing

``` mermaid
graph TD 
    A[Start Game/Reset Game] --> G1;
    subgraph G1[Global];
        B([Initialise]);
    end;
    G1 --> S;
    subgraph S[For Each Screen];
        SA([Initialise]);
    end;
    S --> R;
    subgraph R[For Each Room];
        direction LR;
        RA([Initialise]) --> RO;
        subgraph RO[For Each Room Object];
            RB([Initialise]);
        end;
    end;
    R --> G2;
    subgraph G2[For Each Global Object];
        C([Initialise]);
    end;
    G2 --> FR;
    subgraph FR[Each Frame];
        subgraph G3[Global];
            E([Always]);
        end;
        subgraph CS[Current Screen];
            F([Always]);
        end;
        subgraph CR[Current Room];
            G([Always]);
            subgraph RO2[For Each Room Object];
                H([Always]);
            end;
            G --> RO2;
        end;
        subgraph GO[For Each Global Object];
            J([Always]);
        end;
        G3 --> CS;
        CS --> CR;
        CR --> GO;
    end;
```
