CKAD
Install the bitnami/nginx Helm chart with the following specifications:
Set the number of deployment replicas to 3.
Use chart version 15.5.2.
Expose the service as NodePort with the external port set to 30007.
Provide the Helm command(s) you used and the output in q3-install.txt
Task 2: Upgrade the Release
Upgrade the Helm release deployed above to chart version 15.5.3 and apply the following changes:
Change the service type from NodePort to ClusterIP.
Provide the Helm command(s) you used and the output in q3-upgrade.txt
​
Q4:
You are tasked with creating a namespace and retrieving the service account token. Complete the following task:
Task:
Create a namespace named q4.
Extract the token for the default service account in the q4 namespace, decode it, and save the decoded output to a file named q4-token.txt.

Q5:
You are tasked with creating and configuring a Pod in a Kubernetes cluster. Complete the following steps:
Create a Pod named pod6 in the default namespace with the following specifications:
Use the image busybox:1.31.0.
Configure a readiness probe to execute the command cat /tmp/ready:
Set an initial delay of 5 seconds.
Set a period of 10 seconds.
The container should only be marked ready if the file /tmp/ready exists.
Ensure the Pod runs the following command when started:
touch /tmp/ready && sleep 1d
This command creates the file required for readiness and keeps the container idle.
Write the manifest file for this Pod to a file named q5-pod.yaml.
Deploy the Pod in the cluster and verify its creation.
Write the output of the kubectl describe command for the Pod to a file named q5-pod-describe.txt.
​
Q6:
You need to set up a cluster-internal Service and associated Pod. Complete the following tasks:
Create a ClusterIP Service named project-q6-svc in the q6 namespace with the following specifications:
The Service should expose the Pod created in step 2.
Configure the Service to redirect TCP traffic from port 3333 (Service port) to port 80 (Pod target port).
Save the manifest into q6-svc.yaml
Create a Pod named project-q6-api in the same namespace with the following specifications:
Use the image nginx:1.17.3-alpine.
Add the label project: q6-api to identify this Pod.
Save the manifest into q6-pod.yaml
Use a temporary Pod (e.g., nginx:alpine) to send a curl request to project-q6-svc and capture the response:
Save the response into q6/test.html
Verify the request logs in the project-q6-api Pod:
Save the logs into q6/service_test.log 
