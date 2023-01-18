## This folder contains files to help deal with postential issues or recreating sample applications, in case they are deleted.

*app-of-app.yaml*: We use ArgoCD's app-of-app paradigm to install all the sample applications. This can be manually done using: `kubectl -n opsmx-argo apply -f app-of-apps.yaml`

isdargo-autoconfig-job.yaml: During installation there is an autoconfiguration of Datasources along with other activities. In case this fails, one can delete the job and rexecute it as follows:
1. `kubectl -n opsmx-argo delete job oes-autoconfigure`
2. `Kubectl -n opsmx-argo apply -f https://raw.githubusercontent.com/OpsMx/isd-sample-apps/main/MISC/isdargo-autoconfig-job.yaml`

opsmxproject.yaml: All samples applications installed are in their own project called "opsmxproj". In case this is not created during installation, one can create it manuallu.
