PROJECT := helm-charts

cluster-up:
	k3d cluster create mycluster2 -p "8081:80@loadbalancer" --agents 4 --wait --timeout 120s

cluster-down:
	k3d cluster delete mycluster2

todo-up:
	helm install todo mychart
	kubectl get nodes -o jsonpath="{.items[0].status.addresses[0].address}"

todo-down:
	helm delete todo
