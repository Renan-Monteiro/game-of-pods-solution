$ kubectl create role developer-role --resource=pods,svc,pvc --verb=* --namespace=development

$ kubectl create rolebinding -n development developer-rolebinding --role=developer-role --user=drogo

$ kubectl config set-credentials drogo --client-certificate=/root/drogo.crt --client-key=/root/drogo.key

$ kubectl config set-context developer --cluster=kubernetes --user=drogo

$ kubectl config use-context developer