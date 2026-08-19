# CD changes

- Kafka has been removed for this stage.
- Removed the Kafka StatefulSet and headless Service Helm template.
- Removed Kafka/streaming configuration from the common chart and product production values.
- Product continues to use Redis with a persistent PVC.
- Cart continues to use Redis with a persistent PVC.
- Product application data continues to use a persistent PVC.
- Frontend is deployed as its own Argo CD Application.
- Frontend is exposed at `/` through `microservices.local`.
- Gateway keeps API routes under `/products`, `/login`, `/cart`, and `/orders`.
- Redis remains internal ClusterIP only.
- ECR application images remain unchanged.
