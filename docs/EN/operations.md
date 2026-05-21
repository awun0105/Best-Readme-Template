<!-- 
OPERATIONS TEMPLATE
===================
Focus: Health, metrics, logs, background jobs, and incident management.

AGENT EXECUTION PROTOCOL:
1. Identify health endpoints, logging formats, and job backends.
2. Resolve [brackets].
3. Clean up instructional notes.
-->

# Operations Guide

This document explains how to inspect and operate **[Project Title / Name]** once it is running.

## Health Monitoring

Inspect system health via the API:

```bash
curl http://localhost:[PORT]/health
```

Health response typically includes:
- `status`: High-level API status.
- **[Component 1 Status]**: [e.g., Database connectivity].
- **[Component 2 Status]**: [e.g., Model load state].

*Note: [Optional note about lazy-loading or specific startup behaviors].*

## Metrics

Expose Prometheus metrics for monitoring:

```bash
curl http://localhost:[PORT]/metrics
```

**Metric Groups:**

| Metric | Meaning |
|---|---|
| `[Metric Name 1]` | [Description of what is being counted/measured] |
| `[Metric Name 2]` | [Description] |

*Note on Availability: The `/metrics` endpoint typically requires `[ENV_VAR_NAME]=true` to be active.*

## Logging

- **Local Development**: Usually uses `text` format for readability.
- **Production**: Recommended `json` format for structured logging and aggregation.

**Request Tracking:**
Each request is assigned a unique ID. Look for the `X-Request-ID` header in responses to correlate API calls with backend logs.

## Background Jobs

*If the project uses a task queue (e.g., Redis/RQ, Celery, Cron), document how to manage jobs here.*

### 1. Starting a Job
```bash
curl -X POST http://localhost:[PORT]/api/v1/[job-path] \
  -H "X-API-Key: $API_KEY" \
  -d '{"param": "value"}'
```

### 2. Monitoring Status
```bash
curl -H "X-API-Key: $API_KEY" \
  http://localhost:[PORT]/api/v1/[job-path]/<job_id>
```

**Status Meanings:**
- `queued`: Accepted, waiting for a worker.
- `running`: Currently being processed.
- `completed`: Success.
- `failed`: Terminal failure; inspect logs for details.

## Common Incidents / Troubleshooting

### API Returns 401 (Unauthorized)
**Cause**: API key is missing or incorrect.
**Check**: Ensure `[ENV_VAR_NAME]` matches the key sent in the header.

### Job Is Stuck in Queued
**Cause**: Worker process is not running or connected to the wrong queue/database.
**Action**: Check worker container status and `[ENV_VAR_NAME]` configuration.

### [Issue 3 Name, e.g., Slow Response]
**Cause**: [Description].
**Action**: [Troubleshooting steps].

---

<div align="center">

[Back to Documentation Index](README.md)

</div>
