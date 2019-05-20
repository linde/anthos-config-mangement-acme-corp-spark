# Custom Resource Definition and Custom Resource syncing example

this example has CRDs from the
[spark-on-k8s-operator](https://github.com/GoogleCloudPlatform/spark-on-k8s-operator)
which are in the [cluster](config-root/cluster/) directory and it instantiates a
spark operator resource using the
[spark-operator.yaml](config-root/namespaces/spark-operator/spark-operator.yaml)
which lives in a dedicated namespace,
[spark-operator](config-root/namespaces/spark-operator).

there is an example to show how the acme datascience team might set up jobs under
a [job directory](config-root/namespaces/datascience-team/jobs/) and have RBAC
configured automatically for respective subdirectories. the job there is based on the
[spark-pi-schedule.yaml](https://github.com/GoogleCloudPlatform/spark-on-k8s-operator/blob/master/examples/spark-pi-schedule.yaml)
example which runs a spark job every 5 minutes in the cluster.

this config set up works well with
[kind](https://github.com/kubernetes-sigs/kind) which uses docker not actual VMs
for pods. if you're using a real enviroment like GKE, be sure to watch resources
and in particular, CPUs. you might need more than default clusters provide
because spark is pretty core hungry.



