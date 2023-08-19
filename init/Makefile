crossplane:
	helm repo add crossplane-stable https://charts.crossplane.io/stable
	helm install crossplane crossplane-stable/crossplane --namespace crossplane-system --create-namespace

external-secrets:
	helm repo add external-secrets https://charts.external-secrets.io
	helm install external-secrets external-secrets/external-secrets -n external-secrets --create-namespace

install: external-secrets crossplane
	kubectl apply -f providers.yaml
	kubectl apply -f provider-config.yml
	./fix-provider-kubernetes-perms.sh
