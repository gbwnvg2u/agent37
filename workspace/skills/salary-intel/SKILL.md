# Salary Intelligence

Infer compensation for jobs that don't list salary by cross-referencing US market data.

## When to Use

- After job scanner finds matches (enrich each match with salary data)
- User asks "what does this pay?" or "salary estimate for [role] at [company]"
- User asks to compare compensation across matched jobs

## Instructions

### Salary Inference Process

1. **For each matched job**, use `web_search` to find salary data:

   **Primary method — US Pay Transparency:**
   - Search: "[company name] [similar role title] salary New York site:linkedin.com"
   - Search: "[company name] [role title] salary site:glassdoor.com"
   - Search: "[company name] careers [role] New York OR San Francisco OR Colorado"
   - Why: US states like NYC, California, Colorado require salary ranges in job postings. Same company + similar role = strong inference.

   **Secondary method — Market data:**
   - Search: "[role title] [industry] salary range [year]"
   - Search: "[role title] salary site:levels.fyi" (for tech roles)
   - Search: "[company name] salary reviews site:glassdoor.com"

   **Contextual adjustments:**
   - Consider company stage: startup vs. FAANG vs. mid-size
   - Consider funding round: "Series A startup" pays differently than "public company"
   - If user's market is different from US, note the cost-of-living adjustment

2. **Present salary estimate with confidence level:**

   - **High confidence**: Found the exact company's US posting for same/similar role
     - "Estimated: $120K-$150K (high confidence — found NYC posting for same role)"
   - **Medium confidence**: Found similar roles at similar companies, or Glassdoor data
     - "Estimated: $90K-$110K (medium confidence — based on Glassdoor + similar companies)"
   - **Low confidence**: Only general market data available
     - "Estimated: $80K-$120K (low confidence — market average, no company-specific data)"

3. **Add comparative context:**
   - "This is 20% above market average for your level"
   - "Similar to what [other matched company] likely pays"
   - If multiple matches: rank by estimated compensation

4. **Save salary data** alongside job data in `memory/jobs-latest.md` under each job entry.

### Key Principles

- Always state your confidence level — never present an estimate as definitive
- The US cross-reference trick is the primary differentiator — lead with it when data is available
- If no data found, say so: "Couldn't find salary data for this specific role. Market range for similar positions is $X-$Y."
- Remember: salary data helps users prioritize which jobs to pursue, not just satisfy curiosity
