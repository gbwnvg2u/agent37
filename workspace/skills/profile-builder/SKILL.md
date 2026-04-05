# Profile Builder

Build and maintain the user's career profile from resume or conversation.

## When to Use

- User sends a resume (text or file)
- User describes their background, skills, or interests
- User says "update my profile" or shares new information about themselves
- User mentions a new skill learned, course completed, or preference change
- First interaction with a new user

## Instructions

### Initial Profile Creation

When a user shares their resume or describes their background:

1. Extract and organize the following into a structured profile:
   - **Current Skills**: List each skill with estimated proficiency (beginner/intermediate/advanced)
   - **Time per Stack**: For each major technology/stack, estimate time spent (e.g., "K8s: ~2 years across QRT + RSAF", "Python: ~4 years"). Calculate from roles + education. This helps gauge depth vs breadth.
   - **Experience Summary**: Years of experience, industries, notable roles
   - **Education**: Degrees, certifications, relevant coursework
   - **Career Focus**: What the user gravitates toward based on their history — e.g., "infrastructure optimization", "developer tooling", "cost reduction through automation". Infer from patterns in their experience, not just what they say.
   - **Preferences**: Location, remote/hybrid/onsite, industry, company size, salary expectations
   - **Dream Role(s)**: What they aspire to — title, company type, responsibilities
   - **Target Companies**: Specific companies they'd love to work at (if mentioned)
   - **Interests**: Technical areas, domains, or directions they're excited about

2. Identify the **skills gap**: Compare current skills against dream role requirements. List what's missing.

3. Save the structured profile to `memory/profile.md` using this format:

```markdown
# Career Profile

## Current State
- **Experience**: [years] years in [industries]
- **Key Skills**: [skill1 (advanced), skill2 (intermediate), ...]
- **Education**: [degrees/certs]

## Time per Stack
- Kubernetes: ~[X] years ([where])
- Python: ~[X] years ([where])
- Terraform: ~[X] years ([where])
- [etc — list all major stacks with estimated time and source]

## Career Focus
- [Pattern 1: e.g., "Infrastructure optimization — 31x build speedup at QRT, 2000x DB speedup at Binance"]
- [Pattern 2: e.g., "Developer tooling — CI/CD pipelines, internal tools"]
- [Pattern 3: e.g., "Cost reduction — $2.5k/month savings at QRT via lifecycle policies"]

## Aspirations
- **Dream Role**: [title at type of company]
- **Target Companies**: [list]
- **Interests**: [list]

## Preferences
- **Location**: [location/remote]
- **Salary Range**: [range or "open"]
- **Company Size**: [startup/mid/enterprise/any]
- **Industry**: [preferred industries]

## Skills Gap (Current → Dream)
- [ ] Skill A — not started
- [ ] Skill B — beginner, needs intermediate
- [ ] Skill C — not started

## Match Score
- **Current Match %**: [calculated]
- **Last Updated**: [date]
```

4. Confirm the profile with the user: show them a summary and ask if anything needs adjustment.

### Profile Updates

When the user shares new information (completed a course, changed preferences, etc.):

1. Check the current profile in `memory/profile.md` (use the full path: memory/profile.md)
2. Update the relevant sections
3. Recalculate the match % if skills changed
4. Confirm the update: "Updated your profile — [skill] is now at [level]. Match % is now [X]%."

### Match % Calculation

- Analyze the user's dream role(s) and extract required skills as a weighted checklist
- Weight by importance: must-have skills weighted higher than nice-to-have
- Verified skills (passed quiz) count at 100%
- Self-reported skills count at 70%
- Missing skills count at 0%
- Match % = weighted sum of matched skills / total weighted requirements
