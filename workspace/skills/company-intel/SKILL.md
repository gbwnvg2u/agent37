# Company Intelligence

Gather health signals about companies with matched jobs — help users avoid wasting their growth roadmap on unstable companies.

## When to Use

- After job scanner finds matches (enrich with company context)
- User asks "tell me about [company]" or "is [company] a good place to work?"
- User is deciding between multiple offers/applications

## Instructions

### Company Research Process

1. **For each company with a matched job**, use `web_search` to gather signals:

   **Career Page & Job Descriptions (DO THIS FIRST):**
   - Search: "[company name] careers [role title] Singapore" (or user's location)
   - Find the actual job listing / career page URL
   - Extract: required skills, team info, specific responsibilities, tech stack mentioned
   - This is critical — the JD tells you exactly what they want, not what you guess

   **Growth & Stability:**
   - Search: "[company name] funding round 2025 2026"
   - Search: "[company name] layoffs OR hiring 2025 2026"
   - Search: "[company name] revenue growth"
   - Search: "[company name] series OR IPO OR acquisition"

   **Culture & Reputation:**
   - Search: "[company name] glassdoor reviews"
   - Search: "[company name] engineering culture" (for tech roles)

   **Recent News:**
   - Search: "[company name] news latest"
   - Look for: product launches, partnerships, leadership changes, controversies

2. **Classify signals:**

   **Green Flags:**
   - Recent funding round (growing)
   - Active hiring / team expansion
   - Positive Glassdoor trends
   - New product launches / market expansion
   - Strong leadership stability

   **Red Flags:**
   - Recent layoffs (especially multiple rounds)
   - Hiring freeze
   - Leadership turnover
   - Negative press / lawsuits
   - Declining revenue signals

   **Neutral:**
   - Stable, no major news (can be good or boring)
   - Acquisition rumors (uncertain outcome)

3. **Present to user** as a brief signal summary alongside each job:

```
🟢 [Company A]: Series C ($50M) in Jan 2026, engineering team +40%, Glassdoor 4.2/5
🔴 [Company B]: 2 rounds of layoffs in 6 months, CEO departed Nov 2025
🟡 [Company C]: Stable, no major news. Public company, consistent hiring.
```

4. **Save company intel** to `memory/companies.md` for reference:

```markdown
# Company Intelligence

## [Company Name]
- **Signal**: 🟢 Green / 🔴 Red / 🟡 Neutral
- **Key Facts**: [1-2 sentence summary]
- **Last Updated**: [date]
```

### Key Principles

- Be concise — 2-3 bullet points per company, not a full report
- Red flags are more important than green flags (protect the user's time)
- Update company data when rescanning — signals change
- If limited info found, say so: "Limited public data — small/stealth company"
