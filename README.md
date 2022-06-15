[![SourceGuard Code Analysis](https://github.com/chkp-ofirs/todo/actions/workflows/SourceGuard.yml/badge.svg)](https://github.com/chkp-ofirs/todo/actions/workflows/SourceGuard.yml)

# todo
 1. Download and install museum application https://chartmuseum.com/#Instructions
 2. Nevigate to the folder: cd todo
 3. Set my-sql password: set mysql-pass=Pwssword1!
 4. Verify helm chart: # helm --upgrade install --dry-run --set mysql-pass=%mysql-pass% --debug todo .
 5. Create helm chrt packge: # helm package .
 6. Start the museum application: # chartmuseum.exe --debug --port=8080 --storage local --storage-local-rootdir . 
 7. Upload pakcge to museum application: #  curl --data-binary "@todo-0.1.0.tgz" http://localhost:8080/api/charts
 8. Add the URL to your ChartMuseum installation to the local repository list: # helm repo add todo http://localhost:8080
 9. Update the repo: # helm repo update
 10. Search for charts: # helm search repo todo
 11. Install chart: # helm upgrade --install todo/todo --generate-name --atomic --set password=%mysqlpassword%
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
