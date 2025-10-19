# FAQs — WTX Library of 200+ n8n Automation Templates

A clear, practical FAQ to help you install, customize, and get value fast.

## General

### What is this project?
A curated library of 200+ ready-to-use n8n automation templates that streamline sales, marketing, ops, finance, support, analytics, HR, and IT workflows.

### Who is it for?
Founders, agencies, RevOps, finance, support, data teams, and solo builders who want leverage without rebuilding flows from scratch.

### Do I need to be an n8n expert?
No. Templates are beginner-friendly with clear node names and comments where relevant.

### Does it work with n8n Cloud and self-hosted n8n?
Yes—both are supported.

### What version(s) of n8n are supported?
Templates use stable nodes and patterns compatible with recent n8n versions. Always test on your current version before going live.

---

## Installation & Setup

### How do I import a template?
1) Download a template JSON file.  
2) In n8n, go to “Import from File” and select the JSON.  
3) Update credentials, environment variables, and trigger settings.

### What prerequisites do I need?
- An n8n instance (cloud or self-hosted)  
- API keys/credentials for any services you want to integrate (e.g., Slack, Gmail, HubSpot, Stripe, Notion)

### How do I configure credentials securely?
Use n8n Credentials and environment variables. Do not hardcode secrets in nodes. Restrict access to your n8n instance.

### Can I run multiple templates together?
Yes. You can chain workflows (call one from another) or copy/paste nodes across flows to build end-to-end pipelines.

### How do I enable triggers safely?
Start in manual mode for testing. Validate inputs/outputs, add error branches, then enable triggers once stable.

---

## Customization & Best Practices

### How do I tailor a template to my stack?
- Replace or configure app nodes (CRM, email, chat, billing, DB)  
- Adjust filters/conditions and field mappings  
- Add notifications (Slack/Email) on success/failure  
- Map your specific data schemas

### How do I handle errors and retries?
- Use n8n’s Error Workflow feature  
- Configure retry settings on nodes that call external APIs  
- Add failure branches to notify Slack/Email with context

### What about rate limits?
Use delay nodes, batching, and pagination. Many templates are prepped with rate-limit-friendly patterns, but you may need to tune them per API.

### How do I version control my workflows?
Export JSON and commit to Git. Consider tagging releases and keeping a CHANGELOG for important updates.

---

## Integrations & Compatibility

### Which services are supported?
Most common SaaS tools across CRM, marketing, finance, support, analytics, docs, and communication. For anything without a native node, use the HTTP Request node to hit any REST API.

### Will templates break after n8n updates?
Rarely. We rely on stable nodes and conventions. Still, check n8n release notes before major upgrades and test in staging.

### Can I swap one app for another (e.g., HubSpot → Pipedrive)?
Yes. Replace the CRM node(s) and adjust field mappings. The logic pattern typically stays the same.

---

## Data & Security

### Do templates store or transmit my data to external servers?
No. Templates run in your n8n environment; you control data and credentials. Review each node’s destinations and apply least-privilege access.

### How do I protect PII and secrets?
- Use encrypted credentials in n8n  
- Limit who can access your n8n instance  
- Mask logs where sensitive fields appear  
- Consider data minimization and retention policies

---

## Performance & Reliability

### Are these production-ready?
They’re designed with production in mind, but every stack is different. Validate against your data size, SLAs, and API quotas; add monitoring and alerting.

### How do I monitor workflows?
- Send run summaries to Slack/Email  
- Log key metrics to a database or a monitoring tool  
- Set alerts on failure branches and long runtimes

---

## Licensing & Commercial Use

### Can I use these templates commercially?
Yes—subject to this repo’s license. If you plan to sell or redistribute, review the license terms carefully.

### Do you offer Pro (paid) packs?
Optionally, yes. Pro packs typically include commercial rights, priority support, and advanced templates. See the repository README for current offerings.

### Can I redistribute or resell templates?
- Community edition: follow the open-source license terms  
- Pro edition: redistribution is typically prohibited; see the Pro license

---

## Support & Contributions

### How can I get help?
Open a GitHub Issue or Discussion with:
- Goal and expected outcome  
- Apps/services involved  
- Sample input/output (scrub sensitive data)  
- Error messages or screenshots

### Do you offer consulting or custom builds?
Yes—installation, integration audits, and bespoke automations. See the README “Support & Custom Work” section.

### How can I contribute a template?
Open a PR and include:
- Clear description and category tags  
- Example input/output  
- Required credentials  
- Notes on limits or caveats

---

## Troubleshooting

### Import fails with “invalid JSON” or similar
- Ensure the file wasn’t altered by copy/paste  
- Re-download the raw JSON  
- Validate the JSON structure

### Nodes fail with 401/403 errors
- Refresh or recreate credentials  
- Verify scopes/permissions in the connected app  
- Check IP allowlists and OAuth redirect URIs if applicable

### Rate limits or timeouts
- Add delays/batching  
- Implement retries with backoff  
- Split large jobs into smaller chunks or scheduled batches

### Data mapping issues (missing fields, nulls)
- Inspect the incoming payload with a Set node  
- Add Field Mappings/If branches for optional data  
- Normalize data types before DB writes
