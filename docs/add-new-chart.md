# Instructions to Add a New Chart

1. `$ git clone https://github.com/platformercloud/helm-charts.git && cd helm-charts`

2. `$ helm create <helm-chart-name>`

3. `$ helm lint <helm-chart-name>`
    > As a good habit, helm lint runs a series of tests to verify that the chart is well-formed

4. `$ helm package <helm-chart-name>/*`
    > This will create the package in order to publish the helm chart. e.g: helm-chart-name-0.1.0.tgz

5. `$ helm repo index --url https://github.com/platformercloud/helm-charts/ .`
    > Create the Helm chart repository index. A repository is characterized primarily by the presence of a special file called index.yaml that has a list of all of the packages supplied by the repository, together with metadata that allows retrieving and verifying those packages.

6. `$ git add . && git commit -m "commit note" && git push origin master`

* Note: Whenever you need to add a new chart to the Helm chart repository, it’s mandatory for you to regenerate the index.yaml file. The `$ helm repo index` command will completely rebuild the index.yaml file from scratch, including only the charts that it finds locally, which very likely is your case. However, it worth notice that you can use the --merge flag to incrementally add new charts to an existing index.yaml --> `$ helm repo index --url https://github.com/platformercloud/helm-charts/ --merge index.yaml .`