# steps to install Kubernetes on Azure container Services
- Clone Azure ACS repo [https://github.com/Azure/acs-engine](https://github.com/Azure/acs-engine)
- Install ACS engine: [https://github.com/Azure/acs-engine/blob/master/docs/acsengine.md](https://github.com/Azure/acs-engine/blob/master/docs/acsengine.md)
- Update the cluster definition to your needs(Add Subnets, disk sizes, network policies etc.) [https://github.com/Azure/acs-engine/blob/master/examples/vnet/kubernetesvnet1.6.json](https://github.com/Azure/acs-engine/blob/master/examples/vnet/kubernetesvnet1.6.json). For details refer cluster definition options [https://github.com/Azure/acs-engine/blob/master/docs/clusterdefinition.md](https://github.com/Azure/acs-engine/blob/master/docs/clusterdefinition.md)
- Generate the ARM templates (not necessary, only for debugging purposes) 
    - `acs-engine generate ./kubernetesvnet1.6.json –location <<location>> –subscription-id <<sub-id>> –resource-group <<k8-rg-name>>`
- Deploy the cluster 
    - `acs-engine deploy ./kubernetesvnet1.6.json –location <<location>> –subscription-id <<sub-id>> –resource-group <<k8-rg-name>>`
- Kubernetes cluster in ACS reference architecture ![https://github.com/Azure/acs-engine/blob/master/docs/images/kubernetes.png](https://github.com/Azure/acs-engine/blob/master/docs/images/kubernetes.png)
- Next steps: [https://github.com/Azure/acs-engine/blob/master/docs/kubernetes/walkthrough.md](https://github.com/Azure/acs-engine/blob/master/docs/kubernetes/walkthrough.md)