# AnonyShare licences

Licence authority for AnonyShare clone deployments. `licences.json` is fetched by
each clone every ~5 minutes.

- **Pause a clone:** add its `LICENSE_ID` to the `revoked` array, commit, push.
  Within one check the clone goes silently inert (stops handling all updates).
- **Restore:** remove the id, commit, push.
- **Terminate a clone:** add its `LICENSE_ID` to the `terminated` array, commit,
  push. Use this for a final hard stop certificate; after the clone observes it,
  it stays locally terminated, purges the bot's cached media/cards/records, and
  leaves its groups. This is checked directly by the installed bot and does not
  require the buyer to accept a product update.
- `revoked: []` and `terminated: []` means every clone is active.

No secrets live here — it is only a list of ids, safe to keep public so clones can
fetch it without credentials.
