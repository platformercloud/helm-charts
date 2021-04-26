# Platformer Helm Charts

This repo publishes helm charts for Platformer Cloud.

### Prerequisites

* Helm 3.0+

### Steps to Install Charts

```
    1. $ helm repo add platformer https://platformercloud.github.io/helm-charts/
    2. $ helm search repo platformer # This will list down all the available charts e.g: platformer/sample-chart
    3. $ helm install sample-chart platformer/sample-chart
```
