# Installing Kubeflow Pipelines on OpenShift


## Prerequisites

## KFP on Tekton

Follow these [instructions](https://github.com/kubeflow/kfp-tekton/blob/master/guides/kfp-tekton-openshift.md)

```bash
export KFDEF_DIR=
mkdir -p ${KFDEF_DIR}
cd ${KFDEF_DIR}
export CONFIG_URI=https://raw.githubusercontent.com/IBM/KubeflowDojo/master/OpenShift/manifests/kfctl_tekton_openshift_minimal.v1.1.0.yaml
kfctl apply -V -f ${CONFIG_URI}
```

## KFP on Argo

https://github.com/kubeflow/manifests/blob/master/distributions/kfdef/kfctl_openshift.v1.2.0.yaml

## Smoke Test
export PATH=$PATH:/Users/jakang/Library/Python/3.8/bin

Add `dsl-compile-tekton` to your path

```bash
dsl-compile-tekton --py echo_pipeline.py --output pipeline.yaml
dsl-compile-tekton --py sequential.py --output sequential.tar.gz
```

Upload these to the KFP dashboard and execute