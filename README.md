[![SourceGuard Code Analysis](https://github.com/chkp-ofirs/todo/actions/workflows/SourceGuard.yml/badge.svg)](https://github.com/chkp-ofirs/todo/actions/workflows/SourceGuard.yml)
[![upload-artifact](https://github.com/chkp-ofirs/todo/actions/workflows/upload-artifact.yml/badge.svg)](https://github.com/chkp-ofirs/todo/actions/workflows/upload-artifact.yml)

# todo
 1. Download and install museum application https://chartmuseum.com/#Instructions
 2. Nevigate to the folder: cd todo
 3. Build dependency # helm dependency build
 4. Update dependencies : # helm dependencies update
 3. Verify helm chart: # helm install --dry-run --debug . --generate-name
 4. Create helm chrt packge: # helm package .
 5. Start the museum application: # chartmuseum.exe --debug --port=8080 --storage local --storage-local-rootdir . 
 6. Upload pakcge to museum application: #  curl --data-binary "@todo-0.1.0.tgz" http://localhost:8080/api/charts
 7. Add the URL to your ChartMuseum installation to the local repository list: # helm repo add todo http://localhost:8080
 8. Update the repo: # helm repo update
 9. Search for charts: # helm search repo todo
 10. Install chart: # helm install todo/todo --generate-name
 # Expected Results:
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


# YAML to HelmChart
  cat wordpress-deployment.yaml  | helmify wordpress-deployment
