RESUME TAILOR RULES
Read this file before every tailoring task. These rules override memory if they conflict.

INPUTS (required): the job description in the item folder item.md, /workspace/hunt/profile/skeleton.tex, /workspace/hunt/profile/master-resume.md (a copy of skeleton.md), /workspace/hunt/profile/projects.md, /workspace/hunt/profile/cover-letter-reference.docx, and the item research.md if present. If the job description, skeleton.tex, master-resume.md, or the cover-letter reference is missing, stop and ask @Hunt Chief. Never work from memory. Never edit skeleton.md, skeleton.tex, or cover-letter-reference.docx.

RESUME RULES (copy skeleton.tex to <folder>/resume.tex and edit only that copy; keep the skeleton's layout, fonts, and macros)
1. Experience: choose at most the 3 roles out of the 6 in master-resume.md that best match the job description. Drop the rest.
2. Every bullet follows "Did X by using Y, resulting in Z". Lead with impact, never with "owned", "supported", or "helped with". Wrap metrics and numbers in \textbf{}, and wrap the key technology in each bullet in \textbf{}.
3. Use only facts and metrics present in master-resume.md, skeleton.md, or projects.md. You may reword, reorder, cut, and reframe for the job. If a bullet needs a metric that does not exist, flag it in review.md and ask Bhishman for the real number. Never invent one.
4. ATS keywords: extract the job description's hard skills and tools. Put every keyword Bhishman genuinely has into Skills, using the job description's exact wording, and weave the most important ones into bullets. Keep technology in bullets balanced with Skills: some repetition is fine, not a lot. A keyword he lacks never goes on the resume; list it under Gaps instead.
5. Projects: at most 1. Pick the project from projects.md that best matches the job description, with exactly 2 bullets: (1) the problem it solves, (2) what he learned, mainly about the technologies used.
6. Professional summary: write it LAST, from the final bullets. At most 2 sentences: start with his experience across the industries he has worked in (startups and MNCs, and how he helped them), then the key strengths for this job and his strongest accomplishments. Be specific, not general.
7. Cut anything that does not support this role. A recruiter skimming for 7 seconds must see what he does, what problems he solves, and why he fits.
8. Compile: run tectonic <folder>/resume.tex. The PDF must be exactly 1 page with no LaTeX errors or overfull lines; fix and recompile until it is clean. If tectonic is missing, reinstall it on this cloud computer and put the binary on PATH via /workspace/bin. Do not install it on the user's Mac.
9. Keep the skeleton's formatting. If the page has empty space, fill it with role-relevant facts from the allowed sources. Do not add filler.

COVER LETTER RULES
Read cover-letter-reference.docx for voice, length, and structure. Do not edit that Word file. There is no cover-letter.tex master. Write a new <folder>/cover.tex. Use the header styling from skeleton.tex so the letter matches the resume. Compile to cover.pdf, 1 page.
Plain, simple English with simpler words, so it reads as human. No dash punctuation anywhere. No setup-and-negate sentences. Four paragraphs:
1. An eye-catching opening: something from his experience that the job description asks for, tied to why he is interested.
2. What the company does and why he wants to work there, from research (cite sources in review.md, not in the letter).
3. What makes him different and why they should pick him. Say something unique and specific.
4. A short thank you. Use this paragraph to acknowledge one thing from the job description that helps him stand out, for example a technology he lacks that he is ready to learn.

RECRUITER REVIEW LOOP (do not skip)
After each draft, review it as the strict recruiter for this exact job: would you advance this candidate? Score ATS keyword coverage, relevance of each bullet, metrics, story clarity in a 7-second scan, the summary, and the cover letter. Revise and recompile. Stop when you have no reason left to reject it, or after 3 rounds.
Write review.md: VERDICT (ACCEPT or REJECT), keyword coverage (matched / missing), what changed and why, Gaps (requirements he does not meet, stated bluntly), metrics you need from Bhishman, and honest advice (including "skip this job" when the fit is weak).
Report to @Hunt Chief: "[ID] resume + cover ready" with resume.pdf, cover.pdf, review.md paths and the verdict in one line. On "fix" notes, apply them, rerun the review loop, and report again.

Standing prohibitions:
- Never invent or inflate any experience, metric, title, employer, skill, or credential.
- Never put a skill on the resume that master-resume.md, skeleton.md, or projects.md does not support.
- Resume and cover letter are each exactly 1 page, compile cleanly, and use no dash punctuation in the cover letter.
- Be brutally honest in the verdict; never soften a REJECT.
