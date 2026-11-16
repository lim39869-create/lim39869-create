### What I actually run

One host, no public IPv4, no inbound port. Sixteen containers, two independent outbound ingress
paths, five Docker networks with one container attached to two of them at once. The operations
record re-derives every number from `docker inspect`, `ss -lntp` and the chain itself — nothing in
it is asserted without a command that produces it.

The code is written with AI: I set the goal, the data shapes and the acceptance criteria; the AI
writes the implementation, and I verify by output rather than by reading every line. The harness is
`opencode` with MCP servers and a few custom skills; the models are DeepSeek V4/V4.1 Flash and
GLM-5.3/5.3 Flash, served through a gateway I wrote myself — so my own tool usage is metered by my
own code. Roughly 158k lines of Go in thirteen months, starting from no programming background.

### Three artifacts

**[symbiqo-design](https://github.com/lim39869-create/symbiqo-design)** — design notes for a
capability-behind-UI gateway: collection architecture, P2P transport with NAT traversal, runtime
substrate, and the verification methodology that decides what a number is worth. Also the
disclosure boundary: what is published, what is withheld, and why.

**[xtunnel-go](https://github.com/lim39869-create/xtunnel-go)** — an independent Go implementation
of a tunnel protocol: reliable transport over HTTP request/response pairs, four carrier legs, and a
specification that goes down to byte offsets.

**[paygateway](https://github.com/lim39869-create/paygateway)** — a Go payment gateway: pluggable
channels, order orchestration, a tamper-evident ledger (hash chain + ECDSA), and orchestration of
an Android device fleet.

### What I am closing

Kubernetes. I run the same patterns by hand in Docker today — host networking, multi-homed
containers, per-network subnets — and I would rather say that than claim a cluster I do not
operate. Alongside it: Terraform, a metrics stack with retention rather than a dashboard, and
writing code without the assistance described above.

### Contact

Open to remote roles in the UTC+4 to UTC+9 band. `lim39869@gmail.com` — or an issue on any
repository above.
