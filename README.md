My Personal AI Infrastructure Lab

Foundation, Evolution & Secure AI Orchestration | A Living Engineering Project

Architecture revision: November 22, 2026

Project Overview

This repository documents the design, development, testing, and continued expansion of my personal AI infrastructure laboratory.

The lab combines hands-on experience in:

- Artificial intelligence and machine learning
- Linux and systems administration
- Local large language models
- Docker and Kubernetes
- Networking and shared storage
- Cybersecurity and intrusion detection
- Agentic AI and controlled autonomy
- Infrastructure monitoring and recovery
- Predictive maintenance and anomaly detection

The objective is not simply to accumulate hardware or deploy increasingly powerful models.

The objective is to build, understand, secure, measure, and continuously improve a locally operated AI infrastructure environment.

The laboratory began with Python coursework and Jupyter notebooks on an HP laptop. It subsequently expanded into local AI development on a Lenovo Legion, larger-model experimentation on a Lenovo Yoga ARM64 platform, shared NAS storage, dedicated infrastructure nodes, and independent security systems.

The current architecture is designed around a three-node Kubernetes cluster, dedicated AI development machines, and physically separated security infrastructure.

This repository is a living engineering record. Planned capabilities are distinguished from installed, configured, tested, and validated systems.

---

Engineering Principles

1. Optimize before autonomy. Establish reproducible model performance before introducing autonomous execution.

2. Security by design. Every model and agent must operate under appropriate security policies.

3. Independent enforcement. Security mechanisms must not depend entirely on the systems they supervise.

4. Human oversight first. Autonomous containment is introduced only after controlled testing and validation.

5. Least privilege. Models, agents, containers, and infrastructure services receive only the permissions necessary for their tasks.

6. Measure everything. Record performance, resource consumption, failures, security events, and recovery behavior.

7. Incremental expansion. Additional hardware and orchestration capabilities must support identifiable engineering requirements.

8. Preserve the learning trail. Document successful experiments, failures, corrections, and design decisions.

---

1. Physical Infrastructure

AI Development and Compute Systems

Lenovo Legion 5 Gen 10

Primary role: Tank7B development, optimization, and testing.

Hardware:

- AMD Ryzen 7 processor
- NVIDIA RTX 5060 GPU
- 8 GB dedicated VRAM
- 48 GB system RAM
- Windows 11

Software and development tools include:

- Ollama
- Docker
- Python
- JupyterLab
- SearXNG
- VS Code
- Local model evaluation tools

Primary workloads:

- Tank7B
- Ozzy development
- Coding experiments
- Sensor drift analysis
- Anomaly detection
- Retrieval-augmented workflows
- Security testing

Lenovo Yoga RTX Spark

Primary role: Larger-model development and Tank30B experimentation.

Hardware:

- NVIDIA N1-based ARM64 platform
- 64 GB unified LPDDR5X memory
- 1 TB SSD
- Windows ARM64

Development environment:

- Ubuntu through WSL2
- NVIDIA CUDA Toolkit
- Docker
- VS Code with WSL integration
- Python and machine learning libraries

Previously completed validation includes ARM64 Docker execution and basic Linux development functionality.

GPU acceleration and larger-model performance must be documented separately for each tested runtime and workload.

Planned workloads include:

- Tank30B
- Larger coding models
- Model optimization
- Developer/reviewer collaboration
- Agentic workflow experiments

HP Development Laptop

Primary role: General laboratory health monitoring and Linux practice.

Responsibilities include:

- Python development
- Jupyter notebooks
- Linux administration exercises
- Infrastructure health monitoring
- Operational dashboards
- Manual laboratory supervision

This machine is not the primary security enforcement host.

---

2. Mini-PC Infrastructure

The expanded infrastructure consists of five mini PCs.

