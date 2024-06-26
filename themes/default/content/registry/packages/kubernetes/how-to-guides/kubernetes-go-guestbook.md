---
title: "Simple and Component-based Kubernetes Guestbook Apps | Go"
h1: "Simple and Component-based Kubernetes Guestbook Apps"
linktitle: "Simple and Component-based Kubernetes Guestbook Apps"
meta_desc: "Simple and Component-based Kubernetes Guestbook Apps How-to Guide using Go"
no_edit_this_page: true
cloud: kubernetes
language: go
layout: package
---

<!-- WARNING: this page was generated by a tool. Do not edit it by hand. -->
<!-- To change it, please see https://github.com/pulumi/registry/tree/master/tools/mktutorial. -->

<p class="mb-4 inline-flex items-center">
    <a class="rounded-md font-display text-lg text-white bg-white border-2 border-blue-600 px-3 mr-2 whitespace-no-wrap hover:text-white" style="height: 45px; line-height: 41px;" href="https://github.com/pulumi/examples/tree/master/kubernetes-go-guestbook" target="_blank">
        <span class="flex items-center">
            <i class="fab fa-github pr-1.5"></i>
            <span>View Code</span>
        </span>
    </a>
    <a href="https://app.pulumi.com/new?template=https://github.com/pulumi/examples/tree/master/kubernetes-go-guestbook/simple" target="_blank">
        <img src="https://get.pulumi.com/new/button.svg" alt="Deploy this example with Pulumi">
    </a>
</p>


A port of the standard [Kubernetes Guestbook](https://kubernetes.io/docs/tutorials/stateless-application/guestbook/)
to Pulumi. This example shows you how to build and deploy a simple, multi-tier web application using Kubernetes and
Docker, and consists of three components:

* A single-instance Redis master to store guestbook entries
* Multiple replicated Redis instances to serve reads
* Multiple web frontend instances

There is an [interactive Tutorial available](https://www.pulumi.com/docs/tutorials/kubernetes/guestbook/) for
this example. If this is your first time using Pulumi for Kubernetes, we recommend starting there.

In this directory, you will find two variants of the Guestbook:

1. [simple/](https://github.com/pulumi/examples/blob/master/kubernetes-go-guestbook/simple) is a direct port of the original YAML.
2. [components](https://github.com/pulumi/examples/blob/master/kubernetes-go-guestbook/components) demonstrates the benefits of using a real language, namely eliminating boilerplate through
   the use of real component abstractions.

Both examples provision the exact same Kubernetes Guestbook application, but showcase different aspects of Pulumi.

