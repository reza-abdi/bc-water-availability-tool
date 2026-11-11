FROM flyway/flyway:11-alpine

# Copy migrations
COPY ./sql /flyway/sql

# Non-root user
RUN adduser -D app
USER app

# Validate recorded history before applying migrations. A one-shot
# migration job does not require a container health check.
CMD ["info", "validate", "migrate"]
