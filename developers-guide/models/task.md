---
icon: list
---

# Task

<table><thead><tr><th>Field Name</th><th>Type</th><th data-type="checkbox">Required</th><th data-type="checkbox">Encrypted</th></tr></thead><tbody><tr><td><code>ID</code></td><td><code>string</code></td><td>true</td><td>false</td></tr><tr><td><code>Title</code></td><td><code>string</code></td><td>true</td><td>true</td></tr><tr><td><code>User</code></td><td><code>primitive.ObjectID</code></td><td>true</td><td>false</td></tr><tr><td><code>Description</code></td><td><code>*string</code></td><td>false</td><td>true</td></tr><tr><td><code>StartDate</code></td><td><code>*primitive.DateTime</code></td><td>false</td><td>false</td></tr><tr><td><code>EndDate</code></td><td><code>*primitive.DateTime</code></td><td>false</td><td>false</td></tr><tr><td><code>Reminders</code></td><td><code>[]*primitive.DateTime</code></td><td>false</td><td>false</td></tr><tr><td><code>Tags</code></td><td><code>*[]*Tag</code></td><td>false</td><td>true</td></tr><tr><td><code>Completed</code></td><td><code>*bool</code></td><td>false</td><td>false</td></tr><tr><td><code>CreatedAt</code></td><td><code>primitive.DateTime</code></td><td>true</td><td>false</td></tr><tr><td><code>UpdatedAt</code></td><td><code>primitive.DateTime</code></td><td>true</td><td>false</td></tr></tbody></table>
