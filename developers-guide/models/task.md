---
icon: list
---

# Task

| Field Name    | Type                    | Required |
| ------------- | ----------------------- | -------- |
| `ID`          | `string`                | ✅        |
| `Title`       | `string`                | ✅        |
| `User`        | `primitive.ObjectID`    | ✅        |
| `Description` | `*string`               |          |
| `StartDate`   | `*primitive.DateTime`   |          |
| `EndDate`     | `*primitive.DateTime`   |          |
| `Reminders`   | `[]*primitive.DateTime` |          |
| `Tags`        | `*[]*Tag`               |          |
| `Completed`   | `*bool`                 |          |
| `CreatedAt`   | `primitive.DateTime`    | ✅        |
| `UpdatedAt`   | `primitive.DateTime`    | ✅        |
