# ModelAudit Security Reports

Security scan reports for three GGUF models, generated using [Promptfoo ModelAudit](https://github.com/promptfoo/modelaudit) v0.2.54 on Ubuntu 24.04 (WSL2).

## Repository Structure

```text
modelaudit-reports/
├── qwen/                  # Qwen3.5-9B (Q4_K_M)
├── granite/               # Granite-4.2-8B (Q4_K_M)
├── gemma/                 # Gemma-4-E4B-it (Q5_K_M)
├── environment.json       # Test environment and dependencies
├── modelaudit-version.txt # ModelAudit version
├── scanners-doctor.txt    # Scanner diagnostics
└── scanners-list.json     # Available scanners
```

Each model folder contains:

- **Basic & Strict scans:** GGUF security scan results.
- **Repository scan:** Model files, documentation, and metadata checks.
- **SBOM:** CycloneDX component and license inventory.
- **Metadata:** Model information and security-related metadata.
- **Corrupted model test:** Detection of invalid GGUF files.

## Results

| Model          | GGUF Scans | Corrupted Model Test |
| -------------- | ---------- | -------------------- |
| Qwen3.5-9B     | Passed     | Detected             |
| Granite-4.2-8B | Passed     | Detected             |
| Gemma-4-E4B-it | Passed     | Detected             |

**All three original GGUF models passed the applicable static security checks with no findings.** All three corrupted files were detected successfully.

Repository scans produced additional documentation-related findings: incomplete coverage for Qwen, informational findings for Granite, and a CRITICAL `git clone` detection in Gemma's README.

The repository contains the generated reports and diagnostics, not the model weights or inference code.
