# AnonyShare licences

Licence authority for AnonyShare clone deployments. `licences.json` is fetched by
each clone every ~15 minutes.

- **Pause a clone:** add its `LICENSE_ID` to the `revoked` array, commit, push.
  Within one check the clone goes silently inert (stops handling all updates).
- **Restore:** remove the id, commit, push.
- `revoked: []` means every clone is active.

No secrets live here — it is only a list of ids, safe to keep public so clones can
fetch it without credentials.
