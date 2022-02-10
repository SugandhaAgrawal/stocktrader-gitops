It is still possible to delete an ApplicationSet resource, while preventing Applications (and their deployed resources) from also being deleted, using a non-cascading delete:

kubectl delete ApplicationSet (NAME) --cascade=false

Warning

Even if using a non-cascaded delete, the resources-finalizer.argocd.argoproj.io is still specified on the Application. Thus, when the Application is deleted, all of its deployed resources will also be deleted. (The lifecycle of the Application, and its child objects, are still equivalent)



argocd app delete APPNAME --cascade=false
