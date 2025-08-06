# AWS Egress Estimate

A tool for visualizing and analyzing AWS network egress costs and data transfer patterns.

## ⚠️ Important Disclaimer

**These are estimates only, intended for educational purposes and general cost planning.** Actual AWS costs may vary significantly based on:
- Real-world usage patterns
- AWS pricing changes
- Regional differences
- Specific service configurations
- Data transfer volumes and timing

Always consult official AWS pricing documentation and use AWS Cost Explorer for accurate billing information.

## Overview

This project provides HTML-based reports and network diagrams to help understand AWS egress charges and optimize network architecture for cost efficiency.

## Files

- `src/index.html` - Main dashboard and cost analysis interface
- `src/aws-egress-report.html` - Detailed egress cost report
- `src/network-diagram.html` - Interactive network topology diagram

## Usage

1. Open any of the HTML files in your browser to view the reports
2. The main interface is `src/index.html`
3. Use the network diagrams to visualize data flow and potential cost optimization opportunities

## Regional Configuration

The cost estimates are currently based on **US-East-1 (N. Virginia)** pricing. To adjust for other AWS regions:

### Easy Configuration via config.json:
Simply edit `src/config.json` to update pricing for your region. All pricing rates are configurable:

```json
{
  "region": {
    "name": "EU-West-1 (Ireland)",
    "code": "eu-west-1"
  },
  "pricing": {
    "internet": {
      "freeThreshold": 100,
      "rates": [
        { "threshold": 10000, "rate": 0.09 },
        { "threshold": 50000, "rate": 0.085 },
        { "threshold": 150000, "rate": 0.07 },
        { "threshold": 999999999, "rate": 0.05 }
      ]
    },
    "interAZ": 0.01,
    "interRegion": 0.02,
    "crossAccount": 0.01,
    "vpcPeering": 0.01,
    "transitGateway": 0.02,
    "directConnect": 0.02,
    "vpnTransfer": 0.09,
    "privateLink": 0.01,
    "cloudFront": 0.085,
    "natGateway": 0.045,
    "apiGateway": 0.09,
    "s3DynamoNAT": 0.135,
    "s3DynamoGateway": 0,
    "interfaceEndpoints": 0.01
  }
}
```

### Configurable Pricing Components:
- **Internet egress tiers**: Tiered pricing for data transfer to internet
- **Inter-AZ transfers**: Cross-availability zone data transfer
- **Inter-region transfers**: Cross-region data transfer
- **VPC peering**: VPC-to-VPC communication costs
- **Transit Gateway**: Centralized connectivity hub costs
- **NAT Gateway**: Network address translation processing
- **CloudFront**: CDN data transfer costs
- **API Gateway**: API data transfer costs
- **VPC Endpoints**: Private connectivity costs
- And more...

### Regional Pricing Resources:
- [AWS Data Transfer Pricing](https://aws.amazon.com/ec2/pricing/on-demand/#Data_Transfer)
- [CloudFront Pricing](https://aws.amazon.com/cloudfront/pricing/)

### Common Regional Adjustments:
- **Asia Pacific regions**: Generally 10-20% higher egress costs
- **Europe regions**: Similar to US-East-1 with minor variations  
- **South America/Middle East**: Typically 15-30% higher costs

## Features

- Interactive HTML reports for egress cost analysis
- Network topology visualization
- Educational tool for understanding AWS data transfer costs
- Regional cost estimation capabilities