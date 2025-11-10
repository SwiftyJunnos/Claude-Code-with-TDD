---
description: Manage Claude skills (list, add, delete)
---

# Skills Management Command

This command helps manage Claude skills in your project.

## Usage

- `/skills` or `/skills list` - List all available skills in `.claude/skills/`
- `/skills list-available` - List all available skills in the claude-skills repository
- `/skills add <category> <skill-name>` - Add a skill from claude-skills repository
- `/skills delete <skill-name>` - Delete a skill from `.claude/skills/`

## Arguments Provided

{{{input}}}

---

## Execute the command

Based on the arguments provided above, execute the appropriate skill management operation:

### If listing current skills (no args or "list"):
1. Use Bash to list all skills in `.claude/skills/` directory
2. Show each skill with its target path
3. Format output in a readable way

### If listing available skills ("list-available"):
1. Use Bash to explore the claude-skills repository structure
2. List all available skills organized by category (common, backend, frontend)
3. Show which skills are already installed

### If adding a skill ("add <category> <skill-name>"):
1. Validate the category (common, backend, or frontend)
2. Check if the skill exists in `../../../claude-skills/<category>/<skill-name>`
3. Check if the skill already exists in `.claude/skills/`
4. Create a symlink: `ln -s ../../../claude-skills/<category>/<skill-name> .claude/skills/<skill-name>`
5. Confirm successful addition

### If deleting a skill ("delete <skill-name>"):
1. Check if the skill exists in `.claude/skills/`
2. Remove the symlink: `rm .claude/skills/<skill-name>`
3. Confirm successful deletion

Make sure to handle errors gracefully and provide helpful feedback to the user.
