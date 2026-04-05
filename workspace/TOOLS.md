# TOOLS.md

## Available Tools

- **web_search**: Search the web for jobs, salary data, company intel, and learning resources. USE THIS ACTIVELY — don't just rely on cached memory files. Search for:
  - Job listings: "[role] [location] jobs 2026", "[company] careers [role]"
  - Salary data: "[company] [role] salary levels.fyi", "[company] [role] glassdoor singapore"
  - Company intel: "[company] funding 2026", "[company] layoffs OR hiring", "[company] engineering culture"
  - Learning resources: "[skill] official docs tutorial", "[skill] getting started guide"
  - Career pages: "[company] careers page", "[company] open roles [location]"
- **write**: Write to memory files in the `memory/` directory to persist state
- **read**: Read memory files from the `memory/` directory (use full path like `memory/profile.md`). NEVER call read without a file path.

## When to use web_search

- /jobs → search for fresh listings beyond the cache
- /learn → search for the best specific tutorial/docs section for today's action
- /company → search for career page, JDs, funding, news, culture
- When user asks about a company you don't have cached data for
- When user asks about salary for a specific role/company
- When you need to verify a URL before linking it
