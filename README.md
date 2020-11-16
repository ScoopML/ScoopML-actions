# ScoopML-actions
Github actions for ScoopML 

No Code Machine learning using github actions!!

Lets build AI models without coding inside repository

```

name: ScoopML Git Actions
on: 
  push :
    branches: [ master ]  
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: ScoopML Git Actions
        id: model
        uses: ScoopML/ScoopML-actions@automl
        with:
          DATASET: "juice"
          TARGET: "Purchase"
          USECASE: "classification"
      - name: Upload model.pkl
        uses: actions/upload-artifact@v2
        with: 
          name: model
          path: model.pkl
      - name: Upload exp_github_logs.csv
        uses: actions/upload-artifact@v2
        with: 
          name: experiment-logs
          path: exp_github_logs.csv
      - name: Upload logs.log
        uses: actions/upload-artifact@v2
        with: 
          name: system-logs
          path: logs.log
```
