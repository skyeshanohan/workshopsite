# Change: enrich portfolio sections for a fuller resume + self-paced stretch

## Outcome

Give workshop portfolio starters the sections a real one-page resume site usually has—multi-entry education, credentials/honors, interests, and optional “currently learning”—while keeping beginners on a single-file `profile.js` path. Use empty optional lists to hide sections so early finishers have productive stretch work without increasing setup friction for first-time VS Code/GitHub users.

## Scope

- Extend `starters/portfolio/src/data/profile.js` with:
  - `badge` (optional hero status string)
  - `education` as an **array** of `{ school, degree, detail }`
  - `certifications` as an array of `{ name, issuer?, detail? }`
  - `honors` as an array of `{ title, detail? }`
  - `interests` as a string array
  - `learning` as a string array (stretch)
- Update **Editorial**, **Developer**, and **Professional** themes to render the new fields.
- Hide credentials, interests, and learning sections when their lists are empty; hide hero badge when `badge` is empty/absent.
- Accept legacy single `education` object by normalizing to a one-item list in layouts (compat during migration).
- Ship sample student-friendly stretch content in the starter `profile.js` (campus clubs, certifications-in-progress, hobbies)—not Tyler’s production resume content.
- Update student guide with optional “stretch” tasks after the core personalize step; note self-paced early-finisher path in facilitator guide.
- Rebuild theme ZIPs via existing packaging so downloads include the enriched starter.

## Non-goals

- Multi-page routing, blog, CMS, or new npm dependencies.
- Changing GitHub Actions / Pages deploy mechanics.
- Requiring students to fill every new section to complete the workshop.
- Porting Pathfinder-specific palette or Tyler Beach personal content into workshop starters.
- Building a separate “advanced track” codebase.

## Acceptance criteria

- Each theme shows projects, experience, about/skills, contact **and** multi-entry education when provided.
- Optional sections (credentials/honors, interests, learning) appear only when their arrays have items.
- `badge` is editable from `profile.js` and does not require editing theme Astro files for the common case.
- Sample starter data includes at least one stretch-ready interest and one learning item so early finishers see what to edit.
- Student guide documents core path vs stretch path without blocking the 3-hour critical path.
- `npm run build` for the workshop site regenerates ZIPs that contain the new `profile.js` shape.
- Narrow viewport layouts still stack without horizontal overflow for the new sections.

## Risks and rollback

- **Breaking change:** `education` object → array. Mitigate with layout normalization for a single object during one release; document the array form as the only sample in `profile.js`.
- Extra nav links can crowd the Developer header on small screens—wrap nav (already present) and only show optional anchors when sections exist.
- Stretch content can distract beginners—keep stretch clearly labeled “optional / if you finish early” in the guide.

Rollback: revert the change branch; prior ZIPs remain in git history. Prototype remains on `tyler-beach/example-my-resume-site` for reference.

## Decisions needing review

1. Confirm the optional field set: `badge`, multi-`education`, `certifications`, `honors`, `interests`, `learning` (vs dropping honors or learning).
2. Confirm sample starter copy should stay student-persona (Jordan Lee) with campus-appropriate stretch examples.
3. Confirm whether the student guide gets a dedicated “Stretch track” subsection or inline callouts only.

## Prototype reference

Implemented and published for review:

- Repo: https://github.com/tyler-beach/example-my-resume-site
- Live: https://tyler-beach.github.io/example-my-resume-site/
- PR: https://github.com/tyler-beach/example-my-resume-site/pull/3
