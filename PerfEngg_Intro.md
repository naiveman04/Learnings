# Introduction to Performance Engineering

> Notes from an internal session conducted by a Staff Engineer  
> Topic: Performance Testing & Performance Engineering Fundamentals

---

## What is Performance Testing (Non-Functional Testing)?

Performance testing validates **how a system behaves under load**.

### Key Focus Areas
- Speed  
- Scalability  
- Stability  
- Reliability  

### It answers questions like:
- How many users can the system handle?
- Will it slow down or crash under peak load?

> Although non-functional, performance is **business-critical**.

---

## Types of Performance Tests

| Test Type | Purpose |
|---------|--------|
| **Load Testing** | Tests system behavior under expected user load |
| **Stress Testing** | Pushes the system beyond expected limits |
| **Spike Testing** | Evaluates response to sudden traffic surges |
| **Soak / Endurance Testing** | Checks long-duration stability |
| **Scalability Testing** | Assesses horizontal and vertical scaling behavior |

---

## Skills Required for a Performance Tester

<table>
<tr>
<td valign="top" width="50%">

### Technical Skills
- HTTP, REST, APIs  
- Request / response analysis  
- Correlation and parameterization  
- Basic SQL  

### Programming & Scripting
- Java / Scala / JavaScript basics  
- Understanding code flow  
- Debugging scripts  

</td>
<td valign="top" width="50%">

### System Knowledge
- Client–server architecture  
- Databases and caches  
- Load balancers  
- Microservices basics  

### Analytical & Soft Skills
**Analytical**
- Interpreting graphs and metrics  
- Identifying bottlenecks  
- Root cause analysis  

**Soft Skills**
- Communication with dev, infra, product teams  
- Writing clear performance reports  
- Asking the right questions  

</td>
</tr>
</table>

---

## Introduction to Performance Engineering

Performance Engineering is a **proactive approach** to performance.

### Performance is considered throughout:
1. Design  
2. Development  
3. Testing  
4. Production monitoring  

<table>
  <tr>
    <th>Performance Testing</th>
    <th>Performance Engineering</th>
  </tr>
  <tr>
    <td>Finds problems</td>
    <td>Prevents problems</td>
  </tr>
</table>

---

## Key Principles of Performance Engineering

- Shift-left performance  
- Design for scalability  
- Continuous monitoring and tuning  
- Performance as a feature, not a phase  

---

## Tools Used

### Load Generation Tools

<table>
<tr>
<td valign="top" width="50%">

<strong>Open-source</strong>
- JMeter  
- Gatling  
- k6  
- Locust  

</td>
<td valign="top" width="50%">

<strong>Commercial</strong>
- LoadRunner  
- NeoLoad  
- BlazeMeter  

</td>
</tr>
</table>

---

### Enterprise & SaaS APM Tools

| Tool | Description |
|----|------------|
| **Datadog** | Full-stack observability covering APM, infrastructure, logs, RUM, and synthetics |
| **New Relic** | End-to-end APM with strong real-user monitoring and distributed tracing |
| **Dynatrace** | AI-driven root cause analysis with deep infrastructure visibility |
| **AppDynamics** | Business-transaction-focused APM, widely used in large enterprises |
| **Elastic APM** | Integrated with ELK stack for logs, metrics, and traces |

---

> **Key takeaway:**  
> Performance Engineering is not a testing activity — it is an **engineering mindset** embedded across the system lifecycle.
