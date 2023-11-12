## NestJS Microservices App with Docker and Kubernetes setup. Integrated Stripe, GCP (Cloud Build, Artifact Registry).

DB: MongoDB (can be changed to SQL)
Nestjs/Microservices on TCP, Auth with Passport, Payments with Stripe

Make sure to set env variables into both google cloud cli and .env files.

### Run

```bash
# Docker Compose
$ docker dompose up --build
# or Helm
$ cd k8s/airbnb && helm install airbnb .
```
