# Instructions to add new chart

1. `$ helm create helm-chart-name`

2. `$ helm lint helm-chart-name`
    > As a good habit, helm lint runs a series of tests to verify that the chart is well-formed

3. `$ helm package helm-chart-name/*`
    - This will create the package to publish helm chart

4. Create the Helm chart repository index.
    > A repository is characterized primarily by the presence of a special file called index.yaml that has a list of all of the packages supplied by the repository, together with metadata that allows retrieving and verifying those packages.
    > `$ helm repo index --url https://github.com/platformercloud/helm-charts/ .`

5. Push the git repository on GitHub
    > `$ git add . && git commit -m "commit note" && git push origin master`