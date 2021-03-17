# Cadence Commands.

## Not work
`curl -O https://raw.githubusercontent.com/uber/cadence/v0.18.1/docker/docker-compose.yml`
`docker-compose up`
`docker run --rm ubercadence/cli:master --domain samples-domain domain register`
`docker run --network=host --rm ubercadence/cli:master --do test-domain domain register -rd 1`
`docker run --rm ubercadence/cli:master --domain samples-domain domain describe`

`docker run --rm ubercadence/cli:master --address host.docker.internal:7933 --domain test-domain domain describe`
`docker run --rm ubercadence/cli:master --address host.docker.internal:7933 --domain test-domain workflow list`

`alias cadence="docker run --rm ubercadence/cli:master --address host.docker.internal:7933 "`
`cadence --domain test-domain domain desc`

## Work
`curl -O https://raw.githubusercontent.com/uber/cadence/v0.7.1/docker/docker-compose.yml`
`docker-compose up`

`docker run --network=host --rm ubercadence/cli:master --do test-domain domain register -rd 1` - register domain 
`docker run --network=host --rm ubercadence/cli:master --do test-domain domain describe` - describe domain

`docker run --network=host --rm ubercadence/cli:master --do test-domain workflow start -wt test -tl test -et 300` - start workflow
`docker run --network=host --rm ubercadence/cli:master --do test-domain workflow list -op` - list started workflow
`docker run --network=host --rm ubercadence/cli:master --do test-domain workflow terminate -wid workflowId` - terminate workflow with workflowId
`docker run --network=host --rm ubercadence/cli:master --do test-domain workflow list` - list terminated workflow

docker run --network=host --rm ubercadence/cli:master --do test-domain workflow start --et 300  --tl hello --wt HelloWorkflow::getGreetings --input \"World\"  