System| Assigned responsibility
HP EliteDesk 800 G5 Mini| Kubernetes control plane
Dell OptiPlex #1| Kubernetes worker node 1
HP Mini #2| Kubernetes worker node 2
Lenovo ThinkCentre Tiny| Independent Watchdog
Dell OptiPlex #2| Suricata and Adrian security services

These assignments represent the intended architecture. Deployment and validation status must be tracked independently.

Kubernetes Control Plane

HP EliteDesk 800 G5 Mini

Known hardware configuration:

- Intel Core i7-9700T
- 16 GB RAM
- 256 GB storage

Assigned responsibilities:

- Kubernetes control plane
- Cluster coordination
- Workload scheduling
- Cluster API services
- Cluster configuration management
- Infrastructure experimentation

The control plane will support a three-node Kubernetes environment.

Kubernetes Worker Node 1

Dell OptiPlex #1

Known hardware configuration:

- Intel Core i5-9500T
- 32 GB RAM
- 256 GB SSD

Assigned responsibilities:

- Container workloads
- Kubernetes worker services
- Infrastructure monitoring workloads
- Controlled distributed-computing experiments

Kubernetes Worker Node 2

HP Mini #2

Assigned responsibilities:

- Additional Kubernetes worker capacity
- Distributed workload experiments
- Resource scheduling tests
- Infrastructure monitoring
- Failure and recovery simulations

Exact hardware specifications and deployment status will be recorded following verification.

Independent Security Host

Lenovo ThinkCentre Tiny

Dedicated role: Watchdog security enforcement.

Watchdog operates outside Kubernetes.

Its responsibilities include:

- Independent workload supervision
- Heartbeat monitoring
- Security policy enforcement
- Container containment
- Shutdown authorization
- Security event logging
- Communication with Pitbull

The purpose of this separation is to prevent the Kubernetes cluster from being solely responsible for its own security enforcement.

Watchdog requires protected credentials, limited permissions, and independently tested control mechanisms.

Dedicated Network and Agent Security Host

Dell OptiPlex #2

Dedicated role: Suricata and Adrian.

This machine is assigned to network and agent-focused security monitoring.

Planned services:

Suricata

- Network intrusion detection
- Traffic analysis
- Suspicious connection monitoring
- Network security event generation
- Structured security logging

Suricata must receive the relevant network traffic through an appropriate monitoring configuration. A normal network connection alone does not provide visibility into all traffic between other devices.

Adrian

- Agent-focused security monitoring
- Suspicious tool-use investigation
- Agent activity analysis
- Potential prompt-injection detection
- Security event correlation

Adrian's precise capabilities, integration methods, and resource requirements require verification before deployment claims are made.

The intended configuration uses Linux to minimize unnecessary system overhead.

CPU, RAM, storage, and network utilization will be measured with both security services operating concurrently.

---

3. Networking and Shared Storage

Network Infrastructure

The laboratory uses:

- Netgear Nighthawk BE9200 router
- 2.5 GbE Ethernet switches
- Cat 6 Ethernet cabling
- 2.5 GbE adapters for supported systems
- Segmented physical work areas

The network connects AI development machines, Kubernetes infrastructure, shared storage, and security services.

Planned validation includes:

- Network throughput
- Latency
- Packet loss
- Device connectivity
- Network isolation
- Security monitoring visibility

Additional adapters and switch capacity will be evaluated as infrastructure expands.

Shared Storage

UGREEN NASync DXP4800

Storage configuration:

- Four-bay NAS
- Two 8 TB Seagate IronWolf drives
- Mirrored storage configuration

Intended storage categories:

- AI models
- Jupyter notebooks
- Engineering documentation
- Laboratory logs
- Project backups
- Personal files

The NAS supports shared storage and project continuity.

RAID mirroring is not a replacement for independent backups.

Backup integrity and recovery procedures require dedicated validation.

Power Protection

The laboratory includes CyberPower UPS equipment.

Power management planning covers:

- Safe shutdown
- Power-loss recovery
- UPS runtime testing
- Load distribution
- Infrastructure restart procedures

