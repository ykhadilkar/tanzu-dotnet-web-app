# Tanzu .NET Web App

This is a sample .NET [Steeltoe](https://steeltoe.io/) app that works with Tilt and the Tanzu Application Platform.

## Prerequisites

* A Kubernetes cluster with [Tanzu Application Platform](https://docs.vmware.com/en/VMware-Tanzu-Application-Platform/index.html) installed
* Your client machine must have the [Tanzu CLI](https://docs.vmware.com/en/Tanzu-Application-Platform/1.0/tap/GUID-install-tanzu-cli.html)

## Deploy and Run

You can use either command below to deploy the application:

### With Tests
```
tanzu apps workload create tanzu-dotnet-web-app \
--git-repo https://github.com/fjb4/tanzu-dotnet-web-app \
--git-branch master \
--type web \
--label app.kubernetes.io/part-of=tanzu-dotnet-web-app \
--label tanzu.app.live.view=true \
--label tanzu.app.live.view.application.flavours=steeltoe \
--label tanzu.app.live.view.application.name=tanzu-dotnet-web-app \
--label apps.tanzu.vmware.com/has-tests=true

tanzu apps workload create tanzu-dotnet-web-app -f ./config/workload.yaml --yes
```
Without test / scan pipeline
```
tanzu apps workload create tanzu-dotnet-web-app \
--git-repo https://github.com/fjb4/tanzu-dotnet-web-app \
--git-branch master \
--type web \
--label app.kubernetes.io/part-of=tanzu-dotnet-web-app \
--label tanzu.app.live.view=true \
--label tanzu.app.live.view.application.flavours=steeltoe \
--label tanzu.app.live.view.application.name=tanzu-dotnet-web-app \

```


## Register Application Accelerator Template

`tanzu accelerator create tanzu-dotnet-web-app --git-repository https://github.com/fjb4/tanzu-dotnet-web-app --git-branch master`

