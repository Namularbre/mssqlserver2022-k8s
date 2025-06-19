# MS SQL Server 2022 on K8S

Here you can find a MS SQL Server 2022 configuration that runs on k8s.

## Setup

### Make a secret for SA password

First, you need to create a secret for the SA password.

The most secure way is to run this command (change the password of course)
```bash
kubectl create secret generic mssql-sa-secret --from-literal=SA_PASSWORD="YourStrong@Passw0rd"
```

But you can also make a secret.yaml, even if it's less secure.

*Note: MS SQL Server want a secure password with more that 8 characters and with digits and letters or it won't work ;)*

### Make a statefulset for K8S

You just need to copy the statefulset.yaml, adapt it as you want, and then run this command:
```bash
kubectl apply -f statefulset.yaml
```
