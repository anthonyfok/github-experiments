This is an imitation, coded in [Mermaid](https://github.blog/2022-02-14-include-diagrams-markdown-files-mermaid/) in Markdown, of @DamonU2's original sequence diagram drawn with draw.io Desktop:

```mermaid
sequenceDiagram
    actor User
    participant User
    participant TakeSnapshot.py
    participant Finished
    participant FinishedMap.sh
    participant /_docs
    participant GitHub Pages
    Note over TakeSnapshot.py, /_docs: OpenDRR/earthquake-scenario repo
    Note over dsra-geopackages.yml: OpenDRR/opendrr-api repo
    User->>+Finished: add new scenario
    User->>+TakeSnapshot.py: run
    TakeSnapshot.py-->>-Finished: scenario .md<br>and map .png
    User->>+FinishedMap.sh: run
    FinishedMap.sh->>+/_docs: dsra.yml updated
    /_docs->>-GitHub Pages: pages updated
    FinishedMap.sh-->>-Finished: FinishedScenarios.md,<br>FinishedScenario.geojson,<br>and scenario.csv updated
    User->>+dsra-geopackages.yml: run
    dsra-geopackages.yml-->>-Finished: geopackage generated
    deactivate Finished
```

Source code:

    ```mermaid
    sequenceDiagram
        actor User
        participant User
        participant TakeSnapshot.py
        participant Finished
        participant FinishedMap.sh
        participant /_docs
        participant GitHub Pages
        Note over TakeSnapshot.py, /_docs: OpenDRR/earthquake-scenario repo
        Note over dsra-geopackages.yml: OpenDRR/opendrr-api repo
        User->>+Finished: add new scenario
        User->>+TakeSnapshot.py: run
        TakeSnapshot.py-->>-Finished: scenario .md<br>and map .png
        User->>+FinishedMap.sh: run
        FinishedMap.sh->>+/_docs: dsra.yml updated
        /_docs->>-GitHub Pages: pages updated
        FinishedMap.sh-->>-Finished: FinishedScenarios.md,<br>FinishedScenario.geojson, <br>and scenario.csv updated
        User->>+dsra-geopackages.yml: run
        dsra-geopackages.yml-->>-Finished: geopackage generated
        deactivate Finished
    ```

There are several things that I can't quite yet reproduce...
