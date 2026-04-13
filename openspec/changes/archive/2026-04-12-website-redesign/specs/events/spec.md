## ADDED Requirements

### Requirement: Events listing page
The events page at `/events/` SHALL display events in chronological order. Upcoming events (date >= build date) SHALL appear in the main section. Past events (date < build date) SHALL appear in a separate archive section on the same page.

#### Scenario: Upcoming events displayed
- **WHEN** a visitor navigates to `/events/` and upcoming events exist
- **THEN** upcoming events are listed chronologically in the main section with title, date, and location

#### Scenario: Past events in archive section
- **WHEN** a visitor navigates to `/events/` and past events exist
- **THEN** past events are displayed in a visually distinct archive section below the upcoming events

#### Scenario: No upcoming events
- **WHEN** no upcoming events exist but past events do
- **THEN** the page renders without errors, showing only the archive section

### Requirement: Events as markdown files
Events SHALL be authored as markdown files in `content/events/`. Each event SHALL have front matter with at least `title`, `date`, and `location` fields. The body MAY contain a description.

#### Scenario: Event file structure
- **WHEN** an event markdown file exists with `title`, `date`, and `location` in front matter
- **THEN** it appears in the events listing at the correct chronological position

### Requirement: Single event detail page
Each event SHALL have its own detail page displaying the full event information.

#### Scenario: Event detail page
- **WHEN** a visitor navigates to an event URL
- **THEN** the page displays the event title, date, location, and description content
