# Nomad Cheatsheet

A collection of cheatsheets for getting started with [Nomad](https://github.com/hashicorp/nomad)! 



## Motivation

Learning new tools can be difficult at first, so we wanted curate and collect a series of cheatseheets to help you get started with Nomad. Since kubernetes is popular in the container orchestration world, we felt that the first couple cheat sheets should be focused on nomad commands and concepts from a kubernetes perspective. If you'd like to add to our existing cheatsheets or make new ones, see the [contributing](##Contributing) section below.




## Kubernetes -> Nomad Command cheatsheet 






| What the command does                                                                                                                | Kubernetes                                                                  | Nomad                                                                                                                                                                                        |
| ------------------------------------------------------------------------------------------------------------------------------------ | --------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Print the logs for a container in a pod or specified resource. If the pod has only one container,<br>the container name is optional. | kubectl logs pod\_identifier                                                | nomad alloc logs {allocID}                                                                                                                                                                   |
| Get high fidelity information about a cluster resource                                                                               | kubectl describe {resource} {resourceId}                                    | nomad status {resourceID}                                                                                                                                                                    |
| Create a resource                                                                                                                    | kubectl {create \| apply} -f {file}                                          | nomad job run {file}                                                                                                                                                                         |
| Stop a resource                                                                                                                      | kubectl destroy {resource}                                                  | nomad job stop -purge                                                                                                                                                                        |
| Forward a port locally to your machine                                                                                               | kubectl port-forward {options}                                              | [Unimplemented – More information here:<br>](https://github.com/hashicorp/nomad/issues/6925)[https://github.com/hashicorp/nomad/issues/6925](https://github.com/hashicorp/nomad/issues/6925) |
| View the machines running in the cluster                                                                                             | kubectl get nodes                                                           | nomad node status                                                                                                                                                                            |
| View the running instances of compute                                                                                                | kubectl get pods                                                            | Jobs: nomad status<br>Allocs: nomad status {jobID}                                                                                                                                           |
| View the documentation for objects                                                                                                   | kubectl explain {resource}                                                  | Unimplemented                                                                                                                                                                                |
| Edit any API resource in your preferred editor.                                                                                      | kubectl edit {resource}                                                     | Unimplemented in CLI.<br>UI has job editing (JSON only)                                                                                                                                      |
| Create example workload                                                                                                              |                                                                             | nomad job init                                                                                                                                                                               |
| Open UI for object                                                                                                                   | No Kubernetes equivalent (Kubernetes Dashboard is not a guaranteed install) | nomad ui {some ID}                                                                                                                                                                           |






## Kubernetes -> Nomad Concepts Cheatsheet





| Kubernetes  | Nomad                                        |
| ----------- | -------------------------------------------- |
| Daemon set  | System Job                                   |
| Replica set | Service Job                                  |
| Pod         | Allocation                                   |
| kubelet     | Client Agent (or just “Client”)              |
| Node        | Node (or sometimes “Client” as they map 1:1) |
| Job         | Batch Job                                    |
| CronJob     | Periodic Batch Job                           |
| Namespace   | Namespace                                    |





## Contributing


Did we miss one of your favorite commands? We welcome the community to contribute to this repo and insert commands that were helpful for you in your Nomad journey. We also welcome the addition of any new cheatsheets centered around Nomad. If you'd rather not contribute directly, we still encourage you to make an issue outlining what additions you'd like to see.


