# JARVIS — DWC Personal AI Orchestrator

## Vision
A personal assistant that can be used through ChatGPT or Claude while a separate orchestration layer coordinates connected tools. The goal is to turn natural-language requests into supervised, trackable work: planning, code changes, design tasks, media workflows, testing, and delivery.

## Constraints
- Target budget: R$0/month.
- Primary device: Android phone.
- Prefer free tiers and open-source tools.
- Do not assume ChatGPT/Claude subscriptions include API credits.
- Do not store API keys, passwords, private tokens, or personal data in the repository.
- Never execute destructive, publishing, messaging, spending, or account-changing actions without explicit approval.

## Architecture direction: hybrid
1. **Conversation layer:** use the ChatGPT and Claude apps/interfaces the user already has.
2. **Project workspace:** GitHub repository for source files, plans, issues, and version history.
3. **Orchestration layer:** start with explicit, small workflows; later connect a workflow engine or MCP-compatible tools where available.
4. **Specialist tools:** coding, design, image/audio/video processing, and deployment tools, connected individually rather than assuming universal access.
5. **Approval gate:** preview intended actions and request confirmation for consequential operations.
6. **Result report:** summarize what changed, where the output is, what was tested, and what still needs a human.

## Build sequence
### Phase 0 — Foundation
- Document the goal, constraints, tool inventory, and safety rules.
- Keep the existing website files intact; they can become a future dashboard but are not the Jarvis itself.
- Separate documentation from any future runnable orchestrator.

### Phase 1 — First useful workflow
- Use GitHub as the first workspace because the user already has a repository.
- Define a request format: goal, input files/links, constraints, expected output, and approval level.
- Produce a task plan and maintain a task log before making code changes.
- Demonstrate one end-to-end workflow that can be operated from a phone.

### Phase 2 — Tool adapters
- Add one integration at a time, only after checking authentication, free-tier limits, mobile usability, and permissions.
- Prefer official integrations/APIs and MCP-compatible tools when supported.
- Treat each adapter as a limited capability, not unrestricted access to the user's accounts.
- Add retries, error reporting, and a clear record of actions.

### Phase 3 — Media workflows
- Start with low-risk actions such as organizing inputs, generating edit plans, captions, transcripts, and shot lists.
- Add actual video processing only after confirming a free, mobile-accessible execution environment.
- Never claim a video was edited unless an output file was actually produced and verified.

### Phase 4 — Voice and personal dashboard
- Add voice input/output and a dashboard only if they make the workflow more useful than using ChatGPT/Claude directly.
- Keep the interface lightweight and mobile-first.
- A custom interface does not automatically provide free model access; choose the model/runtime separately.

## Initial tool evaluation checklist
For each candidate, record:
- What it can actually do
- Whether it works from Android
- Whether the relevant features are free
- Whether it needs an API key or external hosting
- What permissions it needs
- Whether it can be triggered from an existing assistant
- Whether the user must approve actions

## Candidate categories (not yet connected)
- GitHub: version control and project workspace.
- MCP-compatible integrations: tool access where a supported connector and authorization exist.
- Workflow automation: only if a usable free tier and suitable hosting are confirmed.
- Open-source media tools: only when there is a realistic way to run them from the user's available device or free compute.
- Coding agents: compare phone access, execution environment, and actual costs before choosing one.

## Current status
- Repository exists and contains a static DWC AI Studio website.
- This roadmap is the first project artifact for the Jarvis direction.
- No personal assistant, automation backend, API integration, or video-editing pipeline has been deployed yet.
