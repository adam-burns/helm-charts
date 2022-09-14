PROJECT := helm-charts

cluster-up:
	k3d cluster create mycluster2 --port "8000:80@loadbalancer" --agents 4 --wait --timeout 120s

cluster-down:
	k3d cluster delete mycluster2

zenflows-up:
	helm install interfacer zenflows
	kubectl get nodes -o jsonpath="{.items[0].status.addresses[0].address}"

zenflows-down:
	helm delete zenflows

todo-up:
	helm install todo mychart
	kubectl get nodes -o jsonpath="{.items[0].status.addresses[0].address}"

todo-down:
	helm delete todo
