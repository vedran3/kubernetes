Dynamic storage provisioning is enabled in k8s by creating a StorageClass. Use this option, when you want k8s to create the storage for your application itslef, so you are not creating it and definining it yourself upfront (using the pv/pvc method). 

You still consume storage for yor app the same way (using a pvc). Inside a pvc.yaml file, you use the storageClassName in the spec section to specify the sc that you want to use (see pvc_with_sc.yaml file for an example). 

Each StorageClass contains the fields provisioner, parameters, and reclaimPolicy, which are used when a PersistentVolume belonging to the class needs to be dynamically provisioned.

The name of a StorageClass object is significant, and is how users can request a particular class. Administrators set the name and other parameters of a class when first creating StorageClass objects, and the objects cannot be updated once they are created.

You can specify a default StorageClass only for PVCs that don't request any particular class to bind to.