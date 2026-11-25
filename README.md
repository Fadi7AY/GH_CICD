# GitHub Actions · Docker publishing lab

A Flask greeting app on port **3000**, paired with a GitHub Actions exercise.


```mermaid
flowchart LR
    N0["Push"]
    N1["Docker Hub login"]
    N2["Build lab11:latest"]
    N3["Push image"]
    N0 --> N1 --> N2 --> N3
```


## Run the app locally

```bash
python3 -m pip install -r requirements.txt
python3 app.py
```

Open [localhost:3000](http://localhost:3000).

## Workflow behavior

The workflow runs on pushes. It needs repository variable `DOCKERHUB_USERNAME` and secret `DOCKERHUB_TOKEN`, and publishes `<DOCKERHUB_USERNAME>/lab11:latest`.

| File | Purpose |
| --- | --- |
| [app.py](app.py) | Flask route for GET /. |
| [test_app.py](test_app.py) | Application test source. |
| [Dockerfile](Dockerfile) | Container definition. |
| [.github/workflows/lab11.yaml](.github/workflows/lab11.yaml) | Checked-in workflow. |
