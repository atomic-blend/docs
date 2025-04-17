---
icon: braille
---

# Habit

<table><thead><tr><th>Field Name</th><th>Type</th><th data-type="checkbox">Required</th><th data-type="checkbox">Encrypted</th></tr></thead><tbody><tr><td><code>ID</code></td><td><code>primitive.ObjectID</code></td><td>true</td><td>false</td></tr><tr><td><code>UserID</code></td><td><code>primitive.ObjectID</code></td><td>true</td><td>false</td></tr><tr><td><code>Name</code></td><td><code>*string</code></td><td>true</td><td>true</td></tr><tr><td><code>Emoji</code></td><td><code>*string</code></td><td>false</td><td>false</td></tr><tr><td><code>Frequency</code></td><td><code>*string</code></td><td>true</td><td>false</td></tr><tr><td><code>NumberOfTimes</code></td><td><code>*int</code></td><td>false</td><td>false</td></tr><tr><td><code>Duration</code></td><td><code>*int</code></td><td>false</td><td>false</td></tr><tr><td><code>DaysOfWeek</code></td><td><code>*[]int</code></td><td>false</td><td>false</td></tr><tr><td><code>DaysOfMonth</code></td><td><code>*[]primitive.DateTime</code></td><td>false</td><td>false</td></tr><tr><td><code>StartDate</code></td><td><code>*primitive.DateTime</code></td><td>true</td><td>false</td></tr><tr><td><code>EndDate</code></td><td><code>*primitive.DateTime</code></td><td>false</td><td>false</td></tr><tr><td><code>CreatedAt</code></td><td><code>*string</code></td><td>false</td><td>false</td></tr><tr><td><code>UpdatedAt</code></td><td><code>*string</code></td><td>false</td><td>false</td></tr><tr><td><code>Reminders</code></td><td><code>[]string</code></td><td>false</td><td>false</td></tr><tr><td><code>Citation</code></td><td><code>*string</code></td><td>false</td><td>true</td></tr><tr><td><code>Entries</code></td><td><code>[]HabitEntry</code></td><td>false</td><td>false</td></tr></tbody></table>



### Valid Frequencies

| Constant             | Value           | Description      |
| -------------------- | --------------- | ---------------- |
| `FrequencyDaily`     | `"daily"`       | Occurs every day |
| `FrequencyWeekly`    | `"weekly"`      | Occurs weekly    |
| `FrequencyMonthly`   | `"monthly"`     | Occurs monthly   |
| `FrequencyRepeating` | `"repeatition"` | Every x days     |

