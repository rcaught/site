---
title: "High Availability"
---

Convox Racks are designed to be durable in the face of common failure scenarios such as instance failure or loss of an  availability zone.

All major changes to Convox Racks or applications are executed as rolling, incremental updates. It is simple to ensure that your Rack and applications are as robust as possible.

### Hardening a Rack

#### Instance Count

Rack instances are automatically spread across three availability zones in your chosen region. Run at least 3 instances in your Rack to take advantage of this distribution. This allows your Rack to easily survive loss of up to two availability zones.

See [Scaling](/docs/scaling).

#### Private Networking

Configure your Rack to use a private internal network with the load balancers and NAT gateways providing the only access in or out of your Rack.

    $ convox rack params set Private=Yes

### Hardening an Application

#### Process Count

Run at least 2 copies of each process to ensure constant uptime even if an instance is lost or terminated. Run at least 3 or more copies for better balancing across availability zones and higher durability to instance loss.

    $ convox scale web --count 3

<div class="block-callout block-show-callout type-info" markdown="1">
If your process type declares internet-facing ports you must have at least N+1 instances in your Rack to support load balancing and rolling updates.
</div>

See [Scaling](/docs/scaling).
