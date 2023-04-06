> Hello, first of all, thanks for the opportunity of learning more about SIG
> Network. I would love to hear your story so could you please tell us a bit
> about yourself, your role, and how you got involved in SIG Network?

Hello! Thank you for reaching out.

My Kubernetes journey started while I was working for a small data center: we
were early adopters of Kubernetes and focused on using Kubernetes to provide
SaaS products. That experience led to my next position developing a distribution
of Kubernetes with a focus on networking. During this period in my career, I was
active in SIG Network (predominantly as a consumer).

When I joined [Kong][kong] my role in the community changed significantly, as
Kong actively encourages upstream participation. I greatly increased my
engagement and contributions to the [Gateway API][gwapi] project during those
years and eventually became a maintainer.

I care deeply about this community and the future of our technology, so when
a chair position for the SIG became available I volunteered my time
immediately. I've enjoyed working on Kubernetes over the better part of a
decade and I want to continue to do my part to ensure our community and
technology continues to flourish.

[kong]:https://konghq.com/
[gwapi]:https://gateway-api.sigs.k8s.io/

> What's going on in SIG Network today, and where can people jump in and
> contribute?

For those who may be uninitiated: SIG Network is responsible for the components,
interfaces, and APIs which expose networking capabilities to Kubernetes users
and workloads. The [charter][net-charter] is a pretty good indication of our
scope, but I can add some additional highlights on some of our current areas of
focus:

### KubeProxy / KPNG

Those who are familiar with Kubernetes will be familiar with the `Service` API
which enables exposing a group of `Pods` over a network. The current standard
implementation of `Service` is known as `kube-proxy` but what may be unfamiliar
to people is that there are a growing number of disparate alternative
implementations on the rise in recent years. To try and give provisions to these
implementations (and also provide some areas of alignment so that implementations
do not become too disparate from each other) upstream Kubernetes efforts are
underway to create a more modular public interface for `kube-proxy`. The
intention is for implementations to join in around  a common set of libraries and
speak a common language. This area of focus is known as the KPNG project, if this
sounds interesting to you, please join us in the KPNG [community meetings][meet]
and `#sig-network-kpng` on [Kubernetes Slack][kslack].

[meet]:https://github.com/kubernetes/community/blob/master/sig-network/README.md#meetings
[kslack]:https://kubernetes.slack.com/

### Multi-Network

Today one of the primary requirements for Kubernetes networking is to achieve
connectivity between `Pods` in a cluster, satisfying a large number of
Kubernetes end-users. However, some use cases require isolated networks and
special interfaces for performance-oriented needs (e.g. `AF_XDP`, `memif`,
`SR-IOV`). There's a growing need for special networking configurations in
Kubernetes in general. The Multi-Network project exists to improve the
management of multiple different networks for `Pods`: if you're interested in
some of the lower-level details of `Pod` networking or have relevant use cases
join us in the Multi-Network community meetings and `#sig-network-multi-network`
on Kubernetes Slack.

### Network Policy

The `NetworkPolicy` API sub-group was formed to address network security beyond
the well-known version 1 of the `NetworkPolicy` resource. We've also been
working on the `AdminNetworkPolicy` resource (previously known as
`ClusterNetworkPolicy`) to provide cluster administrator-focused functionality.
The network policy sub-project is a great place to join in if you're
particularly interested in security and CNI, please feel free to join our
community meetings and the `#sig-network-policy-api` channel on Kubernetes
Slack.

### Gateway API

If you're particularly interested in **ingress** or **mesh** networking the
Gateway API may be a sub-project you would enjoy. In Gateway API we're actively
developing the successor to the illustrious `Ingress` API which includes a
`Gateway` resource which defines the addresses and listeners of the gateway and
various routing types (e.g. `HTTPRoute`, `GRPCRoute`, `TLSRoute`, `TCPRoute`,
`UDPRoute`, .e.t.c) which attach to `Gateways`. We also have an initiative
within this project called GAMMA which is geared towards using Gateway API
resources in a mesh network context. There are some up-and-coming side projects
within Gateway API as well, including `ingress2gateway` which is a tool for
compiling existing `Ingress` resources to equivalent Gateway API resources and
`Blixt` which is a Layer4 implementation of Gateway API using Rust/eBPF for the
dataplane and is intended as a testing and reference implementation. If this
sounds interesting to you we'd love to have you join us in our Gateway API
community meetings and `#sig-network-gateway-api` on Kubernetes Slack.

---

This is a non-exhaustive highlight of sub-projects. For help getting started
[Kubernetes Slack][kslack] is a great place to talk to community members and
includes several `#sig-network-<project>` channels as well as our main
`#sig-network` channel. Also check for issues labeled `good-first-issue` if
you prefer to just dive right into the repositories. Let us know how we can
help you!

[net-charter]:https://github.com/kubernetes/community/blob/master/sig-network/charter.md
[kslack]:https://kubernetes.slack.com/

> What skills are contributors to SIG Network likely to learn?

To me, it feels limitless. Practically speaking it's very much up to the
individual what they _want_ to learn. However, If you simply intend to learn as
much as you possibly can about networking SIG Network is a great place to join
in and grow your knowledge.

If you've ever wondered how Kubernetes `Service` API works or wanted to
implement an ingress controller, this is a great place to join in. If
you wanted to dig down deep into the inner workings of CNI, or how the network
interfaces at the `Pod` level are configured you can do that here as well.

We have an awesome and diverse community of people from just about every kind
of background you can imagine. This is a great place to share ideas and raise
proposals, improving your skills in design as well as alignment and consensus
building.

There's a wealth of opportunities here in SIG Network. There's lots of places
to jump in, and the learning opportunities are boundless.