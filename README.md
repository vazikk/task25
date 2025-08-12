# task25
Для начала скачал Kubeadm и Calico <br>

<img width="800" height="226" alt="image" src="https://github.com/user-attachments/assets/c92970b8-2694-4295-8425-fbd46ecc02b0" /> <br>

потом написал маинфест для Pod <br>

```
apiVersion: apps/v1
kind: Deployment
metadata:
  name: nginx
spec:
  replicas: 1
  selector:
    matchLabels:
      app: nginx
  template:
    metadata:
      labels:
        app: nginx
    spec:
      containers:
      - name: nginx
        image: vazik1910/my-nginx:latest
        ports:
        - containerPort: 80
---
apiVersion: v1
kind: Service
metadata:
  name: nginx
spec:
  type: NodePort
  selector:
    app: nginx
  ports:
    - port: 80
      targetPort: 80
```

запустил: <br>

<img width="806" height="146" alt="image" src="https://github.com/user-attachments/assets/a435b13a-7d1a-4908-8805-13d43f152c09" /> <br>

Проверка подключения: <br>

<img width="1055" height="364" alt="image" src="https://github.com/user-attachments/assets/da73884c-58bc-41b1-af9c-be6b5ac1fa94" />




