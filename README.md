# README

This is a demonstration application for an issue filed against [RuboCop](https://github.com/rubocop-hq/rubocop).

`db/migrate/.rubocop.yml` looks like this:

```yaml
inherit_from:
  - ../../.rubocop.yml

# Uncommenting either Metrics/MethodLength or Style/Documentation will disable Rails/CreateTableWithTimestamps!

#Metrics/MethodLength:
#  Enabled: false

Rails/CreateTableWithTimestamps:
  Enabled: true

#Style/Documentation:
#  Enabled: false
```

With the file in this state, `bundle exec rubocop --only Rails/CreateTableWithTimestamps db/migrate/*.rb` shows an offence on the migration, as the timestamps are missing.

If either the `Metrics/MethodLength` or `Style/Documentation` blocks are uncommented, the missing timestamp offence will no longer be detected.
