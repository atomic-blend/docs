---
icon: braille
---

# Habit

| Field Name      | Type                    | Required |
| --------------- | ----------------------- | -------- |
| `ID`            | `primitive.ObjectID`    | ✅        |
| `UserID`        | `primitive.ObjectID`    | ✅        |
| `Name`          | `*string`               | ✅        |
| `Emoji`         | `*string`               |          |
| `Frequency`     | `*string`               | ✅        |
| `NumberOfTimes` | `*int`                  |          |
| `Duration`      | `*int`                  |          |
| `DaysOfWeek`    | `*[]int`                |          |
| `DaysOfMonth`   | `*[]primitive.DateTime` |          |
| `StartDate`     | `*primitive.DateTime`   | ✅        |
| `EndDate`       | `*primitive.DateTime`   |          |
| `CreatedAt`     | `*string`               |          |
| `UpdatedAt`     | `*string`               |          |
| `Reminders`     | `[]string`              |          |
| `Citation`      | `*string`               |          |
| `Entries`       | `[]HabitEntry`          |          |



### Valid Frequencies

| Constant             | Value           | Description      |
| -------------------- | --------------- | ---------------- |
| `FrequencyDaily`     | `"daily"`       | Occurs every day |
| `FrequencyWeekly`    | `"weekly"`      | Occurs weekly    |
| `FrequencyMonthly`   | `"monthly"`     | Occurs monthly   |
| `FrequencyRepeating` | `"repeatition"` | Every x days     |

