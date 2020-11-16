# ScoopML-actions
Github actions for ScoopML 

No Code Machine learning using github actions!!

Lets build AI models without coding inside repository
# Lets get Started

Copy paste the below code in a .yml script inside a target repository and click on start commit and then actions
```

name: ScoopML Git Actions
on: 
  push :
    branches: [ main ]  
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: ScoopML Git Actions
        id: model
        uses: ScoopML/ScoopML-actions@1.0
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
