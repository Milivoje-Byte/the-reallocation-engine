# search/gaps.md

Delta between attested `resume.json` and the target role in `profile.yml`
(quantitative economist/data scientist, SOC 19-3011 / 15-2051 / 15-2041,
H-1B sponsorship required as hard gate, STEM OPT extension ending
2027-01-15, 45/90 unemployment days used).

Drafted by agent, reviewed by candidate on 2026-06-25.

---

## Gap Table

| # | Gap | Evidence the target demands it | What I have | Plan to close it |
|---|-----|-------------------------------|-------------|-------------------|
| 1 | **FY2027 H-1B cap lottery window has already closed for new registrations.** Registration ran March 4–19, 2026; selections were announced by March 31, 2026; the petition filing window (April 1–June 30, 2026) closes in ~5 days from today. A new cap-subject H-1B cannot be initiated for this cycle. | USCIS official registration/filing timeline for FY2027; multiple immigration-law sources confirm the same dates (registration closed, selections out, petition window ending June 30, 2026). | A target role identification (SOC 19-3011/15-2051/15-2041) and a profile that requires sponsorship, but no live cap-subject H-1B registration in progress for this cycle. | This is not closeable by building a project or credential — it is a timing fact. The plan is to pivot active search toward (a) **cap-exempt employers** (universities, Federal Reserve Banks, RAND, Brookings, Urban Institute — confirmed cap-exempt categories under INA §214(g)(5)) who can file H-1B petitions year-round without the lottery, and (b) employers who can do a same-fiscal-year **H-1B transfer** if the candidate already holds cap-subject H-1B status from a prior count — which does not apply here, so cap-exempt is the primary near-term path. Closes when: an active application or conversation is underway with at least one specific cap-exempt employer (not just a category). |
| 2 | **New wage-weighted H-1B lottery system (effective Feb 27, 2026) changes registration strategy for the *next* cycle (FY2028, ~March 2027).** Selection is now weighted by DOL wage level — Level III/IV wages get substantially better odds (DHS estimates suggest Level IV could see ~65-70% selection vs. ~10-12% for Level I) — but FY2028 registration falls *after* the candidate's STEM OPT extension end date (2027-01-15) unless a cap-exempt bridge is secured first. | USCIS final rule (effective Feb 27, 2026) and multiple immigration-law summaries of the FY2027 cap season confirm the wage-weighted mechanics and that the next registration window opens ~March 2027. | Wage data already in `resume.json`-adjacent research (mode-design file): SOC 19-3011 P75 $132,870, SOC 15-2051 P75 $145,000 — likely Level III/IV range, which is favorable *if* a registration can happen. | The plan is not a credential — it's a sequencing decision. Target cap-exempt employers first to bridge the gap between OPT end date and the FY2028 lottery, so that if a cap-subject opportunity arises later, status is already secured independently. Closes when: cap-exempt employment is secured, removing dependence on the lottery timing entirely. |
| 3 | **No confirmed H-1B sponsorship history attached to any specific employer in the candidate's current target list.** `profile.yml` now gates on sponsorship: a company with no sponsorship history is skip-regardless. The candidate's `resume.json` and mode-design file reference target employers (Analysis Group, Cornerstone Research, RAND, Brookings, Urban Institute, Amazon econ teams) but none of these have been checked against actual current LCA filing data in this exercise — only against figures from the candidate's earlier mode-design assignment (filed under a different, hypothetical run). | The gap is evidenced by web search confirming that economist/data-scientist roles are commonly H-1B sponsored at consulting firms, Fed Reserve Banks, and tech econ teams (Migrate Mate visa-sponsorship listings; H1B Data Hub top-sponsor lists for data-scientist LCAs), but no employer-specific, current-year LCA count has been pulled for *this* candidate's actual target list as of June 2026. | Mode-design file's `filter_sponsors.py` simulated output (not a live run) showing illustrative LCA counts for some of the same employers — explicitly labeled simulated, not real, in that file. | Closes when the engine's `filter_sponsors.py` is actually run (not simulated) against `data/h1b_sponsors.csv` for the candidate's real target employer list, producing a current, dated LCA count per employer that can be cited here by filename and run date — not reused from the earlier simulated output. |
| 4 | **No econ-soc-sponsor-tracker.py equivalent has been run to estimate P(SOC code | employer) for any of the candidate's specific target employers**, meaning the wage-floor identification problem the candidate's own mode-design file is built around remains theoretically described but not actually computed for this candidate's real situation. | The candidate's own mode-design file documents this script as proposed but not yet built (`scripts/jobops/econ-soc-sponsor-tracker.py` — NOT AVAILABLE). | The conceptual framework and formula (`P(SOC=X|employer=E) ≈ LCA_count(E,X) / Σ LCA_count(E,SOC_j)`) already exists in the candidate's own prior work. | Closes when this script exists and is actually run — even a manual spreadsheet cross-tab of `h1b_sponsors.csv` by employer × SOC code for the candidate's top 5 target employers would satisfy this, producing a dated table the candidate could defend in an interview. |
| 5 | **The Northeastern M.S. in Applied Mathematics (Data Science & ML) is in progress, not complete**, and `resume.json` correctly flags this — but no specific coursework, project, or deliverable from this degree has yet been added as a separate verifiable line in `resume.json`. A general "in progress" degree entry is weaker signal than specific demonstrated coursework/projects for SOC 15-2051 (Data Scientist) roles, which weight applied ML skills more heavily than the econ PhD alone. | O*NET task statements for 15-2051 (Data Scientists) emphasize applied machine learning and statistical programming deliverables, not just coursework enrollment — this is a general pattern from the occupation profile, not a single posting. | An in-progress degree entry with no project-level evidence yet. | Closes when a specific project from this M.S. (e.g., a course paper, a coding project, a thesis chapter) is completed and added to `resume.json` as a new dated entry with a verifiable artifact (GitHub repo, paper, or grade), at which point this gap row is deleted. |

