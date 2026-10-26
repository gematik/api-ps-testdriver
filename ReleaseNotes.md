<img align="right" width="250" height="47" src="https://raw.githubusercontent.com/gematik/gematik.github.io/master/Gematik_Logo_Flag_With_Background.png"/> <br/>

# Release Notes PS Testdriver API

## Release 0.3.0 (2026-10-23)

### added

- `POST /system/configuration/konnektor` to set the Konnektor configuration of the PS for the duration of a test run
  (`.kon` format; only the environments `tu` and `ru` are accepted, `pu` is rejected with 400)
- `GET /system/configuration/konnektor` to retrieve the current Konnektor configuration; credential secrets are masked
- Schemas for Konnektor configuration and credentials (`basic`, `pkcs12`, `system`)
- Action type `set-konnektor-config`

### changed

- Media type version raised to `application/gematik.psTestdriver.v0.3.0+json`
- README, CONTRIBUTING.md and release notes aligned with the gematik OSPO guidelines

## Release 0.2.0 (2025-01-10)

### changed

- Renamed "read-vsd" to "insert-egk" to better reflect that the action is non-technical

### fixed

- Corrected typo "emp" (incorrect) to "eml" (correct)

## Release 0.1.0 (2024-08-30)

### added

- Error details for actions

### changed

- Corrected the action types

### removed

- `/system/start` (unused in KOB EPA 3.0; might be added back later if needed)
- `DELETE /actions/{id}` (unused in KOB EPA 3.0; might be added back later if needed)
- EMP data in the action response

### fixed

- Description and validation regex of the KVNR type

## Release 0.0.1 (2024-07-10)

### added

- Initial version of the PS Testdriver API with all basic operations needed for KOB EPA 3.0
