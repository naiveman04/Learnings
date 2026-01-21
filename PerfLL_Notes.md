# Performance Testing Foundations

> Notes from a LinkedIn Learning course on Performance Testing Foundations  
> Source: AI-assisted summaries + personal consolidation

---

## What is Performance Testing?

**Performance Testing** is the practice of determining how a system behaves in terms of **responsiveness** and **stability** when subjected to a defined **workload**.

### Key Concepts

- **Responsiveness**  
  Refers to how quickly the application responds to user requests. This typically includes response time, latency, and throughput, and directly affects user perception of speed.

- **Stability**  
  Describes how consistently and reliably the system behaves, especially when multiple users interact with it simultaneously. A stable system does not degrade or crash under sustained load.

- **Workload**  
  Represents the input conditions of the test, including the number of users, request patterns, and data volume. Different workloads are modeled using:
  - Load testing
  - Stress testing
  - Endurance (soak) testing
  - Spike testing
  - Scalability testing

> Although performance testing is non-functional, its impact on user experience, revenue, and reliability makes it business-critical.

---

## Why Performance Testing Is Important

- Ensures that applications respond within acceptable time limits under real-world usage.
- Helps prevent outages, slowdowns, and poor user experience in production.
- Identifies performance risks early, when they are cheaper to fix.

### Cost–Benefit Trade-Off

Performance testing requires infrastructure, tools, and time, so it should be applied thoughtfully.

- **Likelihood of issues**  
  Performance risks increase during:
  - Major feature releases
  - Large code refactors
  - Infrastructure or cloud changes
  - High-traffic events such as sales or campaigns

- **Impact of issues**  
  The cost of failure depends on:
  - Number of active users
  - Business criticality of the system
  - SLAs or contractual commitments

> Systems that are business-critical or customer-facing almost always justify performance testing.

---

## Getting Started with Performance Testing

Before executing any performance test, preparation is essential.

- **Understand the business need**  
  Clarify why performance testing is required and what problem it is expected to solve.

- **Identify available tools**  
  Select tools based on application type, supported protocols, and team expertise.

- **Gather necessary data**  
  - Input data such as user journeys, traffic distribution, and peak load expectations  
  - Output data such as response times, error rates, and system metrics

- **Ask questions early**  
  Clarifying assumptions prevents running tests that produce misleading or unusable results.

---

## Measurements in Performance Testing

### Timing Measurements
- Measure how long requests take to complete under load.
- Expect natural variability between runs due to system noise.
- Multiple executions are required to identify consistent performance patterns.

### Stability Measurements
- Monitor error rates to detect functional failures under load.
- Track CPU, memory, disk, and network usage to identify resource exhaustion.
- Stability issues often appear before complete system failure.

### Analytics-Based Measurements
- Use real user monitoring (RUM) or production analytics data.
- Helps design realistic test scenarios that reflect actual usage patterns.

---

## Identifying Bottlenecks

A **bottleneck** is any component that limits overall system performance.

### Common Bottleneck Areas
- Frontend or UI rendering logic
- Server-side application code
- API calls and integrations
- File input/output operations
- Databases and query performance
- Third-party services
- Network latency
- Architectural or design limitations

### Key Principle
> Performance optimization must focus on the **entire system**, not isolated components.

Fixing one bottleneck often reveals the next weakest part of the system.

---

## Monitoring Performance Test Results

- **Expect variation**  
  Performance results fluctuate due to background processes, shared infrastructure, and network conditions.

- **Use running averages**  
  Smoothing data helps differentiate real performance degradation from random spikes.

- **Monitor multiple indicators simultaneously**  
  Relying on a single metric can hide failures or create false alarms.

This approach reduces false positives while improving confidence in results.

---

## Load Testing

**Purpose:** Validate how the system behaves under expected user load.

### Key Steps
- **Test design**
  - Define the load pattern and user behavior.
  - Decide which metrics indicate success or failure.

- **Types of load**
  - Basic constant load
  - Ramp-up and ramp-down patterns
  - Multi-step or phased load
  - Randomized request patterns
  - Linear growth
  - Exponential growth

