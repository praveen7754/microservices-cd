# Frontend deployment

The frontend is deployed through Argo CD using the `frontend` ECR image.

Browser flow:

Browser
  -> NGINX Ingress (`microservices.local`)
     -> `/` -> frontend Service
     -> `/products`, `/login`, `/cart`, `/orders` -> gateway Service
        -> auth/product/cart/order services

The frontend uses same-origin API calls such as `/products` and `/cart/alice`,
so no browser CORS configuration is required for the normal ingress path.

Kafka is intentionally not deployed in this stage.