UPS capacity will be reassessed as additional mini PCs are deployed.

---

4. Kubernetes Architecture

The planned cluster consists of three nodes:

KUBERNETES CLUSTER
|
+-- HP EliteDesk Mini
|   +-- Control Plane
|
+-- Dell OptiPlex #1
|   +-- Worker Node 1
|
+-- HP Mini #2
    +-- Worker Node 2

The cluster will support:

- Container orchestration
- Resource allocation
- Workload placement
- Service discovery
- Infrastructure monitoring
- Controlled recovery testing
- Agent and service coordination

Kubernetes does not combine the physical RAM or GPU memory of separate computers into one shared memory pool.

Tank7B and Tank30B remain primarily hosted on their respective development laptops.

Remote model access and cluster integration will require separately configured interfaces and network permissions.

---

5. Pitbull: In-Cluster Security Monitoring

Pitbull is a planned Kubernetes-managed monitoring and anomaly-detection agent.

Pitbull will operate inside the cluster.

Its primary responsibility is to monitor both infrastructure behavior and the activities of AI agents executing assigned tasks.

Infrastructure Monitoring

Pitbull is intended to observe:

- Kubernetes node health
- Container failures
- Resource consumption
- Unexpected restarts
- Abnormal workload activity
- Service availability
- Unusual operational behavior

AI Agent Monitoring

Pitbull will also monitor assigned AI workloads for:

- Suspicious tool calls
- Unauthorized file operations
- Unexpected execution behavior
- Abnormal resource usage
- Policy violations
- Possible prompt-injection attempts
- Deviations from assigned task boundaries

Monitoring of models operating outside Kubernetes requires appropriate telemetry connections.

Pitbull Security Authority

Pitbull will not initially have independent shutdown authority.

Its first operational phase is detection, evidence collection, and alerting.

When suspicious behavior is detected, Pitbull will communicate the event to Watchdog.

Watchdog will be responsible for authorized enforcement.

This establishes a separation between detection and containment.

---

6. Watchdog: Independent Security Enforcement

Watchdog remains physically independent on the Lenovo ThinkCentre Tiny.

Its purpose is to supervise designated workloads and enforce security boundaries without relying entirely on the Kubernetes environment.

Previously Demonstrated Capability

An earlier Tank7B test demonstrated that a container could be shut down following loss of the required Watchdog heartbeat.

This result establishes an initial security milestone, not complete validation of the final distributed architecture.

Planned Enforcement Responsibilities

Watchdog will support:

- Heartbeat supervision
- Security incident intake
- Policy evaluation
- Human authorization
- Targeted container containment
- Security event logging
- Recovery supervision

Pitbull-to-Watchdog Workflow

AI Agent or Kubernetes Workload
             |
             v
       Pitbull Monitoring
             |
             v
       Anomaly Detected
             |
             v
       Evidence Recorded
             |
             v
      Watchdog Notified
             |
             v
       Policy Evaluation
             |
             v
     Human Authorization
             |
             v
   Targeted Container Shutdown
             |
             v
       Incident Logging

During initial development, containment actions require human authorization except for separately validated fail-closed safeguards.

After extensive testing, narrowly defined security conditions may qualify for automatic enforcement.

Watchdog will target the affected workload rather than indiscriminately shutting down the entire Kubernetes cluster.

Its control permissions must be restricted to authorized resources.

---

7. Universal AI Guardrails

Every AI model and agent developed within the laboratory will be subject to an appropriate security baseline.

This applies to:

- Ozzy
- Tank7B
- Tank30B
- Twin
- Pitbull
- Future specialized agents

The purpose is to reduce exposure to prompt injection, unauthorized tool execution, unsafe workflows, and privilege escalation.

NVIDIA NeMo Guardrails

NeMo Guardrails is planned as part of the model and agent security architecture.

Potential responsibilities include:

