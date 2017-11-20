# ocp_configure_node

## Description:

This role pre-configures a server for deployment of Openshift Container Platform.

## Behaviour:

**Feature:** Configure OCP Node

As a PaaS Operator
I want to preconfigure nodes
so that nodes are ready for OCP deployment

- **Scenario:** OCP node is successfully prepared for OCP deployment
- **Given:** there is enough storage
- **Given:** there is enough memory
- **Given:** there is enough CPU
- **When:** the deployment is executed
- **Then:** subscriptions are attached
- **Then:** repositories are enabled
- **Then:** prereqs are installed
- **Then:** docker storage is configured
- **Then:** ssh keys are deployed 

## Configuration:

A list of the external variables used by the role.

| Variable  | Description  | Example  | 
|---|---|---|
| **node_type**  | The type of node to preconfigure  |  One of master, infra, compute |
| **min_storage**  | List of minimum storage requirements, by node_type  |  (defaults in role) |
| **min_memory**  | List of minimum memory requirements, by node_type | (defaults in role)  |
| **min_cpu**  | List of minimum cpu requirements, by node_type | (defaults in role)  |



## Usage:

How to invoke the role from a playbook:

```yaml
- name: Check OCP Node
  include_role:
    name: ocp_configure_node
  vars:
    node_type: 'master'
```
