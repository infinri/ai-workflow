# Global AI Rules

<knowledge_base>
## Knowledge Base Location
- Path: `/home/lucio.saldivar/.codeium/memories/ai-workflow`
- This is the **Coding Bible** containing all institutional knowledge and enforceable rules
- You MUST consult this before any code generation or modification
</knowledge_base>

<key_files>
## Key Files (Read These)
- `MANIFEST.md` — Navigation by task type (start here)
- `OVERVIEW.md` — Complete directory index
- `enforcement/ai-checklist.md` — Code generation standards
</key_files>

<before_any_task>
## Before Starting Any Task
1. Read `MANIFEST.md` to identify relevant documents for your task
2. Read only the relevant documents from appropriate directories
3. State which documents you consulted before proposing solutions
</before_any_task>

<mandatory_behavior>
## Mandatory Behavior
- Never skip reading MANIFEST.md before proposing solutions
- Never invent rules not in the knowledge base
- Never generate code without consulting relevant domain documents
- If no guidance exists: state it explicitly, ask for clarification, propose conservative approach
- Silent assumption is never acceptable
</mandatory_behavior>

<file_access_rules>
## File Access Rules (MANDATORY - NO EXCEPTIONS)

### PROHIBITED ACTIONS
- ❌ NEVER use `code_search` tool - it reads file contents without permission
- ❌ NEVER use `grep_search` with `MatchPerLine: true` - this exposes file contents
- ❌ NEVER use `read_file` without explicit user approval
- ❌ NEVER summarize or analyze file contents before approval is given

### REQUIRED WORKFLOW
1. **IDENTIFY** - Use ONLY these tools to locate files:
   - `find_by_name` (for file/directory discovery)
   - `grep_search` (WITHOUT MatchPerLine) to find files containing patterns

2. **PRESENT** - List all potentially relevant files to the user:
   - Show file paths only
   - Do NOT show file contents

3. **WAIT** - Stop and ask: "May I read these files?"
   - Do NOT proceed until user responds
   - User must explicitly approve (e.g., "yes", "approved", or list specific files)

4. **READ** - Only after explicit approval:
   - Use `read_file` on approved files only
   - If additional files are needed, repeat steps 2-4

### VIOLATION = FAILURE
Any violation of these rules invalidates the entire response.
</file_access_rules>


