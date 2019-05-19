---
layout: post
title:  "Target port, port, and node-port"
date:   2019-05-19 16:00 -0500
categories: blog update kubernetes learning
---

I know... I know... there are a thousand pages out there giving this exact definition, but to be honest... I am doing this more for me
then for you. (sorry). 

nodePort - This will make the service visible OUTSIDE of the Kubernetes cluster by the node's IP address and the port number declared in this property.
This service also has to be of type NodePort (if this field is not specified, Kubernetnes will allocate a node port automatically.)

port - exposes the services on the specified port internally within the cluster. That is, the service becomes visible on this port and will send requests made to this port 
to the pods selected by the service.

targetPort - This is the port on the pod that the request gets sent to. Your application needs to be listening for network requests on this port for the service to work.

Reference:
https://matthewpalmer.net/kubernetes-app-developer/articles/kubernetes-ports-targetport-nodeport-service.html
