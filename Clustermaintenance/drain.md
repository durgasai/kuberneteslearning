###Things need to be done during OS Updates for the nodes
* If we want to do some Updates for node, which might require some downtime and also we will loose pods.
* Also if there is only one replica and pod is sceduled on that node, we will complately lost the application.
* In these scenarious we can just drain the node, which will place the pods in the other nodes and once we are back we can uncordon the node so that it will be available for scheduling pods.

Commands we can use

**kubectl drain <node-name>** this will place the pods in the other nodes and make this node unavailable for scheduling.
**kubectl uncordon <node-name>** once the OS updates were done node will be again make available for scheduling.
**kubectl cordon <node-name>** if we want to make node unavailable for scheduling.