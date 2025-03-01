# Overview

This document provides a high level view of the workflow for adding a new
infrastructure provider to OpenShift. The following list is meant to give
a general idea of the work involved with this process, the links contained
within the list reference documents with greater detail for each step.

## Workflow

1. [Preparation](/preparation.md)

    Start with an idea to add a new infrastructure provider to OpenShift.
    Identify contacts within Red Hat, and the community, and then set
    expectations about the process ahead.

1. [Information Gathering](/information-gathering.md)

    Define the reference architecture and toplogy for OpenShift clusters
    on the new provider. Inventory existing components including licenses
    and plugin providers, and identify supported formats and infrastructure.

1. [OpenShift Enhancement](/openshift-enhancement.md)

    Create an enhancment describing the new platform in detail, this will
    become a part of the official
    [OpenShift enhancements](https://github.com/openshift/enhancements).

1. [Cloud Controller Manager](/cloud-controller-manager.md)

    New providers must have a
    [Cloud Controller Manager](https://kubernetes.io/docs/concepts/architecture/cloud-controller/)
    integrated into OpenShift, including a repository in the OpenShift
    organization and container images included in the release payload.

1. [Container Storage Interface Driver](/container-storage-interface-driver.md)

    Providers that expose storage options must have a CSI driver integrated into
    OpenShift, including a repository in the OpenShift organization and container
    images inclujded in the release payload.

1. [Machine API Controllers](/machine-api-controllers.md)

    New providers must have a Machine actuator, and related controllers, for
    the [Machine API Operator](https://github.com/openshift/machine-api-operator),
    including a repository in the OpenShift organization and container images
    included in the release payload.

1. [Network Ingress and DNS](/network-ingress-dns.md)

    Evaluate provider-specific support for ingress load balancers and endpoint
    publishing strategies, as well as internal and external DNS support.
    Update and validate the
    [Cluster Ingress Operator](https://github.com/openshift/cluster-ingress-operator)
    for the new infrastructure provider.

1. [Continuous Integration and Testing](/continuous-integration-and-testing.md)

    All components must have a suite of automation including unit style testing
    (run in isolation), and integration testing (run on cluster from the
    provider). This automation is part of the OpenShift development and release
    process, and exists within the OpenShift organization.

1. [Component Infrastructure](/component-infrastructure.md)

    Once OpenShift can be installed and operated on the new infrastructure
    platform attention should be given to the dynamic infrastructure services.
    These components are non-critical to the installation process and include
    things like the image registry.

1. [Documentation](/documentation.md)

    Product documentation is required for installation and maintenance tasks
    on the new infrastructure platform. Source level documentation is expected
    for all component repositories added to the OpenShift organization.

1. [Red Hat Relationship](/red-hat-relationship.md)

    After the new infrastructure provider is ready for release, what are the
    commitments around maintenance and future releases.

1. [Release](/release.md)

    What to do once the code is approved and the release is ready for public
    consumption. How to promote and advertise, and work with Red Hat.
