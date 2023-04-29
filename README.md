# gke-nextjs-poc

## nextjs
`npm run dev`

## gke setup
https://medium.com/bb-tutorials-and-thoughts/gcp-deploying-next-js-app-with-nodejs-backend-on-gke-908bdb7a5be2
`docker build -t next-node-image .`
`docker run -it -p  3000:3000 --name next-node-ui next-node-image`
`docker images`
`docker ps`
`gcloud services enable containerregistry.googleapis.com`
`gcloud auth configure-docker`
`docker build -t nextjs-node-image .`
`docker tag nextjs-node-image gcr.io/nextjs-gke-poc/nextjs-webapp:v1`
`docker push gcr.io/nextjs-gke-poc/nextjs-webapp:v1`
https://cloud.google.com/kubernetes-engine/docs/deploy-app-cluster
`gcloud container clusters create my-cluster --location us-central1-f`
`gcloud components install gke-gcloud-auth-plugin`
`gcloud container clusters get-credentials my-cluster --zone us-central1-f --project nextjs-gke-poc`
`kubectl get nodes`
`kubectl create -f manifest.yml`
`kubectl get deploy`
`kubectl get po`
`kubectl get svc`
`gcloud container clusters delete my-cluster`
https://cloud.google.com/kubernetes-engine/docs/tutorials/configuring-domain-name-static-ip
`gcloud container clusters create domain-test`
https://cloud.google.com/nat/docs/gke-example
`kubectl apply -f helloweb-deployment.yaml`
`gcloud compute addresses create helloweb-ip --region us-central1`
`gcloud compute addresses describe helloweb-ip --region us-central1`
`kubectl apply -f helloweb-service-static-ip.yaml`
`kubectl get service`
`curl http://34.72.5.23/`
`kubectl delete ingress,service -l app=hello`
`gcloud compute addresses delete helloweb-ip --region us-central1`
`kubectl delete -f helloweb-deployment.yaml`
`gcloud compute forwarding-rules list`
`gcloud container clusters delete domain-test`