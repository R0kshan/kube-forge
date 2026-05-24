# Kube Forge (WIP)

So what are we "forging"? We are forging understanding of Kubernetes concepts and how the components of its architecture independently react to bring the cluster to a desired state.

## Why does this repo exist ? 

I want to deepen my understanding of Kubernetes and the underlying architecture, the interactions between components triggered by incomming / outgoing traffic as well as `kubectl` commands. And this gave me the idea to try to gain this understanding through a more visual and engaging manner.

## Status

Experimenting | Ongoing development

## Current idea

The current idea is to visualize Kubernetes through a 3D Three.js scene in the browser, where cluster state changes and asynchronous control-plane workflows are represented spatially as you apply resource updates to the cluster.

It is not a simulation of Kubernetes internals, but an observational and visual layer built on top of a real Kubernetes cluster and its state changes.

### Live & Trace Modes

Kube Forge operates in two complementary modes:

**Live mode**

- Displays real-time Kubernetes state changes from the cluster
- Reflects pod lifecycle, scheduling, scaling, and failures as they happen

**Trace mode**

- Allows replay of the events triggered by a specific resource change (e.g. after a `kubectl apply`)
- Reconstructs Kubernetes object lifecycles as a sequence of visual events
- Helps understand how Kubernetes system behavior emerges from independent control plane components reacting to state changes
- Slows down and spatially represents the asynchronous reconciliation steps that are otherwise difficult to observe directly in real time

The visualization is derived from real Kubernetes state transitions and events, while the trace visualization itself is an educational reconstruction of how Kubernetes components react and coordinate conceptually via the API server. It does not attempt to represent literal internal execution traces of Kubernetes components.

### How does this help understand the concepts?

You’ll be guided by notifications in the browser-based interface, with structured objectives (built around operational scenarios and problem-solving) to help you practice configuration as well as understand how Kubernetes components collectively react after each change.

Through these objectives, you’ll learn how to (not an exhaustive list):

- set up services and networking
- deploy pods
- observe and react to events
- update running deployments
- configure cronjobs
- analyse failures and misconfigurations

The idea is to get familiar and comfortable with manipulating Kubernetes, while also understanding how Kubernetes system behavior emerges from the orchestration between components visualized in a 3D world.

This approach helps make Kubernetes behavior and asynchronous control-plane loops more visible and easier to understand, especially when dealing with indirect, non-linear control-plane behavior.

The goal is to learn through operational scenarios:

- encourage learning through observation, troubleshooting, and reacting to evolving cluster conditions while visualizing their impact in real time
- making Kubernetes concepts more engaging, interactive, and easier to reason about

**Example:** Applying a deployment manifest triggers a pod scheduling flow visualized in 3D in real time in live mode, and as a step-by-step reconstructed sequence of how components (Controller Manager, Scheduler, and Kubelet) independently coordinate via the API Server in trace mode.

## Notes

I’ve had this idea for a while and explored different ways of balancing visuals and interactivity while focusing on the educational aspect.

I recently came across this repo: <https://github.com/pshenok/server-survival>

It helped shape my idea into something that seems suitable for learning Kubernetes.

I’m still experimenting with the concept, its educational effectiveness, and what is realistically achievable in terms of visuals to represent how these asynchronous loops can be understood conceptually, which is not always straightforward. Hopefully this turns into something useful.

## Contribution

The idea is still in a very early stage, however if you find this idea interesting feel free to open an issue to discuss it.
