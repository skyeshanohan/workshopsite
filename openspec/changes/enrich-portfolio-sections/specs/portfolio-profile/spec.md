## ADDED Requirements

### Requirement: Support multi-entry education in profile data
The portfolio starter MUST represent education as a list of school entries. Each theme MUST render every provided education entry with school, degree, and detail. Layouts MUST accept a legacy single education object by treating it as a one-item list so existing student repos do not crash during migration.

#### Scenario: Multiple schools render
- **GIVEN** `profile.education` is an array with two or more entries
- **WHEN** a visitor opens the portfolio in any theme
- **THEN** each entry’s school, degree, and detail are visible
- **AND** the page does not require editing theme files to add another school

#### Scenario: Legacy single education object still works
- **GIVEN** `profile.education` is a single object with `school`, `degree`, and `detail`
- **WHEN** the site builds and renders
- **THEN** that one education entry appears
- **AND** the build does not fail

### Requirement: Optional credentials and honors sections
The starter MUST allow `certifications` and `honors` arrays in `profile.js`. Themes MUST show a credentials/honors section when either array contains items. Themes MUST omit that section (and its nav link, if any) when both arrays are missing or empty.

#### Scenario: Student adds a certification
- **GIVEN** `certifications` contains at least one `{ name }` object
- **WHEN** the student refreshes the local preview
- **THEN** the certification name is visible in the credentials area
- **AND** optional `issuer` / `detail` fields appear when provided

#### Scenario: Empty credentials stay hidden
- **GIVEN** `certifications` and `honors` are both `[]` or omitted
- **WHEN** the portfolio renders
- **THEN** no credentials/honors heading or empty card grid is shown

### Requirement: Optional interests and learning sections
The starter MUST allow `interests` and `learning` string arrays. Themes MUST show an interests/learning area when either array has items, and MUST hide it when both are empty or omitted.

#### Scenario: Early finisher adds interests
- **GIVEN** `interests` includes one or more strings
- **WHEN** the preview refreshes
- **THEN** those interests appear as readable labels or chips
- **AND** beginners who leave the list empty do not see an empty section

#### Scenario: Currently learning stretch content
- **GIVEN** `learning` includes one or more strings
- **WHEN** the interests/learning area is shown
- **THEN** a “currently learning” (or equivalent) grouping includes those items

### Requirement: Data-driven hero badge
Themes that show a status badge MUST read it from `profile.badge` when present. When `badge` is empty or omitted, Developer MUST not show a misleading hardcoded internship badge; Editorial MAY keep a generic eyebrow fallback.

#### Scenario: Custom badge text
- **GIVEN** `badge` is set to a non-empty string
- **WHEN** the Developer theme renders
- **THEN** that string appears as the hero badge

#### Scenario: No badge configured
- **GIVEN** `badge` is `''` or omitted
- **WHEN** the Developer theme renders
- **THEN** the internship/status badge element is not shown

### Requirement: Preserve core resume sections and deployability
Existing projects, experience, skills, about, photo, and contact behavior MUST remain. The site MUST remain a static Astro build deployable with the existing GitHub Pages workflow. New sections MUST remain usable on a narrow viewport without horizontal page overflow.

#### Scenario: Core path still completes
- **GIVEN** a student only fills existing core fields plus one education entry
- **WHEN** they build and deploy with the workshop Actions workflow
- **THEN** the live site shows their core content successfully
- **AND** optional empty sections do not appear as broken placeholders
