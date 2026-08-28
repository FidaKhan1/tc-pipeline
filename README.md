# Tax Calculator DevOps Final Project

This public repository contains the Tekton resources used to build and test the Tax Calculator application.

## Assignment files

- `tasks.yaml`: the starter cleanup task plus the new `npm` and `jasmine` task definitions.
- `pipeline.yaml`: the `tc-pipeline` definition with `npminstall`, `tests`, and `build` tasks in order.
- `run.yaml`: the `PipelineRun` definition with the required parameters and workspace binding.
- `pvc.yaml`: the persistent workspace claim.
- `serviceaccount.yaml`: the service account used to push the image to IBM Cloud Container Registry.

## Apply the resources

```bash
kubectl apply -f pvc.yaml
kubectl apply -f serviceaccount.yaml
kubectl apply -f tasks.yaml
kubectl apply -f pipeline.yaml
kubectl create -f run.yaml
```

The PipelineRun builds the `v2` branch of the course Tax Calculator repository. Before running it in Skills Network, confirm that the registry namespace in `run.yaml` matches the output of:

```bash
echo "$SN_ICR_NAMESPACE"
```
