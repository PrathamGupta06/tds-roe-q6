# Multi-Platform Matrix Build with Artifacts

This repository demonstrates a GitHub Actions workflow with matrix build strategy for multi-platform CI/CD.

## Contact Information
Email: 23f3001608@ds.study.iitm.ac.in

## Workflow Overview

The workflow builds the project across multiple platforms and Node.js versions:

### Matrix Configuration
- **Operating Systems**: Ubuntu, macOS, Windows
- **Node.js Versions**: 18, 20
- **Total Build Variants**: 6 (3 OS × 2 Node versions)

### Features
- ✅ Parallel execution across all matrix variants
- ✅ Unique artifact generation for each build variant
- ✅ Cross-platform compatibility (Linux, macOS, Windows)
- ✅ Artifact naming with prefix: `build-5d5602f-<variant>`
- ✅ Build metadata and system information capture
- ✅ Workflow identifier: `matrix-5d5602f`

### Artifacts Generated
Each matrix job produces:
1. `output.txt` - Build information and system details
2. `metadata.json` - Structured build metadata

Artifact naming pattern:
- `build-5d5602f-linux-node18`
- `build-5d5602f-linux-node20`
- `build-5d5602f-macos-node18`
- `build-5d5602f-macos-node20`
- `build-5d5602f-windows-node18`
- `build-5d5602f-windows-node20`

## Running the Workflow

The workflow triggers on:
- Push to `main` or `master` branch
- Pull requests to `main` or `master` branch
- Manual trigger via workflow_dispatch

## Viewing Results

After the workflow completes, you can:
1. Check the Actions tab to see all 6 parallel jobs
2. Download artifacts from the workflow run summary
3. Review build logs for each matrix variant

## Local Testing

While this is a GitHub Actions workflow, you can verify the build steps locally:

```bash
# Create build directory
mkdir -p build

# Generate sample output
echo "Build Information" > build/output.txt
echo "OS: $(uname -s)" >> build/output.txt
echo "Node Version: $(node --version)" >> build/output.txt
echo "Build Time: $(date)" >> build/output.txt
```

## Validation Checklist
- [x] At least 3 matrix job variants
- [x] Parallel execution
- [x] Artifact generation with unique content
- [x] Artifact naming with `build-5d5602f` prefix
- [x] Step identifier `matrix-5d5602f`
- [x] README with contact email
