---
title: Reverse Connection
further_reading:
- link: "/cloudprem/install/"
  tag: "Documentation"
  text: "CloudPrem Installation Prerequisites"
---

{{< callout btn_hidden="true" >}}
  Datadog CloudPrem is in Preview.
{{< /callout >}}

## Overview

Reverse connection lets your CloudPrem cluster initiate an HTTP connection with Datadog using your API key, without requiring adding a DNS entry and public ingress. This setup is useful for environments with strict network policies which do not allows inbound requests.

It the default setup for CloudPrem, it requires the following environment variables to be set:
- `DD_API_KEY`
- `DD_SITE` which defaults to `datadog.com`

## Helm chart configuration

First create a secret to store the Datadog API key:
```
kubectl create secret generic datadog-secret --from-literal DD_API_KEY=<DATADOG_API_KEY>
```

To set

```yaml
environment:
  DD_SITE: <DD_SITE>
  secretRef:
      name: datadog-secret
```

## Proxies

You can configure CloudPrem to use a forward proxy, such as Squid, with the environment variable `HTTPS_PROXY`.

```yaml
environment:
  HTTP_PROXY: <your HTTP proxy>

```
