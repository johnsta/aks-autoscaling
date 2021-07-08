# Azure Voting App
This repo is based on the AKS tutorial where this code is packaged into container images, uploaded to Azure Container Registry, and then run in and AKS cluster, see the [AKS tutorials](https://docs.microsoft.com/en-us/azure/aks/tutorial-kubernetes-prepare-app?WT.mc_id=none-github-nepeters).

Note: 'deploy-script.azcli` was authored to *manually* run commands (sometimes, manual steps are required - these are called out in the script's comments).

# Verify autoscale
1. Edit `minReplicas` and `maxReplicas` in [azure-vote-hpa.yaml](azure-vote-hpa.yaml).
2. Apply changes to AKS cluster configuration: `kubectl apply -f azure-vote-hpa.yaml`
3. Run JMeter test: [get-votes.jmx](load/get-votes.jmx)
4. Watch auto-scaling status: `kubectl get hpa --watch`