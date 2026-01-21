# Performance Testing Foundations

> Notes from a LinkedIn Learning course on Performance Testing Foundations  
> Source: AI-assisted summaries + personal consolidation

---

## What is Performance Testing?

**Performance Testing** is the practice of determining how a system performs in terms of **responsiveness** and **stability** under a given **workload**.

### Key Concepts

- **Responsiveness**  
  The speed at which the application responds to requests (e.g., response time, latency).

- **Stability**  
  The ability of the application to behave consistently and reliably, especially under concurrent user load.

- **Workload**  
  The input to the test, which may include:
  - Load testing
  - Stress testing
  - Endurance (soak) testing
  - Spike testing
  - Scalability testing

> Performance testing is non-functional in nature, but it directly impacts user experience and business outcomes.

---

## Why Performance Testing Is Important

- Ensures acceptable response times and system stability
- Prevents poor user experience, outages, and revenue loss
- Identifies performance risks before production

### Cost–Benefit Trade-Off

Performance testing can be resource-intensive, so it’s important to evaluate:

- **Likelihood of issues**
  - Major releases
  - Traffic spikes (sales, campaigns)
  - Large code or infrastructure changes

- **Impact of issues**
  - Size of the user base
  - Business criticality
  - SLAs or contractual obligations

> Not every system needs extreme performance testing, but critical systems always do.

---

## Getting Started with Performance Testing

Before running any test:

- **Understand the business need**  
  Why is performance testing required, and who benefits from it?

- **Identify available tools**  
  Choose tools based on application type, protocols, and team expertise.

- **Gather necessary data**
  - Input data: user flows, traffic patterns
  - Output data: metrics, logs, system stats

- **Ask questions**  
  Clarifying assumptions early avoids meaningless tests later.

---

## Measurements in Performance Testing

### Timing Measurements
- Focus on how fast operations complete
- Expect variability between runs
- Multiple executions are needed for reliable results

### Stability Measurements
- Error rates
- CPU and memory usage
- Disk and network utilization

### Analytics-Based Measurements
- Use real user data (production analytics)
- Helps design realistic and relevant test scenarios

---

## Identifying Bottlenecks

A **bottleneck** is any part of the system that limits overall performance.

### Common Bottleneck Areas
- UI or frontend code
- Server-side logic
- API calls
- File I/O
- Databases
- Third-party services
- Network latency
- Poor system design

### Key Principle
> Optimize the **entire system**, not just one slow component.

Fixing one layer while ignoring others often shifts the bottleneck rather than removing it.

---

## Monitoring Performance Test Results

- **Expect variation**  
  Results naturally fluctuate due to environment and system noise.

- **Use running averages**  
  Helps distinguish real issues from random spikes.

- **Monitor multiple indicators**
  - Response times
  - Error rates
  - Resource usage

This reduces false positives and missed failures.

---

## Load Testing

**Purpose:** Validate behavior under expected user load.

### Key Steps
- **Test design**
  - Decide load pattern
  - Decide what metrics to measure

- **Types of load**
  - Basic load
  - Ramp-up / ramp-down
  - Multi-step load
  - Random load
  - Linear load
  - Exponential growth load

- **Execution**
  - Run in a controlled environment
  - Be aware of differences from production

- **Analysis**
  - Identify issues
  - Refine test design or system behavior

---

## Stress Testing

**Purpose:** Understand how the system fails under extreme conditions.

### Characteristics
- Gradually increase load until failure
- Identify breaking points, not just limits

### What to Monitor
- Swap memory
- Physical RAM
- CPU saturation
- Error rates

> Stress tests must **never** be run on public or live systems without permission.

---

## Endurance (Soak) Testing

**Purpose:** Validate long-term stability under sustained load.

### Key Focus Areas
- Memory leaks
- Resource exhaustion
- Gradual performance degradation

### What to Monitor
- Memory consumption
- CPU utilization
- File I/O patterns

Analysis focuses on **trends over time**, not short-term spikes.

---

## Spike Testing

**Purpose:** Measure behavior during sudden traffic surges (e.g., viral events).

### Load Profiles
- Single spike
- Double spike

### What to Observe
- Response times
- Auto-scaling behavior
- Error rates
- Timeouts

> Test environments should closely resemble production, but never hit live systems.

---

## Scalability Testing

**Purpose:** Ensure the system scales efficiently with demand.

### Key Aspects
- Speed of resource allocation
- Avoiding over-provisioning
- Avoiding frequent scaling oscillations

Especially important for **cloud-native systems**.

---

## Statistics in Performance Testing

Understanding statistics is essential for correct interpretation.

- **Sample size**  
  Too little data leads to misleading conclusions.

- **Average (mean)**  
  Useful, but easily skewed by outliers.

- **Median**  
  Better indicator of typical user experience.

- **Standard deviation**  
  Shows variability in performance.

- **Percentiles (p90, p95, p99)**  
  Critical for understanding tail latency.

---

## Charts in Performance Testing

### Common Chart Types

- **XY (time-series) charts**
  - Show metric changes over time and load

- **Waterfall charts**
  - Visualize how a single request/page loads step by step

### Tooling
- Export metrics to CSV for deeper analysis
- Use Excel or similar tools to combine datasets
- Chrome DevTools provide:
  - Waterfall views
  - Filmstrip rendering analysis

---

## Performance Testing Using Log Files

- Log files are valuable data sources, especially in production
- Server access logs can reveal:
  - Response times
  - Error patterns
  - URL-level performance

### Practical Approach
- Use Python scripts to parse logs
- Extract metrics such as:
  - Min / max response times
  - Averages per endpoint

LLM tools can help enhance and refactor these scripts.

---

## Single-User Performance Testing Tools

These tools analyze performance without load generation.

- **WebPageTest.org**  
  Detailed page-level performance analysis

- **PageSpeed Insights**  
  Performance metrics with optimization suggestions

- **Pingdom**  
  Diagnostics and performance recommendations

- **Chrome Developer Tools**
  - Lighthouse
  - Network and performance tabs

---

## Load Testing Tools

| Tool | Notes |
|-----|------|
| JMeter | Popular open-source load testing tool |
| Loader.io | Cloud-based load testing service |
| SoapUI | API testing tool with load testing support |
| Gatling | Code-first, developer-focused performance tool |
| Locust | Python-based, easy to integrate |

---

## Network Interception Tools

Used to understand and simulate network behavior.

- **Fiddler / Charles Proxy**
  - Inspect and control network traffic

- **Browser Developer Tools**
  - Simulate slower networks

- **WebPageTest.org**
  - Test performance under different network conditions

---

### Final Takeaway

> Performance testing is not just about running tools —  
> it’s about **asking the right questions, measuring the right things, and interpreting results correctly**.
