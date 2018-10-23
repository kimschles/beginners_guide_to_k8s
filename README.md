# A Beginner's Guide to Kubernetes 

Develop Denver, October 18, 2018

## Steps 
### Prebuilt: 

1. Build an app
    * The Node.js app is done! See `package.json`, `index.js`, and the `public` directory 
    * Run `npm install` and `npm start` to run the app locally 
2. Turn the app into a Docker image
    * See `Dockerfile` 
    * `docker build -t kimschles/dvlp-2018 .` 
    * To create a container locally, run `docker run -p 8080:8080 kimschles/dvlp-2018`
    * See the app at `http://localhost:8080/`
3. Push the image to a registry
    * `docker push kimschles/dvlp-2018`
    * [https://hub.docker.com/r/kimschles/dvlp-2018/](https://hub.docker.com/r/kimschles/dvlp-2018/)
 
### To Do: 

4. Create a K8s cluster with GKE 
    * Go to https://cloud.google.com/
    * Create a project 
    * Create a cluster with Google Kubernetes Engine 
    * Connect with Cloud Shell 
    * `git clone` this repo
    * `cd beginners_guide_to_k8s` 
5. Deploy the app to a cluster 
    * `kubectl apply -f app/namespace.yml` 
    * `kubectl apply -f app/deployment.yml`
6. Expose the app to the internet
* `kubectl apply -f app/hpa.yml"` 
7. Add some cool K8s stuff 
    * Increase the number of replicas
    * Horizontal Pod AutoScaler     
        * Test with Apache Bench `ab -n 30000 -c 100 http://[external_ip]:[port]/` 
    * Rolling Updates 
8. Delete your hpa, service, deployment and cluster!
 



