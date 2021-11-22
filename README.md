Деплой кластера

    terraform init
    terraform apply

Импорт контекста в kubectl

    aws eks --region $(terraform output -raw region) update-kubeconfig --name $(terraform output -raw cluster_name)

Установка Ingress контроллера в кластер

    helm repo add eks https://aws.github.io/eks-charts
    helm install aws-load-balancer-controller eks/aws-load-balancer-controller --set clusterName=my-cluster -n kube-system
