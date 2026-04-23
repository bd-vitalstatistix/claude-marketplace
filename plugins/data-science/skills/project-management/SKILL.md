---
description: JIRA and project management standards for the Black Duck Data Science team
disable-model-invocation: false
---

# Project Management Standards

## JIRA Configuration

- **cloudId**: `739838e2-f328-4f14-a533-3f7d49323638`
- **Primary project**: `DS` (Data Science)
- **Account**: bolster@blackduck.com

## Ticket Reference Format

Always use `PROJECT-###` format in communications and weeknotes:
- `DS-1234` for Data Science tickets
- `CR-567` for cross-referenced issues

## Creating Issues

```python
mcp__atlassian__createJiraIssue(
    cloudId="739838e2-f328-4f14-a533-3f7d49323638",
    projectKey="DS",
    issueTypeName="Task",  # or "Bug", "Story"
    summary="Imperative verb phrase (50 chars)",
    description="Context and acceptance criteria",
    contentFormat="markdown",
    additional_fields={"priority": {"name": "Medium"}}
)
```

## When to Create Tickets

- Any blocker mentioned in weeknotes without a JIRA link → create the ticket
- External dependencies that need tracking
- Multi-step work items that span sessions
- Follow-up actions from meetings with named owners

## Searching Issues

```python
mcp__atlassian__searchJiraIssuesUsingJql(
    cloudId="739838e2-f328-4f14-a533-3f7d49323638",
    jql='project = DS AND status != Done ORDER BY updated DESC',
    fields=["summary", "status", "assignee", "priority"],
    maxResults=20,
    responseContentFormat="markdown"
)
```

## Issue Transitions

Find available transitions:
```python
mcp__atlassian__getTransitionsForJiraIssue(
    cloudId="739838e2-f328-4f14-a533-3f7d49323638",
    issueIdOrKey="DS-123"
)
```

Then transition:
```python
mcp__atlassian__transitionJiraIssue(
    cloudId="739838e2-f328-4f14-a533-3f7d49323638",
    issueIdOrKey="DS-123",
    transition={"id": "<transition_id>"}
)
```

## Summary & Reporting

For blockers in weeknotes:
- Always provide JIRA link, not just ticket number
- Explain the context, not just the ticket title
- Group related blockers when they share a root cause

For in-flight items:
- Name specific team members (Tim, Conor) and their ownership
- Include target dates where known

## Team Communication

**Microsoft Teams** channels accessed via WorkIQ:
- LLM Gateway Users channel: budget requests, user issues
- Data Science team channel: team updates and coordination

**WorkIQ lookup for context**:
```python
mcp__workiq__ask_work_iq(question="[question about recent activity]")
```

Use `conversationId` from response for follow-up questions in the same session.
