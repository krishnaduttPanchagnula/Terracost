# Terracost

**Terracost** is a CLI tool that calculates AWS costs from a Terraform plan in JSON format.  

It is currently focused on **on-demand Linux EC2 instances** in the `us-east-1` region.  
The goal is to first support **all AWS regions for EC2**, and later expand to other AWS services.

---

## Features

- Parse a Terraform plan in JSON format.
- Calculate **monthly cost** for EC2 instances.
- Commands for:
  - **Plan cost** — Estimate costs from a Terraform plan file.
  - **Infra cost** — Get total cost of running infrastructure.
- Simple and script-friendly CLI output.

---

## Installation

Download the latest release from the [Releases](https://github.com/krishnaduttPanchagnula/terracost/releases) page and place the binary in your `PATH`.

For example, on Linux/macOS:

```bash
chmod +x terracost
sudo mv terracost /usr/local/bin/
````

Check if it’s installed:

```bash
terracost -v
```

---

## Usage

### General Help

```bash
terracost -h
```

---

### Commands

#### 1. **Plan Cost**

Calculate cost from a Terraform plan JSON file.

```bash
terracost get plan-cost --file myplan.json
```

Example output:

```
┌───────────┬───────────────┬───────────────┬───────────┬───────────────────────┐
│   NAME    │ RESOURCE TYPE │ INSTANCE TYPE │  REGION   │ MONTHLY COST  (USD)   │
├───────────┼───────────────┼───────────────┼───────────┼───────────────────────┤
│ webserver │ AmazonEC2     │ t3.medium     │ us-east-1 │ $25.92                │
└───────────┴───────────────┴───────────────┴───────────┴───────────────────────┘

```

---

#### 2. **[WIP]Infra Cost**

Get the total monthly cost of your running infrastructure.

```bash
terracost get infra-cost
```

Example output:

```
Total infra cost: $78.50/month
```

---

## Current Scope

* **Service:** AWS EC2
* **Pricing type:** On-demand, Linux
* **Region:** us-east-1 only

---

## Roadmap

1. **Expand EC2 support to all AWS regions.**
2. Add support for other AWS services:

   * Amazon RDS
   * Amazon S3
   * Amazon EKS
   * And more…
4. More output formats (JSON, CSV).

---
## Contributing

Pull requests are welcome!
If you’d like to add support for more services or regions, feel free to fork the repo and open a PR.

---

## License

MIT License. See the [LICENSE](LICENSE) file for details.
