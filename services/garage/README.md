# Garage with Tailscale Sidecar Configuration

This Docker Compose configuration sets up [**Garage**](https://garagehq.deuxfleurs.fr/) with tailscale as a sidecar container. Allowing you to securely host your own S3 compatible backend on your tailnet

## Garage

[**Garage**](https://garagehq.deuxfleurs.fr/) is an S3 compatible storage solution designed for self hosting at a small scale. Supporting Geo-replication and redundancy optimised for performance and resiliance to node failures.

## Key Features

- S3 API
- Geo-distribution
- Flexible deployments
- Multiple replication modes
- Compression & Deduplication
- And many more [**here**](https://garagehq.deuxfleurs.fr/documentation/reference-manual/features/)

## Configuration Overview

In this deployment, the `tailscale-garage` service runs the Tailscale client to establish a secure private network. The `garage` container uses `network_mode: service:tailscale-garage` to route its traffic through the Tailscale interface. This ensures that all garage api routes are only accessible securely through your tailnet.

## Files to check

Please check the following contents for validity as some variables need to be defined upfront.

- `.env` // Main variable `TS_AUTHKEY` and `TZ` for timezone config
