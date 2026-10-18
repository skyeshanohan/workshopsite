# Design: enrich portfolio sections

## Context

The portfolio starter is intentionally thin: one `profile.js` file and three presentational themes. That is correct for a 3-hour first publish. Self-paced and returning students finish setup early and need more *content surface* without a harder toolchain.

A live prototype on `tyler-beach/example-my-resume-site` validates the data shape and theme rendering. This change ports the **behavior** into workshop starters with student-safe sample content.

## Data model (`profile.js`)

| Field | Type | Required for core path? | UI behavior |
|---|---|---|---|
| Existing fields (`name`, `role`, `projects`, …) | unchanged | Yes | unchanged |
| `badge` | `string` | No | Hero status chip when non-empty |
| `education` | `Array<{ school, degree, detail }>` | Yes (≥1) | Always rendered when length ≥ 1 |
| `certifications` | `Array<{ name, issuer?, detail? }>` | No | Section hidden if `[]` / missing |
| `honors` | `Array<{ title, detail? }>` | No | Combined with certifications as “Credentials & honors” when either has items |
| `interests` | `string[]` | No | Section hidden if empty |
| `learning` | `string[]` | No | Shown under interests block when non-empty |

### Compatibility

Layouts normalize:

```js
const education = Array.isArray(profile.education)
  ? profile.education
  : profile.education
    ? [profile.education]
    : [];
```

Starter sample ships only the array form. Guide copy tells students to copy/paste education objects like experience/projects.

## Theme placement

| Theme | Education | Credentials | Interests / learning | Badge |
|---|---|---|---|---|
| Developer | Dedicated timeline section after experience | Card grid; nav link only if shown | Tag rows; nav link only if shown | Hero badge from `profile.badge` |
| Editorial | Listed under about column | Extra band before projects | Tag band before projects | Replaces default eyebrow when set |
| Professional | Sidebar list (multi) | Main column section | Main column chips | Sidebar chip when set |

No new pages, components packages, or CSS frameworks.

## Student pacing

```
Core (everyone):   name/contact → skills → education[0] → 1–2 experience → 1–2 projects → photo → PR → Pages
Stretch (early):   more projects → more experience → certifications/honors → interests → learning → polish badge text
```

Stretch tasks are optional checkboxes in the student guide, not blockers for Step 5/6.

## Alternatives considered

1. **Separate “advanced ZIP”** — Rejected: doubles maintenance and confuses download step.
2. **Hardcoded second page** — Rejected: breaks single-file mental model and Pages path simplicity.
3. **Markdown content files** — Rejected: extra format for MIS beginners in a Git-first workshop.

## Implementation notes when applying

- Mirror prototype behavior from `tyler-beach/example-my-resume-site` themes, not Tyler’s Pathfinder colors or personal resume facts.
- Keep Developer default badge sample as something like `Open to internships` for the Jordan Lee persona.
- After starter edits, run workshop `npm run build` so `public/downloads/*.zip` update.
- Update Copilot prompts in the guide to mention optional arrays without requiring them.
