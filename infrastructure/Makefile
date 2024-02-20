.PHONY: apply
apply:
	terraform apply -auto-approve

.PHONY: destroy
destroy:
	terraform state list | grep helm_release | xargs -I terraform state rm
	terraform state list | grep kubectl_manifest | xargs -I terraform state rm
	terraform destroy -auto-approve
	sleep 10
	doctl compute volume list | grep -v ID | awk '{print $$1}' | xargs -I doctl compute volume delete --force

PHONY: save-kubeconfig
save-kubeconfig:
	terraform output -raw kubeconfig > kubeconfig.yaml
	mv kubeconfig.yaml ../demos/
	git add ../demos/kubeconfig.yaml
	git commit -m "chore: bump kubeconfig [auto]"
	git push
