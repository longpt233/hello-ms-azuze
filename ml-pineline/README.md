1. tạo componient 
- ws -> designer
- data set output: azureml://subscriptions/cf6f3ea0-456d-4109-a97c-e363fab3fa53/resourcegroups/default-group/workspaces/long-ws/datastores/workspaceblobstore/paths/UI/2023-11-27_155732_UTC/Salary_dataset.csv
- split data
- model 
- train
- score
- evaluate

2. nối pineline 
- chỉnh split data 0.8
- trỉnh label colume train model 
[](./asset/pineline.png)

3. submit

[](./asset/submit.png)

- kết quả: job -> experient

[](./asset/ketqua.png)

- metric 
[](./asset/metric.png)

4. publish

