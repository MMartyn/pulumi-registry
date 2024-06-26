---
title: "AWS Resources (in Go) | Go"
h1: "AWS Resources (in Go)"
linktitle: "AWS Resources (in Go)"
meta_desc: "AWS Resources (in Go) How-to Guide using Go"
no_edit_this_page: true
cloud: aws
language: go
layout: package
---

<!-- WARNING: this page was generated by a tool. Do not edit it by hand. -->
<!-- To change it, please see https://github.com/pulumi/registry/tree/master/tools/mktutorial. -->

<p class="mb-4 inline-flex items-center">
    <a class="rounded-md font-display text-lg text-white bg-white border-2 border-blue-600 px-3 mr-2 whitespace-no-wrap hover:text-white" style="height: 45px; line-height: 41px;" href="https://github.com/pulumi/examples/tree/master/aws-go-resources" target="_blank">
        <span class="flex items-center">
            <i class="fab fa-github pr-1.5"></i>
            <span>View Code</span>
        </span>
    </a>
    <a href="https://app.pulumi.com/new?template=https://github.com/pulumi/examples/blob/master/aws-go-resources/README.md" target="_blank">
        <img src="https://get.pulumi.com/new/button.svg" alt="Deploy this example with Pulumi">
    </a>
</p>


A Pulumi program that demonstrates creating various AWS resources in Golang

## Deploying the App

To deploy your infrastructure, follow the below steps.

### Prerequisites

1. [Install Go](https://golang.org/doc/install)
2. [Install Pulumi](https://www.pulumi.com/docs/get-started/install/)
3. [Configure AWS Credentials](https://www.pulumi.com/docs/intro/cloud-providers/aws/setup/)

### Steps

After cloning this repo, from this working directory, run these commands:

1. Next, create a new Pulumi stack, which is an isolated deployment target for this example:

    ```bash
    $ pulumi stack init
    ```

2. Set the required configuration variables for this program:

    ```bash
    $ pulumi config set aws:region us-west-2
    ```

3. Run `pulumi up` to preview and deploy changes:

    ```bash
    $ pulumi up
    Previewing update (dev):
    ...

    Updating (dev):
    ...
    Resources:
        + 28 created
    Duration: 44s
    ```

## Clean up

1. Run `pulumi destroy` to tear down all resources.

2. To delete the stack itself, run `pulumi stack rm`. Note that this command deletes all deployment history from the Pulumi console.

