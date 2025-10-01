# Continuous Monitoring Plan (Aeroplicity 20x Moderate)

Objectives
- Persistently validate KSI controls post-authorization
- Detect configuration drift and degraded security posture quickly
- Publish machine-readable deltas and summaries for reviewers

Signals and cadence
- Daily and event-driven runs for sensitive KSIs (IAM, logging, network)
- Weekly comprehensive sweep across all KSIs
- On-demand runs triggered by significant changes

Pipeline overview
- Source: AWS GovCloud telemetry and inventories via SDK/APIs
- Validation: Deterministic checks mapped to KSI definitions
- Output: JSON results merged into unified_ksi_validations-public.json and summarized for humans

Governance
- Findings triage within 1 business day
- POA&M entries opened for sustained Partial/Failed items
- Change notifications raised for material impact

See conmon_pipeline.json for a prototype configuration.