---

## Required Edits

### Killed Row — Candidate Confirmed

**Original gap (removed): "Candidate lacks demonstrated industry (non-academic) work experience, which most data scientist and economist job postings implicitly prefer over a purely academic CV."**

**Why this was wrong (candidate-confirmed reason, 2026-06-25):** I do have industry experience — the J.P. Morgan Chase internship and the MathWorks Lab advisory work count. This gap doesn't apply to me.

### Rewritten Row — Candidate Confirmed

**Original (agent draft):** *"Gap: Candidate's target employers in profile.yml have not been checked for current H-1B sponsorship history. Evidence: general claims that economists and data scientists are commonly sponsored. What I have: simulated script output from a prior assignment. Plan: run filter_sponsors.py for real."*

**Rewritten by candidate (confirmed 2026-06-25 as accurate in their own words):**

> The real problem isn't that I don't know economists get sponsored in general — it's that I don't know, *right now, for the specific 5-6 employers I actually care about*, whether their sponsorship history is current and whether they file under 19-3011 or 15-2051 for someone with my background. My own mode-design file already built the method for answering this. I just haven't run it on myself yet, with real data, for my real target list, this month. That's the actual gap: I designed the tool and didn't use it on my own search before this exercise forced me to notice that.

---

## Notes on Evidence Discipline

- Gaps 1 and 2 are the most consequential findings in this file and were discovered through live web search during this exercise — they were **not** present in the candidate's mode-design file, which predates the FY2027 lottery timeline becoming concrete. This is itself worth logging: the candidate's prior assignment, written in early June, is now partially out of date on a load-bearing timeline fact.
- Gap 3 explicitly distinguishes between the candidate's prior *simulated* script output and what a *real* run would produce — these are not the same evidentiary standard, and the table does not pretend otherwise.
- No gap in this table is closed by "take a course." Each plan column specifies a verifiable artifact or event (a real script run, a secured cap-exempt application, a specific completed project) consistent with the assignment's instruction that courses are inputs, not evidence.
Let me know once that's committed, and we'll move on to the .gitignore edit and the RUN_LOG.md append.You said: It does not paste wellIt does not paste well5:21 AMClaude responded: Let's troubleshoot this without guessing.Let's troubleshoot this without guessing. "Doesn't paste well" could mean a few different things, so let's narrow it down.You said: Q: What does "doesn't paste well" look like specifically?Q: What does "doesn't paste well" look like specifically?
A: Line breaks/paragraphs collapse into one giant line5:21 AMClaude responded: That's a known quirk — GitHub's "Create new file" web editor (CodeMirror) sometimes treats a pasted block as one continuous paste-event and depending on your b…That's a known quirk — GitHub's "Create new file" web editor (CodeMirror) sometimes treats a pasted block as one continuous paste-event and depending on your browser/OS clipboard handling, newline characters can get stripped or interpreted oddly, especially with large blocks of markdown containing long table rows.
A few things to try, roughly in order of how likely they are to just work:
1. Try pasting with a keyboard shortcut instead of right-click paste

Click inside the editor box first, then use Ctrl+Shift+V (Windows) or Cmd+Shift+V (Mac) — "paste as plain text." Some browsers preserve line breaks better this way than a normal Ctrl+V/Cmd+V.
2. Try a smaller paste first to isolate the problem

Paste just the first few lines (the header through "Drafted by agent...") and see if line breaks survive. If yes, the problem is likely the giant table rows specifically (some browsers choke on very long single lines in a paste buffer). If no, it's a broader clipboard/editor issue.
3. Use the "Upload files" method instead of "Create new file"

This sidesteps the editor entirely:

Save the gaps.md content I gave you into a plain text file on your own computer first (open Notepad/TextEdit, paste the content there, save as gaps.md)
On GitHub, go to your repo, click Add file → Upload files
Drag that saved gaps.md file into the upload box, but — important — you need it to land in the search/ folder. Since search/ already exists now (from your two earlier commits), you can navigate into https://github.com/Milivoje-Byte/the-reallocation-engine/tree/main/search first, then use Add file → Upload files from inside that folder view, so the upload goes to the right path.
Commit.

Option 3 is the most reliable since it avoids the browser-paste-into-editor step entirely. Want to try that, or try the plain-text-paste trick first since it's faster?
