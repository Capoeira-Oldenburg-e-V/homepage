## ADDED Requirements

### Requirement: Organisation name is "Capoeira Oldenburg e. V."
The site SHALL use "Capoeira Oldenburg e. V." as the organisation name in all locations where the name appears: site configuration, data files, and content pages. The old string "Capoeira Verein Oldenburg" SHALL NOT appear in any built output.

#### Scenario: Site title uses correct name
- **WHEN** any page is rendered
- **THEN** the `<title>` element contains "Capoeira Oldenburg e. V." and does not contain "Capoeira Verein Oldenburg"

#### Scenario: JSON-LD uses correct name
- **WHEN** any page is rendered
- **THEN** the LocalBusiness JSON-LD block contains `"name": "Capoeira Oldenburg e. V."`

#### Scenario: No stale name in built output
- **WHEN** the site is built with `hugo build`
- **THEN** a search for "Capoeira Verein Oldenburg" in the `public/` directory returns zero matches
