<p align="center">
  <a href="https://aeroplicity.com">
    <img src="https://aeroplicity.com/static/aeroplicity_logos/Aeroplicity_0_Wordmark_Default.png"
         alt="Aeroplicity" height="100">
  </a>
</p>

# Aeroplicity FedRAMP 20x - Public

> **Purpose.** This repository hosts **public** materials that support Aeroplicity’s FedRAMP 20x authorization effort. It contains no Controlled Unclassified Information (CUI), export-controlled data, or production secrets. Any evidence references point to redacted or synthetic examples intentionally prepared for public release.

---

## Aeroplicity

Aeroplicity provides frictionless operating software built for Aerospace & Defense.

<a href="https://aeroplicity.com/trust-center" target="_blank" rel="noopener noreferrer">Visit the Aeroplicity Trust Center →</a>

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
    "scope": "This KSI applies to [specific components/services/systems within the cloud service offering]",
    "cli_commands": [
      {
        "command": "",
        "client_type": "",
        "http_request": {
          "method": "GET",
          "url": "https://example.com/path"
        },
        "evidence_files": [
          {
            "file": "filename.ext",
            "description": "Description of file contents",
            "applicability": "The section of the evidence file that applies to this KSI"
          }
        ],
        "output_file": "",
        "post_process": {
          "type": "multi_step",
          "steps": [
            {
              "action": "call",
              "method": "describe_instances",
              "extract": "Reservations[*].Instances[*].InstanceId",
              "params": {
                "MaxResults": 50
              }
            }
          ]
        },
        "explanation": "Detailed explanation of what evidence demonstrates compliance with this KSI requirement"
      }
    ],
    "auditor_notes": ""
  }
}
```

### Public KSI Results JSON structure

The published, machine-readable KSI results conform to the following structure (see `ksi/ksi_results_schema.json` for details):

```json
{
  "metadata": {
    "generated_at": "ISO-8601 timestamp",
    "generator_version": "string",
    "total_ksis": "integer",
    "total_passed": "integer",
    "total_partial": "integer",
    "total_failed": "integer",
    "category_summary": {
      "<category_prefix>": {
        "total": "integer",
        "passed": "integer",
        "partial": "integer",
        "failed": "integer",
        "long_name": "string"
      }
    }
  },
  "validations": [
    {
      "ksi_id": "string (e.g., KSI-MLA-08)",
      "assessment": "string enum: Pass | Partial | Fail",
      "timestamp": "ISO-8601 timestamp",
      "successful_commands": "integer",
      "failed_commands": "integer",
      "requirement": "string",
      "long_name": "string",
      "category_prefix": "string (e.g., KSI-MLA)"
    }
  ]
}
```

### Command Types and Requirements

The system supports several types of validation commands, each with specific requirements:

1. **Evidence Check** (`"command": "evidence_check"`)
   - **Purpose**: Verify files exist in `evidence/{KSI-ID}/` directory
   - **Required**: `evidence_files` array listing files to verify
   - **Optional**: `note` for additional context

2. **AWS API Calls** (e.g., `"command": "client.describe_instances()"`)
   - **Purpose**: Execute AWS API calls via boto3
   - **Required**: `client_type` (AWS service name like s3, ec2, iam, cloudtrail)
   - **Optional**: `note`, `post_process` for result processing

3. **HTTP Downloads** (`"command": "download"`)
   - **Purpose**: Download content from HTTP URLs
   - **Required**: `client_type="http"`, `http_request` object with method and URL
   - **Optional**: `output_file` (saves to `evidence/{KSI-ID}/`), `note`

4. **Multi-step Operations** (`"command": "multi_step"`)
   - **Purpose**: Execute complex multi-step validation workflows
   - **Required**: `post_process` object with `type: "multi_step"` and `steps` array
   - **Optional**: `client_type`, `note`

5. **Aeroplicity API Calls** (`"command": "aeroplicity_api"`)
   - **Purpose**: Call Aeroplicity API endpoints using environment-driven form-data
   - **Required**: `client_type="aeroplicity_api"`, `http_request` object
   - **Note**: Server base URL comes from env var `aeroplicity_api_server_url`
   - **Note**: Automatically includes env vars for authentication and context
   - **Optional**: `post_process`

### Post-Processing Capabilities

For complex validation scenarios, the `post_process` object supports:

- **Multi-step Operations**: Sequential operations with `steps` array
- **Filtering**: Filter data based on criteria
- **Data Extraction**: Use JMESPath expressions to extract specific data
- **Transformation**: Transform data structures

Each step in a multi-step operation can:
- **Call** APIs (`"action": "call"`) with method, parameters, and extraction rules
- **Filter** data based on conditions
- **Extract** data using JMESPath expressions
- **Transform** data structures

### KSI Categories

KSI identifiers follow the pattern: `KSI-[CATEGORY]-[NUMBER]`
- **CED**: Configuration and Environment Controls
- **IAM**: Identity and Access Management Controls
- **NET**: Network Security Controls
- **CRY**: Cryptographic Controls
- **AUD**: Audit and Accountability Controls

### Evidence Organization

Evidence files are organized in the `evidence/{KSI-ID}/` directory structure, with automated validation ensuring all required evidence exists for compliance verification.

#### Evidence File Requirements

For each KSI, evidence files must include:
- **File name**: The actual filename of the evidence document
- **Description**: Clear description of what the file contains
- **Applicability**: Specific section or content of the evidence file that applies to this KSI requirement

#### Validation Process

- Evidence files are automatically checked in `evidence/{KSI-ID}/` directory
- Multiple commands can be combined for comprehensive validation
- Post-processing enables complex validation scenarios
- The scope field defines where the KSI applies within the cloud service offering
- The explanation field documents how the evidence demonstrates compliance with the KSI requirement

---

### Contact Information

Aeroplicity Security<br>
security@aeroplicity.com<br>
+1 (213) 442-1712

---