- **Execution**
  - Run tests in a controlled environment.
  - Understand differences between test and production setups.

- **Analysis**
  - Identify response time degradation or failures.
  - Adjust test design or system configuration as needed.

---

## Stress Testing

**Purpose:** Understand how and when the system fails under extreme conditions.

### Characteristics
- Gradually increase load until the system breaks.
- Identify failure thresholds and recovery behavior.

### What to Monitor
- Swap memory usage
- Physical RAM exhaustion
- CPU saturation
- Error spikes and crashes

> Stress testing must only be performed in controlled environments with explicit approval.

---

## Endurance (Soak) Testing

**Purpose:** Validate system stability over long periods of sustained load.

### Key Focus Areas
- Memory leaks
- Resource exhaustion
- Gradual performance degradation

### What to Monitor
- Long-term memory usage trends
- CPU utilization over time
- File and disk I/O behavior

Analysis focuses on trends rather than short-term spikes.

---

## Spike Testing

**Purpose:** Evaluate how the system handles sudden, extreme increases in traffic.

### Load Profiles
- Single spike to simulate viral traffic
- Double spike to test recovery and repeat impact

### What to Observe
- Response time spikes
- Auto-scaling behavior
- Error rates and timeouts

Test environments should closely mirror production but never target live systems.

---

## Scalability Testing

**Purpose:** Ensure the system scales efficiently as demand changes.

### Key Aspects
- Speed and efficiency of resource allocation
- Avoiding under-provisioning and over-provisioning
- Preventing frequent or unstable scaling behavior

This is especially important for cloud-based and microservices architectures.

---

## Statistics in Performance Testing

Statistics help interpret performance data correctly.

- **Sample size**  
  Larger datasets produce more reliable conclusions.

- **Average (mean)**  
  Shows general trend but can hide outliers.

- **Median**  
  Represents typical user experience more accurately when outliers exist.

- **Standard deviation**  
  Indicates how much variability exists in performance.

- **Percentiles (p90, p95, p99)**  
  Reveal tail latency and worst-case user experience.

---

## Charts in Performance Testing

### Common Chart Types

- **XY (time-series) charts**
  - Show how metrics evolve over time and under changing load.

- **Waterfall charts**
  - Break down a single user request into individual steps.

### Tooling
- Export metrics to CSV for deeper analysis.
- Combine datasets using spreadsheet tools.
- Chrome DevTools provide:
  - Waterfall timelines
  - Filmstrip rendering analysis

---

## Performance Testing Using Log Files

- Log files provide valuable performance data, especially in production.
- Server access logs reveal response times, errors, and endpoint behavior.

### Practical Approach
- Use Python scripts to parse log files.
- Extract metrics such as:
  - Minimum, maximum, and average response times
  - Endpoint-level performance statistics

LLM tools can assist in refining and extending these scripts.

---

## Single-User Performance Testing Tools

These tools analyze performance without generating load.

- **WebPageTest.org**  
  Provides detailed page-level performance analysis across locations and networks.

- **PageSpeed Insights**  
  Offers performance scores and optimization recommendations.

- **Pingdom**  
  Runs diagnostics and highlights performance issues.

- **Chrome Developer Tools**
  - Lighthouse audits
  - Network and performance analysis tabs

---

## Load Testing Tools

| Tool | Description |
|-----|------------|
| JMeter | Widely used open-source load testing tool |
| Loader.io | Cloud-based load testing platform |
| SoapUI | API testing tool with load capabilities |
| Gatling | Code-first, developer-focused performance testing |
| Locust | Python-based load testing framework |

---

## Network Interception Tools

Used to analyze and simulate network conditions.

- **Fiddler / Charles Proxy**  
  Inspect, modify, and debug network traffic.

- **Browser Developer Tools**  
  Simulate slower networks for quick validation.

- **WebPageTest.org**  
  Test application behavior under different network conditions.

---

### Final Takeaway

> Performance testing is not about tools alone —  
> it is about **understanding systems, asking the right questions, and interpreting data correctly**.
