---
title: "Provisioning an OIDC Provider in Google Cloud for Pulumi Cloud | Python"
h1: "Provisioning an OIDC Provider in Google Cloud for Pulumi Cloud"
linktitle: "Provisioning an OIDC Provider in Google Cloud for Pulumi Cloud"
meta_desc: "Provisioning an OIDC Provider in Google Cloud for Pulumi Cloud How-to Guide using Python"
no_edit_this_page: true
cloud: gcp
language: py
layout: package
---

<!-- WARNING: this page was generated by a tool. Do not edit it by hand. -->
<!-- To change it, please see https://github.com/pulumi/registry/tree/master/tools/mktutorial. -->

<p class="mb-4 inline-flex items-center">
    <a class="rounded-md font-display text-lg text-white bg-white border-2 border-blue-600 px-3 mr-2 whitespace-no-wrap hover:text-white" style="height: 45px; line-height: 41px;" href="https://github.com/pulumi/examples/tree/master/gcp-py-oidc-provider-pulumi-cloud" target="_blank">
        <span class="flex items-center">
            <i class="fab fa-github pr-1.5"></i>
            <span>View Code</span>
        </span>
    </a>
    <a href="https://app.pulumi.com/new?template=https://github.com/pulumi/examples/blob/master/gcp-py-oidc-provider-pulumi-cloud/README.md" target="_blank">
        <img src="https://get.pulumi.com/new/button.svg" alt="Deploy this example with Pulumi">
    </a>
</p>


This example will create OIDC configuration between Pulumi Cloud and Google Cloud, specifically demonstrating connectivity with [Pulumi ESC](https://www.pulumi.com/docs/pulumi-cloud/esc/). The program automates the process detailed in the Google Cloud documentation for the following activities:

- [Create Workload Identity Provider and Pool](https://cloud.google.com/iam/docs/workload-identity-federation-with-other-providers#create_the_workload_identity_pool_and_provider)
- [Authenticate the Workload](https://cloud.google.com/iam/docs/workload-identity-federation-with-other-providers#authenticate)

## Prerequisites

* [Install Pulumi](https://www.pulumi.com/docs/get-started/install/)
* [Configure Pulumi to Use GCP](https://www.pulumi.com/docs/clouds/gcp/get-started/begin/#configure-pulumi-to-access-your-google-cloud-account)
* [Create a Google Cloud Project with the required APIs enabled](https://cloud.google.com/iam/docs/workload-identity-federation-with-other-providers#configure)

## Running the Example

Clone [the examples repo](https://github.com/pulumi/examples) and navigate to the folder for this example.

```bash
git clone https://github.com/pulumi/examples.git
cd examples/gcp-py-oidc-provider-pulumi-cloud
```

Next, to deploy the application and its infrastructure, follow these steps:

1. Create a new stack, which is an isolated deployment target for this example:

    ```bash
    pulumi stack init dev
    ```

1. Set your Pulumi ESC environment name and the name of your GCP Project:

    ```bash
    pulumi config set environmentName <your-environment-name> # replace with your environment name
    pulumi config set gcp:project <your-project-id> # replace with your GCP project ID
    ```

1. Install requirements.

    ```bash
    python3 -m venv venv
    venv/bin/pip install -r requirements.txt
    ```

1. Run `pulumi up -y`. Once the program completes, it will output a YAML template for you to use in the next step.

## Validating the OIDC Configuration

This next section will walk you through validating your OIDC configuration using [Pulumi ESC](https://www.pulumi.com/docs/pulumi-cloud/esc/).

1. Start by [creating a new Pulumi ESC environment](https://www.pulumi.com/docs/pulumi-cloud/esc/get-started/#create-an-environment).
2. Then, copy the template definition from the output in the CLI and paste it into your environment.
3. Save your environment file and run the `pulumi env open <your-pulumi-org>/<your-environment>` command in the CLI. You should see output similar to the following:

```bash
$ pulumi env open myOrg/myEnvironment
{
  "environmentVariables": {
    "GOOGLE_PROJECT": 111111111111
    "CLOUDSDK_AUTH_ACCESS_TOKEN": "ya29...."
  },
  "gcp": {
    "login": {
      "accessToken": "ya29.....",
      "expiry": "2023-11-09T11:12:41Z",
      "project": 111111111111,
      "tokenType": "Bearer"
    }
  }
}
```

## Clean-Up Resources

Once you are done, you can destroy all of the resources as well as the stack:

```bash
$ pulumi destroy
$ pulumi stack rm
```

