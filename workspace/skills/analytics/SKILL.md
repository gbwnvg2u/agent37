# Analytics & Progress

Show users their compound growth over time. The hero metric is match % trend.

## When to Use

- Weekly digest (triggered by cron)
- User asks "show my progress", "how am I doing?", "stats", "analytics"
- After a milestone (e.g., match % crosses 80%, skill gap closed)

## Instructions

### Progress Report Generation

1. **Gather data from:**
   - `memory/profile.md` — current skills and match %
   - `memory/roadmap.md` — completed actions, verification history, match % history
   - `memory/shared/jobs-latest.md` — recent job matches and categories

2. **Calculate key metrics:**
   - **Match % trend**: Current vs. last week vs. when they started
   - **Skills acquired**: Count of verified skills since starting
   - **Skills remaining**: Gaps still on the roadmap
   - **Gap closure rate**: Skills verified per week
   - **Jobs in range**: How many strong matches (>85%) now vs. when started
   - **Streak**: Consecutive days of completed actions

3. **Present the digest:**

   **Daily (after verification):**
   ```
   ✅ Verified! Match: [X-1]% → [X]%
   🔥 Streak: [N] days
   ```

   **Weekly digest:**
   ```
   📊 Weekly Progress Report
   
   Match %: [X]% (+[N]% this week)
   ━━━━━━━━━━━━━━━━━━━━
   [visual progress bar]
   
   🎯 This Week:
   • [N] skills verified
   • [N] daily actions completed
   • [N] new jobs now in your range
   
   📈 Since You Started:
   • Match: [start]% → [current]% (+[total]%)
   • [N] skills verified out of [M] identified gaps
   • [N] more jobs in range than when you started
   
   💡 Key Insight:
   [One actionable observation, e.g., "Your fastest growth area is backend skills — 
   3 verified this week. Frontend gaps remain the biggest blocker for your dream role."]
   
   Keep compounding! 1.01^[days] = [calculated value] 🚀
   ```

   **On milestone:**
   ```
   🎉 Milestone! You just crossed [X]% match!
   [N] new jobs are now strong matches that weren't when you started.
   ```

4. **Save analytics snapshot** to `memory/analytics.md`:
   ```markdown
   # Analytics
   
   ## Latest Snapshot ([date])
   - Match %: [X]%
   - Total skills verified: [N]
   - Streak: [N] days
   - Jobs in range: [N]
   
   ## Weekly History
   - Week of [date]: [X]% (+[N]%)
   - Week of [date]: [X]% (+[N]%)
   ```

### Key Principles

- The match % trend IS the product — make it prominent and satisfying
- Always show relative improvement (vs. last week, vs. start) — people need to see progress
- The 1.01^N calculation is a fun motivator — include it
- Keep it scannable — the weekly digest should take 30 seconds to read
- Celebrate milestones — crossing 10% thresholds, completing skill areas, streaks