- Input screening
- Conversation policy enforcement
- Output validation
- Tool-use restrictions
- Detection of suspicious instructions
- Structured security decisions

Exact capabilities depend on configuration, integrations, and validation.

Ollama-Side Security Controls

Ollama-hosted models will receive additional application-level safeguards.

These may include:

- Request validation
- Tool-call authorization
- Restricted execution environments
- Model access controls
- Output inspection
- Security event logging

Ollama itself should not be treated as a complete guardrails or security enforcement framework.

Additional application logic and external controls are necessary.

Prompt-Injection Defense

The security design assumes that untrusted content may contain malicious instructions.

Potential sources include:

- Retrieved web pages
- Search results
- Documents
- Repository files
- Tool responses
- Agent-to-agent messages

The architecture will distinguish untrusted content from authorized instructions.

Guardrails will be combined with tool permissions, sandboxing, and independent enforcement.

No single guardrails layer is assumed to eliminate prompt-injection risk.

---

8. Layered Security Architecture

The laboratory uses complementary security responsibilities.

Component| Primary responsibility
NeMo Guardrails| Model interaction and policy controls
Ollama-side safeguards| Application and model runtime protections
Pitbull| Cluster and AI workload anomaly detection
Watchdog| Independent supervision and authorized enforcement
Suricata| Network intrusion detection
Adrian| Agent-focused security monitoring, subject to capability verification

Each component addresses a different part of the security problem.

Overlap is acceptable when it improves detection reliability, but unnecessary duplication and conflicting authority must be avoided.

The design emphasizes:

- Defense in depth
- Least privilege
- Independent monitoring
- Human authorization
- Evidence-based response
- Controlled recovery

---

9. Phased Security Development

Phase 1: Detection and Alerting

Pitbull monitors infrastructure and agent behavior.

Suspicious activity is logged and reported.

No new autonomous containment authority is granted.

Phase 2: Human-Authorized Containment

Pitbull reports suspicious activity to Watchdog.

Watchdog evaluates the applicable policy.

Human authorization is required before executing newly enabled containment actions.

Phase 3: Validated Conditional Automation

After sufficient testing, Watchdog may automatically contain specifically authorized workloads when validated security conditions are met.

Autonomous actions remain narrowly scoped.

Cluster-wide shutdown and other high-impact operations continue to require explicit authorization.

Validation Requirements

Testing will include:

- False-positive detection rates
- Missed security events
- Detection latency
- Containment latency
- Audit-log integrity
- Heartbeat interruptions
- Unauthorized tool requests
- Restricted file access
- Prompt-injection simulations
- Container isolation
- Recovery procedures
- Attempts to bypass supervision

Security controls must also be evaluated for their impact on legitimate work.

---

10. Local AI Projects

Ozzy — Local AI Assistant

Repository:

https://github.com/curriemark63-byte/Ozzy_Project

Ozzy is a local-first assistant developed using Mistral 7B, retrieval-augmented responses, and SearXNG.

It established practical experience in:

- Local inference
- Retrieval
- Containerization
- Search integration
- Debugging

Tank — Local Coding Assistant

Repository:

https://github.com/curriemark63-byte/Tank_Coding_Agent

Tank7B uses Qwen 2.5 Coder 7B through Ollama.

Its primary operating modes include:

- Code
- Teach
- Engineering

Testing has included:

- Prime-number programming
- Sensor drift
- Anomaly detection
- Power-monitoring exercises
- Technical retrieval

Tank remains subject to model optimization and security validation before autonomous workflows are introduced.

Tank30B

Tank30B is intended to operate on the Lenovo Yoga.

Development priorities include:

- Runtime validation
- Memory optimization
- Inference benchmarking
- Coding performance
- Larger-model security policies
- Developer/reviewer collaboration

Twin

Twin is a planned professional AI assistant intended for technical research and infrastructure-related workflows.

