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

Reverse connection lets your CloudPrem cluster initiate an HTTP connection with Datadog using your API keys, without requireing a DNS entry and public ingress. This setup keeps CloudPrem private and is useful for environments with strict network policies.

To activate the reverse connection, set the following values in your Helm chart:

```yaml
config:
  cloudprem:
    enable_reverse_connection: true
    site: "datadoghq.com" # your site
    dd_api_key: "${DD_API_KEY}"
    dd_application_key: "${DD_APP_KEY}"
```

## Further reading

{{< partial name="whats-next/whats-next.html" >}}
