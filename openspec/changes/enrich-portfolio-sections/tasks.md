## Specification
- [x] 1.1 Capture proposal, design, and requirements for enriched profile sections + self-paced stretch
- [x] 1.2 Publish a living prototype on `tyler-beach/example-my-resume-site` for visual review before template apply

## Apply to workshop starters (do after prototype approval)
- [ ] 2.1 Update `starters/portfolio/src/data/profile.js` with `badge`, education array, certifications, honors, interests, learning + student-safe sample stretch content and comments
- [ ] 2.2 Update Student, Emerging, and Professional themes to render new fields; hide empty optional sections; normalize legacy education object
- [ ] 2.3 Keep hero/status badge driven by `profile.badge` (default sample: internship-oriented for Jordan Lee persona on Student/Emerging)
- [ ] 2.4 Rebuild theme ZIPs (`npm run build` / package-starters) and verify ZIP `profile.js` contains the new fields

## Docs and facilitation
- [ ] 3.1 Add optional stretch tasks to the student guide after core personalize (certification, interest, learning, extra project)
- [ ] 3.2 Note mixed-pace / early-finisher stretch redirection in facilitator guide
- [ ] 3.3 Update Copilot “one improvement” prompt examples to allow optional array edits without requiring them

## Verification
- [ ] 4.1 Local `npm run build` inside starter with full sample data for each theme
- [ ] 4.2 Confirm empty `certifications`/`honors`/`interests`/`learning` hide sections
- [ ] 4.3 Confirm legacy single `education` object still renders
- [ ] 4.4 Smoke narrow-viewport layout for new sections
- [ ] 4.5 Confirm workshop site downloads serve updated ZIPs after Pages deploy
