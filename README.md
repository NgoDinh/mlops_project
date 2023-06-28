## FLOW
`project based on hands-on bootcamp of MLOps course on udemy, I just follow step by step to understand how a end to end ML project organized`
dagshub link: https://dagshub.com/vu93.ngo/final_project
### Setup
- Step 0: Prepare environment, folder structure, install lib, prepare config file
### Trainning
- Step 1: Build processing step (training.src.process) -> get data from raw folder (data.raw) and return in processed folder (data.processed)
- Step 2: Train model (hyperopt need another section to learn about this lib, in this project we can skip some confused point and focus to flow first) then save to bentoml repo
- Step 3: evaluate and using dagshub to log experiment. (trainning.src.helper -> defind function to log, trainning.src.evaluate_model -> evaluate and log result)
- Step 4: consolidate in main function (trainning.src.main)
### Testing
- Step 5: Test processing function with pytest, to be update: test model (training.test)
### Create service
- Step 6: Load model bentoml model repo (application.src.create_service)
- Step 7: Build bento and docker (bentoml build )
- Step 8: Push image to azure (note when build by Mac m1 include option `--opt platform=linux/amd64`)
- Step 9: Build streamlit app from above API
----
- New libraries:
    - partial functions: https://www.geeksforgeeks.org/partial-functions-python/
    - pandera: https://pandera.readthedocs.io/en/stable/
- Libraries need to learn more:
    - hyperopt