docker run --rm sentry config generate-secret-key

docker-compose up -d postgres redis

docker run -it --rm -e "SENTRY_SECRET_KEY=$SENTRY_SECRET_KEY" -e "SENTRY_REDIS_HOST=redis" -e "SENTRY_POSTGRES_HOST=postgres" --network="sentry_backend" --link sentry-postgres:postgres --link sentry-redis:redis sentry upgrade
