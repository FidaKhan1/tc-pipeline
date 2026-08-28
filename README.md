# Tax Calculator DevOps Final Project

This public repository contains the Tekton resources required by Questions 7–9 of the Tax Calculator final project.

## Assignment files

- `tasks.yaml`: the cleanup task plus the new `npm` and `jasmine` task definitions.
- `pipeline.yaml`: the `tc-pipeline` definition with `npminstall`, `tests`, and `build` tasks.
- `run.yaml`: the `PipelineRun` definition with the required repository, branch, application name, PVC workspace, and Docker registry secret workspace.
- `pvc.yaml`: the persistent workspace claim.

The build image is generated as:

```text
us.icr.io/$(context.pipelineRun.namespace)/$(params.app-name)
```

This avoids hard-coding a learner-specific IBM Cloud Registry namespace.
