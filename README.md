[![SourceGuard Code Analysis](https://github.com/chkp-ofirs/todo/actions/workflows/SourceGuard.yml/badge.svg)](https://github.com/chkp-ofirs/todo/actions/workflows/SourceGuard.yml) [![upload-artifact](https://github.com/chkp-ofirs/todo/actions/workflows/upload-artifact.yml/badge.svg)](https://github.com/chkp-ofirs/todo/actions/workflows/upload-artifact.yml)

# todo
 1. Download and install museum application https://chartmuseum.com/#Instructions
 2. Nevigate to the folder: cd todo
 4. Set my-sql password: mysqlpassword="0DnoUK8Xqlym5JzBCHPItSobKmVI20IrZdu27Uy9kwI="
 5. Verify helm chart: # helm upgrade todo . --install --dry-run --debug --set MYSQL_ROOT_PASSWORD=%mysqlpassword%
 6. Create helm chrt packge: # helm package .
 7. Start the museum application: # chartmuseum.exe --debug --port=8080 --storage local --storage-local-rootdir . 
 8. Upload pakcge to museum application: #  curl --data-binary "@todo-0.1.0.tgz" http://localhost:8080/api/charts
 9. Add the URL to your ChartMuseum installation to the local repository list: # helm repo add todo http://localhost:8080
 10. Update the repo: # helm repo update
 11. Search for charts: # helm search repo todo
 12. Install chart: # helm upgrade --install todo/todo --generate-name --set MYSQL_ROOT_PASSWORD=%mysqlpassword%
 # Expected Results:
	NAME: todo
	LAST DEPLOYED: Wed Jun 15 13:52:04 2022
	NAMESPACE: default
	STATUS: deployed
	REVISION: 1
	NOTES:
	You have deployed the following release: todo.
	1.To get further information, you can run the commands:
	  $ helm status todo
	  $ helm get all todo
	2. Get the application URL by running these commands:
	  export NODE_PORT=$(kubectl get --namespace default -o jsonpath="{.spec.ports[0].nodePort}" services todo)
	  export NODE_IP=$(kubectl get nodes --namespace default -o jsonpath="{.items[0].status.addresses[0].address}")
	  echo http://$NODE_IP:$NODE_PORT
