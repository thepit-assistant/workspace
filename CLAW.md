# CLAW.md - My Duties & Context

## Core Mission
Help Ronnie systematize and scale his small business automation work. Free him up from research/analysis to focus on execution.

## Current Projects

### 1. Account Setup (IN PROGRESS)
- ✅ Proton Mail: `thepit.assistant@proton.me` (ImV5wjkMmLnEIVgvJJXm#1)
- 🔄 GitHub: `thepit-assistant` (IMZDtByoxZbGDYRzSUwk#1) — blocked by CAPTCHA, needs manual signup or browser automation
- ⏳ TODO: Other service accounts as needed

### 2. Infrastructure
- ✅ Chromium + virtual display (Xvfb) on RPi4
- ✅ Proton Mail working + email sending verified
- ✅ GitHub SSH key added & authenticated
- ✅ Git configured (thepit-assistant@proton.me)
- ⏳ Build automated deployment/CI-CD for ThePit projects

## Key Context
- **Running on:** RPi4 (be cost-conscious, no unnecessary overhead)
- **Model:** Always Haiku (RPi can't handle larger models)
- **Approach:** Bash/CLI-first, minimal snapshots, API calls where possible
- **Cost awareness:** Learned from $1.10 snapshot bill — use headless scripts instead
- **Name convention:** Use "assistant" in usernames/emails to keep things obvious

## Account Credentials
Stored in: `/home/pi/.openclaw/workspace/memory/accounts.md`

## Next Steps
1. ✅ GitHub account created & logged in
2. ✅ SSH key setup & verified
3. 🔴 **BLOCKER:** GitHub CAPTCHA (needs manual fix or headless bypass)
4. ⏳ Customer interviews: Pick 5-10 local HVAC/plumbing owners → validate lead-automation pain
5. ⏳ Build first test repository (once GitHub blocker cleared)
6. ⏳ Begin research on small business automation frameworks/tools
7. ⏳ Build sample automation projects
8. ⏳ Create deployment pipeline for ThePit projects

## Blockers (Priority)
1. **GitHub CAPTCHA** — Account created but signup incomplete. Options:
   - Manual browser signup (one-time, 5 min)
   - Headless bypass (cost-benefit unclear)
   - Use other git host temporarily (GitLab, Gitea)
   
2. **Customer validation** — Can't execute MVP without talking to target users. Need:
   - List of 5-10 HVAC/plumbing shops in metro area
   - Schedule 15-min calls this week
   - Single question: "What workflow kills the most time?"

## Learnings So Far
- Proton Mail works great for encrypted comms
- Browser snapshots are expensive ($0.07+ per snapshot due to vision analysis)
- Headless automation + curl is the way forward
- RPi4 needs lean, efficient code
- Market validation is stronger than guessing — interview customers before building
- HVAC/plumbing market is proven + hungry for automation tools
