# Job Scanner

Find jobs worth the user's attention — strategic fit, not volume.

## When to Use

- Scheduled daily scan (triggered by cron)
- User asks "find me jobs", "what's new today", "scan for jobs"
- User updates their profile or preferences (rescan with new criteria)

## Instructions

### Job Search Process

1. **Check the user's profile** in `memory/profile.md` to understand:
   - Target roles and skills
   - Location and remote preferences
   - Industry and company size preferences
   - Dream role requirements

2. **Search for jobs** using the `web_search` tool. Run multiple searches:
   - Search 1: "[dream role title] [location] jobs site:linkedin.com"
   - Search 2: "[dream role title] [preferred industry] remote jobs"
   - Search 3: "[key skills] [location] hiring"
   - Search 4: "[target company names] careers [dream role]" (if target companies exist)
   - Adjust queries based on user preferences

3. **For each job found**, extract:
   - Job title
   - Company name
   - Location (and remote status)
   - Key requirements from the JD
   - Posted date
   - Application link

4. **Reason about strategic fit** for each job (this is where you add real value):
   - Does this role align with their career trajectory, not just their current skills?
   - Is it a stepping stone toward their dream role?
   - Does the company/industry match their interests?
   - Are the gaps closeable in a reasonable timeframe?

5. **Categorize each match**:
   - **Strong Match (>85%)**: Skills align well, ready to apply
   - **Strategic Stretch (70-85%)**: Gaps exist but are closeable — these feed the career coach
   - **Below 70%**: Filter out, don't show to user

6. **Save results** to `memory/shared/jobs-latest.md`:

```markdown
# Job Scan — [date]

## Strong Matches
### [Job Title] at [Company]
- **Match**: [X]%
- **Location**: [location]
- **Key Fit**: [why this matches]
- **Link**: [url]

## Strategic Stretches
### [Job Title] at [Company]
- **Match**: [X]%
- **Gap**: [what's missing]
- **Why Strategic**: [how this fits their trajectory]
- **Link**: [url]
```

7. **Report to user** with a concise digest:
   - Lead with the count: "Found X jobs worth your attention today"
   - Show top 3-5 matches with one-line summaries
   - For stretches, highlight the specific gap: "You're 78% matched — missing [skill]. This feeds into today's growth action."

### Important Notes

- Quality over quantity: 3 great matches > 20 mediocre ones
- Always explain WHY a job is worth their attention
- Flag if a company appeared in previous scans (they're actively hiring = good signal)
- If no good matches found, say so honestly and suggest broadening/adjusting criteria
