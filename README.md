# canzea-rpa

## Speaking

- containerize
- register secrets on Vault: https://vault.186527.xyz/ui/vault/secrets/secret/show/providers/aws/live
- install: voice/aws_polly

```
resources:
- service_discovery_service:
      aws_polly:
        Name: aws_polly
        Address: "${d}{var.compute_instance.${instance.name}.privateIp}"
        Port: 4022
        Tags: [ "${instance.id}", "${environment.id}", "text_to_speech" ]
        Check:
          http: "http://${d}{var.compute_instance.${instance.name}.privateIp}:4022"
          interval: 10s
          timeout: 1s

- service_endpoint:
      ${instance.id}-aws-polly:
        service: aws_polly
        instance: ${instance.id}
        environment: ${environment.id}
        segment: ${segment.id}
        type: console
        secure: "http://${environment.id}.${es.fqdn}:4022"

```

## Listening

## Intelligence
