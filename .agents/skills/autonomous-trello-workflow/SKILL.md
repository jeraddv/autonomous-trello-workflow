---
name: autonomous-trello-workflow
description: An autonomous agent pipeline that fetches Trello tickets, designs UI mockups, and writes technical implementation plans.
---

# Autonomous Trello Workflow

This skill instructs the Orchestrator on how to process a Trello ticket using our permanent, global sub-agents.

## Workflow Execution

When the user asks to process a Trello ticket, follow these exact steps:

1. **Verify Agents:** The `consultant_planner` and `expert_designer` are permanently defined in the global rules directory. You do not need to define them.
2. **Dispatch:** Use the `invoke_subagent` tool to spawn the `consultant_planner`. Pass it the board and ticket information requested by the user. 
3. **Let it run:** The `consultant_planner` will autonomously fetch the ticket, invoke the `expert_designer`, consult the user on the tech stack, write the plan, and post it to Trello.