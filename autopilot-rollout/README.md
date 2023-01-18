This is an example for running on rollouts on a quick-installed ISD (isd-prom): https://github.com/OpsMx/isd-ap-quick-install/tree/main/isd-argo-prom
This requires ISD (ArgoCD and rollouts), prometheus and a test application, all of which are provided here.

To try this out, follow these steps
1. If not autocreated, Create application: kubectl -n opsmx-argo apply -f app-autopilot-rollout.yaml 
2. Wait for 2-3 minutes for the application to stabilize
3. Trigger analysis from the application screen by a) Disabling Auto-Sync b) Editing the Rollout object and bumping the the test image "issuegen:v3.0.4" version to v3.0.5, save and come out.
4. Once the triggered, AnalysisRun will start and a job with Pod is created. Check the logs to see the analysis in progress. If there are any errors, please see our troubleshooting guide
5. You can see the "More" tab on Rollout object screen or Go ISD home screen, click on "autopilot-rollout" -> Analysis Hostory to see the analysis results


The files are as follows:
1. autopilot-rollout.yaml is the Rollouts YAML
2. prometheus-verifier.yaml and elast-verlfider.yaml define the metrics and logs we want to monitor
3. local-alysis-tmpl.yaml is Rollouts Analysis template
4. local-provider-config.yaml file provides configuration for OpsMx Autopilot configuration
5. the folder "one-time" includes files that need to be applied only once per namespace such as serviceAccount, profile, etc.
6. the folder "load" includes an additional service and a job that loads the test application using jmeter. Users can use their own methods for loading their applications 
 
