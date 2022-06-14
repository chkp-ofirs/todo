# todo
 Download and install museum application https://chartmuseum.com/#Instructions
 Verify helm chart: # helm install --dry-run --debug . --generate-name
 Create helm chrt packge: # helm package .
 Start the museum application: # chartmuseum.exe --storage local --storage-local-rootdir . 
 Upload pakcge to museum application: #  curl --data-binary "@todo-0.1.0.tgz" http://localhost:8080/api/charts
 Add the URL to your ChartMuseum installation to the local repository list: # helm repo add todo http://localhost:8080
 Search for charts: # helm search repo todo
 Install chart: # helm install todo/todo --generate-name
 
 Expected Results:
	NAME: todo-1655217341
	LAST DEPLOYED: Tue Jun 14 17:35:42 2022
	NAMESPACE: default
	STATUS: deployed
	REVISION: 1
	NOTES:
	1. Get the application URL by running these commands:
	  export NODE_PORT=$(kubectl get --namespace default -o jsonpath="{.spec.ports[0].nodePort}" services todo-1655217341)
	  export NODE_IP=$(kubectl get nodes --namespace default -o jsonpath="{.items[0].status.addresses[0].address}")
	  echo http://$NODE_IP:$NODE_PORT


