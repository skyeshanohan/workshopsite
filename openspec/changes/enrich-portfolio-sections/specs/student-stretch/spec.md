## ADDED Requirements

### Requirement: Document a self-paced stretch path
The student guide MUST distinguish the core personalize path (required for workshop completion) from optional stretch edits that use the new profile fields. Stretch instructions MUST stay optional and MUST NOT be required checkboxes for Steps 5–6.

#### Scenario: Early finisher finds stretch work
- **GIVEN** a student has finished core profile fields, photo, and local preview checks
- **WHEN** they continue reading the personalize / stretch portion of the guide
- **THEN** they see concrete optional tasks such as adding a certification, an interest, or a learning item
- **AND** they are told these tasks are optional if time remains

#### Scenario: Beginner is not blocked
- **GIVEN** a student is still completing first-time setup
- **WHEN** they follow the numbered core steps
- **THEN** they can reach pull request and Pages without filling interests, certifications, honors, or learning

### Requirement: Provide sample stretch content in the starter
The packaged theme ZIP `profile.js` MUST include example entries for at least interests and learning (student persona, not facilitator personal data) so early finishers can edit by example instead of inventing structure.

#### Scenario: Edit by example
- **GIVEN** a student opens a freshly unzipped theme project
- **WHEN** they inspect `interests` and `learning` in `profile.js`
- **THEN** they see non-empty sample arrays they can replace
- **AND** comments explain that emptying a list hides the section

### Requirement: Facilitator awareness for mixed pace rooms
Facilitator materials MUST note that self-paced / experienced students can be steered to stretch sections after their first successful local preview, while others remain on setup and core profile edits.

#### Scenario: Facilitator redirects early finishers
- **GIVEN** a participant already knows VS Code and GitHub and has a working local preview
- **WHEN** the facilitator needs to keep them occupied without advancing the whole room
- **THEN** facilitator notes point to the stretch profile fields and optional second pull request (for example, “Add interests section content”)
