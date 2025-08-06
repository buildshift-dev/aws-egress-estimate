# AWS Egress Estimate

A tool for visualizing and analyzing AWS network egress costs and data transfer patterns.

## Overview

This project provides HTML-based reports and network diagrams to help understand AWS egress charges and optimize network architecture for cost efficiency.

## Files

- `src/index.html` - Main dashboard and cost analysis interface
- `src/aws-egress-report.html` - Detailed egress cost report
- `src/network-diagram.html` - Interactive network topology diagram
- `src/network-diagram-simple.html` - Simplified network diagram view
- `src/network-diagram-original.html` - Original network diagram format

## Usage

1. Open any of the HTML files in your browser to view the reports
2. The main interface is `src/index.html`
3. Use the network diagrams to visualize data flow and potential cost optimization opportunities

## Development

To publish changes to the buildshift-dev repository:

```bash
# Copy files only
./copy_publish.sh

# Copy files and deploy to GitHub
./copy_publish.sh --deploy

# Copy files and deploy with custom commit message
./copy_publish.sh --deploy --message "Updated cost analysis"
```

The publish script automatically excludes:
- `prompts/` folder
- `copy_publish.sh` script
- Files listed in `.deploy-ignore` (if present)
- Files listed in `.gitignore` (if present)

## Features

- Interactive HTML reports for egress cost analysis
- Network topology visualization
- Multiple diagram formats for different use cases
- Easy deployment to external repositories