# Aeroplicity 20x Submission Rationale (Moderate)

This public narrative explains Aeroplicity's approach to our FedRAMP 20x Moderate submission as a SaaS provider.

- Scope and boundary: All services and evidence are within AWS GovCloud (US). Sensitive artifacts remain restricted; public equivalents are sanitized or summarized.
- KSI validations: KSIs are mapped to automated checks using programmatic discovery (e.g., AWS SDK/boto3) and deterministic post-processing. Validation states are True/False/Partial with explicit rationale.
- Automation: Validations run via CI/CD and on-demand workflows. Outputs are captured in machine-readable JSON and summarized in human-readable form for reviewers.
- Evidence handling: Public repo includes sanitized outputs and pointers. Restricted evidence access is handled via access_instructions.json.
- 3PAO integration: A FedRAMP-recognized 3PAO performs an integrated verification of our KSI validations. Their attestation will be provided as a signed document and summarized in 3pao_attestation.md.
- Continuous reporting: We maintain a plan and prototype to persistently validate and report KSI status post-authorization. See continuous_monitoring_plan.md and conmon_pipeline.json.

References
- Executive overview: executive_summary.md
- Human-readable KSI list: ksis_assessment.md
- Machine results: unified_ksi_validations-public.json
- Schema/definition: ksi_results_schema.json
- Evidence index: evidence_index.json
- 3PAO: 3pao_attestation.md
- Continuous reporting: continuous_monitoring_plan.md, conmon_pipeline.json
