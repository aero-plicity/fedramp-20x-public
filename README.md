<p align="center">
  <a href="https://aeroplicity.com">
    <img src="https://aeroplicity.com/static/aeroplicity_logos/Aeroplicity_0_Wordmark_Default.png"
         alt="Aeroplicity" height="100">
  </a>
</p>

# Aeroplicity FedRAMP 20x - Public

> **Purpose.** This repository contains the **public** materials for Aeroplicity’s FedRAMP 20x submission. It is safe to publish and contains no Controlled Unclassified Information (CUI) or sensitive production secrets. Evidence paths shown here reference redacted or synthetic examples suitable for public release.

---

## Aeroplicity

Aeroplicity provides frictionless operating software built for Aerospace & Defense.

---

## Key Security Indicator (KSI) Control Structure

This repository uses Key Security Indicator (KSI) controls for FedRAMP compliance validation. The KSI controls are defined using a structured JSON format that validates specific NIST SP 800-53 controls through automated checks.

### KSI Structure

Each KSI control follows this structure:

```json
{
  "KSI-IDENTIFIER": {
    "description": "Description of the security requirement being validated",
    "controls": [
      "control-id-1",
      "control-id-2"
    ],
    "scope": "This KSI applies to [specific components/services/systems]",
    "cli_commands": [
      {
        "command": "validation_command",
        "client_type": "aws_service_or_http",
        "explanation": "How this evidence demonstrates compliance"
      }
    ]
  }
}
```

### Command Types

The system supports several types of validation commands:

1. **Evidence Check** - Verifies files exist in the evidence directory
2. **AWS API Calls** - Executes boto3 methods (e.g., `client.describe_instances()`)
3. **HTTP Downloads** - Downloads content from URLs
4. **Multi-step Operations** - Complex validation workflows with post-processing
5. **Aeroplicity API Calls** - Internal API endpoint validation

### KSI Categories

KSI identifiers follow the pattern: `KSI-[CATEGORY]-[NUMBER]`
- **CED**: Configuration and Environment Controls
- **IAM**: Identity and Access Management Controls
- **NET**: Network Security Controls
- **CRY**: Cryptographic Controls
- **AUD**: Audit and Accountability Controls

### Evidence Organization

Evidence files are organized in the `evidence/{KSI-ID}/` directory structure, with automated validation ensuring all required evidence exists for compliance verification.

---

### Contact Information

Aeroplicity Security<br>
security@aeroplicity.com<br>
+1 (213) 442-1712

---
