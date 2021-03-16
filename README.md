# ASP-dotNET
Example ASP .NET application

This is an example showing how to containerize a Windows application and deploy it to OpenShift.

This is based on the Microsoft tutorial:

https://docs.microsoft.com/en-us/virtualization/windowscontainers/quick-start/building-sample-app

You can build the Windows container image on a Windows system but I found it works on a Mac as well.  In either case,
these are the steps:

docker build -t quay.io/tprinz/my-asp-app .

docker login https://quay.io
docker push quay.io/tprinz/my-asp-app:latest

oc new-project
oc create -f k8s-svc.yml

