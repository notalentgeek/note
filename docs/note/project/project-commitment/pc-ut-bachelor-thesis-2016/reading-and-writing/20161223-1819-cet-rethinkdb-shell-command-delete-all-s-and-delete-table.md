* RehinkDB shell command to delete all documents in a table.

```markdown
r.db("sociometric_server").table("testClient_cam").delete() && r.db("sociometric_server").table("testClient_mic").delete()
```

* RethinkDB shell command to delete table (specific table).

```markdown
r.db("sociometric_server").tableDrop("testClient_cam") && r.db("sociometric_server").tableDrop("testClient_mic")
```