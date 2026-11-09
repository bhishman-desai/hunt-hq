# Hunt HQ

Read this file first. It is the setup order and the map of this repository. The other files are the team rules. Load them as written. Do not rewrite them to fit a vendor.

This kit runs on any orchestrator that can give each agent a standing role, a shared filesystem, a mailbox connector, and a schedule. The human owner is Bhishman. He approves every message that leaves the team.

The shared hunt root in every file is `/workspace/hunt`. `~/hunt` is a symlink to that directory. Keep those paths so the role files resolve. Durable files stay under `/workspace/hunt`.

## Repository map

| File in this repo | Copy to |
| --- | --- |
| `charter/CHARTER.md` | `/workspace/hunt/CHARTER.md` |
| `preferences/preferences.md` | `/workspace/hunt/preferences.md` |
| `profile/tailor-rules.md` | `/workspace/hunt/profile/tailor-rules.md` |
| `state/tracker.json` | `/workspace/hunt/tracker.json` |
| `state/suppression.txt` | `/workspace/hunt/suppression.txt` |
| `roles/hunt-chief.md` | Standing role for Hunt Chief |
| `roles/job-scout.md` | Standing role for Job Scout |
| `roles/lead-prospector.md` | Standing role for Lead Prospector |
| `roles/resume-tailor.md` | Standing role for Resume Tailor |
| `roles/pitch-writer.md` | Standing role for Pitch Writer |
| `roles/mailroom.md` | Standing role for Mailroom |

Role files are agent instructions. They are not copied into `/workspace/hunt`, except `profile/tailor-rules.md`, which Resume Tailor reads from disk on every tailoring task.

Each role file ends with a save-confirmation token, `HUNTROLE_OK`. That token only checks that the full role arrived. It is not a hunt step.

## Files the operator adds

These three files are the owner's material. They are not in this repository. Put them in `/workspace/hunt/profile/` before any tailoring:

- `skeleton.md`, the immutable fact base
- `skeleton.tex`, the immutable résumé layout
- `cover-letter-reference.docx`, the Word cover-letter reference

Then copy `skeleton.md` to `/workspace/hunt/profile/master-resume.md`. Do not edit `skeleton.md`, `skeleton.tex`, or the Word file. Do not copy `master-resume.md` back over `skeleton.md`.

`/workspace/hunt/profile/projects.md` is built in step 6. It is not in this repository.

Item work lands in `/workspace/hunt/items/<ID>-<slug>/`. The role files name the files inside an item folder: `item.md`, `contacts.md`, `research.md`, `resume.tex`, `resume.pdf`, `cover.tex`, `cover.pdf`, `review.md`, `email.md`, `proposal.md`, and `audit.md`.

## Setup order

1. Read `charter/CHARTER.md`, then `preferences/preferences.md`.
2. Create `/workspace/hunt/profile` and `/workspace/hunt/items`. Point `~/hunt` at `/workspace/hunt`.
3. Copy the files in the map above to the runtime paths.
4. Add the three operator files, then make `master-resume.md` as a copy of `skeleton.md`.
5. Create the six agents in this order and load each role file in full. Hunt Chief, Job Scout, Lead Prospector, Resume Tailor, Pitch Writer, Mailroom. Hunt Chief coordinates. The others act only when Hunt Chief or Bhishman assigns the step.
6. Have Resume Tailor write `/workspace/hunt/profile/projects.md` from the public repositories named in `skeleton.md`. One entry per repository: name, link, problem, stack, what the README says was learned, and the README URL. Leave `skeleton.md` untouched.
7. Connect the owner's mailbox. Mailroom is the only agent that uses it. Record that address in `preferences.md` if it is not already there. Leave the outreach footer and email signature lines as the placeholders in that file until Bhishman replaces them.
8. Open one group named Hunt HQ that contains all six agents and Bhishman. Handoffs in that group name one owner.
9. Schedule only what the role files already describe.
   - Hunt Chief, weekdays at 7:30 AM America/Toronto: the daily hunt in `roles/hunt-chief.md`. The digest is posted in Hunt HQ.
   - Hunt Chief, Friday at 4:00 PM America/Toronto: the weekly review in that same file.
   - Mailroom, weekdays 9:00 AM to 7:00 PM America/Toronto, every 2 hours: the reply watch in `roles/mailroom.md`.
   - Mailroom, weekdays at 10:00 AM America/Toronto: the follow-ups in that same file.
10. Run one hunt by hand in Hunt HQ before relying on the weekday schedule. Use the active caps in `preferences.md`.

A new schedule waits for its next matching time. It does not hunt at the moment it is saved.

## Owner commands

Say these to Hunt Chief, in Hunt HQ or in Hunt Chief's own chat:

- `go J2 G1 L3` starts the picked items. `J` is a job, `G` is a gig, `L` is a small-business lead.
- `skip L4` drops an item.
- `approve J2` sends the finished package to Mailroom.
- `fix J2: <notes>` returns the notes to Resume Tailor for the résumé and cover letter, or to Pitch Writer for the emails.
- `send O5` is the only instruction that lets Mailroom send outbound message `O5`, and the platform approval still has to be given.
- `prep J2`, `status`, `pause`, and `resume` are defined in `roles/hunt-chief.md`.

## Who writes what

- Hunt Chief is the only writer of `/workspace/hunt/tracker.json`.
- Mailroom is the only writer of `/workspace/hunt/suppression.txt`.
- Job Scout writes job and gig `item.md` files and `contacts.md`.
- Lead Prospector writes lead `item.md` files.
- Resume Tailor writes `resume.tex`, `resume.pdf`, `cover.tex`, `cover.pdf`, and `review.md` inside the item folder.
- Pitch Writer writes `email.md`, `proposal.md`, and `audit.md`.

## Stops

Stop and ask Bhishman when a login, CAPTCHA, price, schedule, eligibility gap, or missing profile file appears. Do not invent a fact, an email address, or a metric. Do not submit an application form. Do not send mail until Bhishman types `send O#` and approves it.
