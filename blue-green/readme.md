### This repository has a sample app to showcase Blue Green deployments using Argo

#### A Blue Green Deployment allows users to reduce the amount of time multiple versions running at the same time.

In addition to managing ReplicaSets, the rollout controller will modify a Service resource during the BlueGreenUpdate strategy. The Rollout spec has users specify a reference to active service and optionally a preview service in the same namespace. The active Service is used to send regular application traffic to the old version, while the preview Service is used as funnel traffic to the new version.

When there is a change to the .spec.template field of a rollout, the controller will create the new ReplicaSet. If the active service is not sending traffic to a ReplicaSet, the controller will immediately start sending traffic to the ReplicaSet. Otherwise, the active service will point at the old ReplicaSet while the ReplicaSet becomes available. Once the new ReplicaSet becomes available, the controller will modify the active service to point at the new ReplicaSet. After waiting some time configured by the .spec.strategy.blueGreen.scaleDownDelaySeconds, the controller will scale down the old ReplicaSet.


For more details refer the following docs:

#### Argo official Document

https://argoproj.github.io/argo-rollouts/features/bluegreen/

#### This is an internal doc for OpsMx

https://docs.google.com/document/d/1w0JsZKbO7yO_WrZOjEd9MUMm9zIoUitsIpiGpVDSdq4/edit?usp=sharing