Its permissions and security policies will be defined according to its assigned responsibilities.

---

11. Model Collaboration and Agentic Development

The laboratory will compare non-agentic and agentic workflows.

Non-Agentic Baseline

Tank7B and Tank30B will perform development and review tasks under direct human supervision.

Example:

1. Tank7B develops a solution.
2. Tank30B reviews the result.
3. Human supervision manages revisions.
4. Tests are executed and recorded.
5. Model roles are reversed.

Supervised Agentic Experiment

After security validation, an orchestrator may coordinate bounded development and review activities.

Controls will include:

- Defined task scope
- Limited tool permissions
- Restricted working directories
- Execution budgets
- Iteration limits
- Human approval gates
- Watchdog supervision
- Security event logging

The purpose is to measure whether autonomous coordination improves results enough to justify its complexity.

---

12. Performance and Reliability Evaluation

Evaluation will use repeatable tasks and recorded measurements.

Model Metrics

- Task correctness
- Test pass rate
- Inference latency
- Token throughput
- Memory consumption
- GPU utilization
- Resource stability

Infrastructure Metrics

- CPU utilization
- RAM consumption
- Network throughput
- Storage performance
- Container recovery time
- Node availability
- Scheduling behavior

Security Metrics

- Detection accuracy
- False positives
- Missed incidents
- Alert latency
- Containment time
- Policy violations
- Recovery success
- Audit-log completeness

Results will be recorded with relevant system configurations and test conditions.

---

13. Development Roadmap

Workstream| Status| Next milestone
HP learning environment| Established| Continue Linux and monitoring exercises
Legion / Tank7B| Working development environment| Complete optimization and benchmark records
Yoga / Tank30B| Development foundation established| Validate larger-model performance
UGREEN NAS| Hardware acquired and initially deployed| Verify backups and recovery
2.5 GbE network| Infrastructure expanded| Validate throughput and monitoring visibility
Kubernetes control plane| Hardware assigned| Confirm deployment and cluster health
Kubernetes worker 1| Hardware assigned| Validate worker integration
Kubernetes worker 2| Additional HP Mini planned| Confirm hardware and deployment
Independent Watchdog| ThinkCentre assigned| Validate cross-machine enforcement
Pitbull| In-cluster architecture defined| Develop detection and alerting
Suricata| Dedicated security host planned| Configure traffic visibility and test detection
Adrian| Dedicated security host planned| Verify capabilities and integration
NeMo Guardrails| Universal adoption planned| Establish model-specific policies
Ollama-side safeguards| Universal adoption planned| Implement and test runtime controls
Agentic collaboration| Future phase| Begin after security validation

Status convention: Hardware assignment, software installation, successful configuration, and validated operational behavior are separate milestones.

---

14. Future Engineering Experiments

Planned areas include:

- Predictive maintenance
- Data-center power anomalies
- Sensor drift detection
- Kubernetes failure simulations
- Security incident response
- Prompt-injection resilience
- Multi-agent collaboration
- Distributed monitoring
- Infrastructure recovery
- Aerospace-related machine learning using synthetic or appropriately authorized data

---

15. Professional Development

I bring more than 20 years of electromechanical testing experience to this engineering project.

My professional objective is to combine practical testing and troubleshooting experience with:

- Artificial intelligence
- Machine learning
- Linux administration
- Networking
- Kubernetes
- Infrastructure reliability
- Cybersecurity
- Predictive maintenance

This laboratory serves as both a technical learning environment and a portfolio of documented engineering work.

Each project is approached through requirements, implementation, testing, evidence collection, and continuous improvement.

---

Project Philosophy

Build the foundation.

Secure the environment.

Validate the behavior.

Measure the results.

Expand deliberately.

The laboratory is not presented as a finished production platform.

It is an evolving engineering environment designed to demonstrate practical learning, disciplined experimentation, and increasingly capable local AI infrastructure.

Last architecture revision: November 22, 2026.