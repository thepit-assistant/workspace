# TASKS.md - Actionable Task Queue

## Queue (In Priority Order)

### IMMEDIATE (This Week)

#### 1. Build HVAC Prospect List
- [ ] Search Google Maps: "[Your City] HVAC contractors" → save top 20 results
- [ ] Extract: Business name, phone, owner name (if visible), address
- [ ] Filter: <20 employees only (target small shops)
- [ ] Create CSV: name | phone | owner | address | notes
- [ ] File: `/home/pi/.openclaw/workspace/prospects/hvac-[city].csv`
- **Owner:** Ronnie or Claw  
- **Time:** 1-2 hours  
- **Done when:** CSV has 15-20 qualified prospects

#### 2. Script Customer Interview Calls
- [ ] Write 3-5 core questions:
  1. "What's the biggest time waster in your business right now?"
  2. "How many leads do you lose per month? (estimate)"
  3. "What would you pay to recover 10% of those leads?"
  4. "Want to be a beta customer if we built this?"
- [ ] Create simple call script (1 page, conversational)
- [ ] Document answers template (Google Sheet or markdown)
- File: `/home/pi/.openclaw/workspace/research/interview-script.md`
- **Owner:** Ronnie (you'll do calls, I'll doc)  
- **Time:** 30 min  
- **Done when:** Script is written and ready to use

#### 3. Schedule First 5 Customer Calls
- [ ] Call prospect #1-5 from CSV (or Claw can cold email intro)
- [ ] Goal: Schedule 15-min calls (phone or Zoom)
- [ ] Dates: This week (Mar 10-14) preferred
- [ ] Track: Calendar invites + email confirmations
- [ ] Backup: If no response in 2 hours, try next prospect
- **Owner:** Ronnie (calls), Claw (tracking)  
- **Time:** 30 min  
- **Done when:** 3-5 calls scheduled

#### 4. Conduct & Log Interview #1
- [ ] Call scheduled prospect
- [ ] Use interview script
- [ ] Record notes: pain, volume, willingness to pay, beta interest
- [ ] File: `/home/pi/.openclaw/workspace/research/interviews/hvac-[prospect-name]-[date].md`
- [ ] Update tally: `/home/pi/.openclaw/workspace/research/interview-tally.md` (count pain mentions)
- **Owner:** Ronnie  
- **Time:** 30 min per call  
- **Done when:** Notes filed + tally updated

#### 5. GitHub CAPTCHA Workaround
- [ ] Option 1: Manual signup via browser (no automation, just finish signup flow)
  - [ ] Open browser, go to github.com/join
  - [ ] Complete signup for `thepit-assistant`
  - [ ] Verify email
  - [ ] Add SSH key to account
- OR Option 2: Use GitLab temporarily
  - [ ] Create account at gitlab.com
  - [ ] Create first repo: thepit-automation-templates
  - [ ] Note: Switch to GitHub once CAPTCHA is done
- **Owner:** Claw or Ronnie  
- **Time:** 10 min  
- **Done when:** Account active + SSH key added

---

### NEXT PHASE (After 5 Interviews Complete)

#### 6. Analyze Interview Data
- [ ] Read all 5 interview notes
- [ ] Tally: Pain points mentioned (frequency), willingness to pay (range), timeline needs
- [ ] Identify: #1 pain point (build MVP around this)
- [ ] Create summary: `/home/pi/.openclaw/workspace/research/interview-summary.md`
  - Top 3 pains (ranked by frequency + severity)
  - Average willingness to pay
  - Timeline for MVP (what they need by)
  - Top 3 feature requests
- **Owner:** Claw  
- **Time:** 1 hour  
- **Done when:** Summary doc written + decision made on MVP scope

#### 7. Design MVP Workflow
- [ ] Document exact data flow:
  - Lead source: Web form? Phone? Both?
  - Form fields: (name, email, phone, service type, description, date needed)
  - Auto-response: SMS template text
  - Next step: Tech assignment or CRM entry?
  - Invoice trigger: When? (after job complete? After estimate?)
- [ ] Create flowchart: `/home/pi/.openclaw/workspace/mvp/workflow-diagram.md` (text or ASCII)
- [ ] List integrations needed: (n8n, Twilio, Zapier, whatever CRM they use)
- **Owner:** Claw + Ronnie  
- **Time:** 1-2 hours  
- **Done when:** Workflow doc finalized + integrations list clear

#### 8. Set Up n8n Workflow (MVP Build)
- [ ] Spin up n8n instance (local or cloud)
- [ ] Create trigger: Form submission webhook
- [ ] Add step 1: Extract form data
- [ ] Add step 2: Send SMS via Twilio
- [ ] Add step 3: Create contact in CRM (or spreadsheet)
- [ ] Test end-to-end: Submit form → SMS arrives
- [ ] File: Export workflow JSON to `/home/pi/.openclaw/workspace/mvp/lead-automation-v1.json`
- **Owner:** Claw  
- **Time:** 4-6 hours  
- **Done when:** Test workflow runs, SMS is received

#### 9. Create First Test Repo
- [ ] GitHub or GitLab (whichever is active)
- [ ] Repo name: `thepit-hvac-automation`
- [ ] Add files:
  - [ ] README.md (setup instructions)
  - [ ] workflow.json (n8n export)
  - [ ] form-template.html (basic contact form)
  - [ ] sms-templates.md (example messages)
  - [ ] DEPLOYMENT.md (how to run)
- [ ] Push to main branch
- [ ] Test: Clone repo on another machine, verify it works
- **Owner:** Claw  
- **Time:** 2-3 hours  
- **Done when:** Repo public, README clear, tested

#### 10. Onboard First Beta Customer
- [ ] Pick best prospect from interviews (most pain + willing to beta)
- [ ] Schedule 1-hour setup call
- [ ] Steps:
  - [ ] Get their Twilio credentials (or create account for them)
  - [ ] Deploy workflow to their n8n
  - [ ] Test: Submit form on their website → SMS to their phone
  - [ ] Document their process (CRM used, tech names, etc.)
  - [ ] Schedule weekly check-in (iterate based on feedback)
- [ ] Track in: `/home/pi/.openclaw/workspace/customers/[name]-onboarding.md`
- **Owner:** Claw + Ronnie  
- **Time:** 3-4 hours  
- **Done when:** Customer has working form → SMS workflow, live

---

## Tracking

### Task Status Codes
- `[ ]` = Not started
- `[~]` = In progress
- `[x]` = Done

### Daily Progress (Log Here)
```
## Mar 9 (Day 1)
- [ ] Prospect list (0/15 qualified prospects)
- [ ] Interview script (not started)
- [ ] Calls scheduled (0/5)

## Mar 10
- [~] Prospect list (10/15 done)
- [~] Interview script (draft done, needs review)
- [ ] Calls scheduled (0/5)

(Update daily during heartbeat checks)
```

---

## Blockers & Dependencies

| Task | Blocked By | Unblocks |
|------|-----------|----------|
| Interviews | Prospect list | Interview analysis |
| Interview analysis | 5 completed calls | MVP design |
| MVP design | Interview analysis | n8n build |
| n8n build | MVP design | Test repo |
| Test repo | n8n build | Beta onboarding |
| Beta onboarding | Test repo + customer | Iteration cycle |

---

**Last Updated:** March 9, 2026 — 09:41 AM  
**Next Update:** Tomorrow (daily) + hourly heartbeat scans
