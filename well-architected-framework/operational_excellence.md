# Operational Excellence
## Overview
**Operational Excellence** is the ability to **run and monitor systems** to **deliver business value** and to continually **improve supporting processes and procedures**.

## Design Principles
The following are the design principles for operational excellence in the cloud:
- **Perform operations as code**: Automate procedures to limit human error and create consistent responses to events.
- **Make frequent, small, reversible changes**: Design workloads to allow components to be updated regurlarly to increase the flow of beneficial changes to the workload.
- **Refine operations procedures frequently**: Evolve procedures as the workload evolves.
- **Anticipate failure**: Set up regular game days to test workload and team responses to simulated events.
- **Learn from all operational failures**: Drive improvement through lessons learned from all operationals events and failures.

## Practice Areas
### Organisation
To create operational excellence, we must understand:
- **Organisation priorities**: teams have a shared understand the entire workload, their role in it, and shared business goals to set priorities for business success.
- **Operating model**: teams understand their part in achieving business success. A well-defined set of responsibilities will reduce the frequency of conflicting and redundant efforts.
- **Organisational culture**: support is provided to team members so that they can be effective in taking action and support business outcomes.

### Prepare
To prepare for operational excellence, we must perform:
- **Design telemetry**: workloads provide the information necessary to understand its internal state.
    - Best practices: metrics, logs, events, and traces.
- **Design for operations**: adopt approaches that improve the flow of changes into production and that help refactoring, fast feedback on quality, and bug fixing.
    - Best practices: version control, build and deployment management systems, multiple environments.
- **Mitigate deployment risks**: adopt approaches that provide fast feedback on quality and provide rapid recovery from changes that do not have desired outcomes.
    - Best practices: automate testing and rollback.
- **Operational readiness and change management**: evaluate the operational readiness of the workload, processes, procedures, and personnel to understand the operational risks related to the workload.
    - Best practices: runbooks to perform procedures, playbooks to investigate issues.

### Operate
To be successful, we must be able to:
- **Understand workload health**: define, capture, and analyse workload metrics to gain visibility to workload events so that we can take appropriate action.
    - Best practices: identify KPIs, define workload metrics, collect and analyse workload metrics.
- **Understand operational health**: define, capture, and analyse operations metrics to gain visibility to workload events so that we can take appropriate action.
    - Best pratices: identify KPIs, define operations metrics, collect and analyse operations metrics.
- **Respond to events**: anticipate operation events, both planned and unplanned.
    - Best practices: use a process for event, incident, and problem management.

### Evolve
To evolve our operatinos over time, we must be able to:
- **Learn, share, and improve**: regularly provide time for analysis of operations activities, analysis of failures, experimentations, and making improvements.
    - Best practices: have a process for continuous improvement, perform PIRs, implement feedback loops.
