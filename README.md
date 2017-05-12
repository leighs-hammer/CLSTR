# CLSTR
A stackable performance cluster system for apps across colocations.
Single service micro componentry for a HA system.


View Example schematic

## Loadbalancer Blocks

- NGINX ( Awesome as it terminates SSL and can terminate multiple and SNI to single upstreams ) 
- HAProxy ( Awesome but can be a bit fidly, however as a transparent it is amazing allowing for balancing of straight TCP and DB type connectivity. ) 
- NGINX GeoWall ( In Dev ) 

## App Blocks
- Apache / PHP 7 ( It is hard to beat apache for straight PHP performance and in some circumstances can out perform NGINX )
- NGINX / FPM / PHP7 ( While quite frequently a config nightmare, NGINX as a php app server is not a bad option, note can be slightly slower than apache for mass request based apps )
- Node / PM2

## DB Blocks
- MariaDB 10 / Galera ( the continuation of MySQL and stable as can be great for colocation ) 
- MongoDB 

## Storage
- NFS : Methodology attached to all servers 
- S3 : Methodology mounted to server stacks
- Google : Cloud Storage

## Procedures for 100% uptime
- LoadBalance -> Away
- Perform Tasks
- LoadBalanc -> Incoming

## SSL & Termination 
- "A" grade termination config
- Multi termination same location
- LetsEncrypt
- Generic SSL Certs

## Scripts & Helpers
- Updates
- Backups
|-- Minute Based
|-- Hourly
|-- Daily 
|-- Weekly
|-- Monthly
|-- CLEAN UP
- SSL Task Runners
- Cron Planning
