Volumes - these are local Volumes for the Pod, that you specify in the Pod spec in a Pod.yaml file. This is good for ephemeral storage (since it is just a Volume on the Pod - so ephemeral) and also for sharing data between 2 containers within a Pod, like a sidecar config. This would be for data that is not important and can be lost at any time.

There are 2 Local Volume Types, native to k8s: 

hostPath Volumes - store data in a specified directory on the k8s Node. So essentially you specify a directory location and on whichever Node your Pod happens to be running on, that's where the files are actually going to be stored on the file system of your k8s Node.

emptyDir Volumes - this type is a Temporary Volume. This directory only exists only for as long as the Pod exists on the Node. If the Pod is deleted, the emptyDir and all the data inside it is deleted as well. This volume type is very useful for sharing data between 2 containers in a Pod. (Basically, this volume type is good for Multiple Containers on a Pod)

There are other Cloud Provider specific local volume types as well, like AWS EBS and Azure Data Disk... 
