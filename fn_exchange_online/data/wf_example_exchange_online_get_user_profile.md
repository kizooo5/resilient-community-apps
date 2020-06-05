<!--
    DO NOT MANUALLY EDIT THIS FILE
    THIS FILE IS AUTOMATICALLY GENERATED WITH resilient-circuits codegen
-->

# Example: Exchange Online Get User Profile

## Function - Exchange Online: Get User Profile

### API Name
`exchange_online_get_email_user_profile`

### Output Name
`None`

### Message Destination
`fn_exchange_online`

### Pre-Processing Script
```python
inputs.exo_email_address = artifact.value
```

### Post-Processing Script
```python
if results.content["error"] is not None:
  noteText = u"Exchange Online user profile NOT FOUND: {0}\n{1}".format(results.inputs["exo_email_address"], results.pretty_string)
else:
  noteText = u"Exchange Online user profile: {0}\n{1}".format(results.inputs["exo_email_address"], results.pretty_string)

incident.addNote(noteText)
```

---
