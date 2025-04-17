---
icon: user
---

# User

<table><thead><tr><th>Field Name</th><th>Type</th><th data-type="checkbox">Required</th></tr></thead><tbody><tr><td><code>ID</code></td><td><code>*primitive.ObjectID</code></td><td>false</td></tr><tr><td><code>Email</code></td><td><code>*string</code></td><td>true</td></tr><tr><td><code>Password</code></td><td><code>*string</code></td><td>true</td></tr><tr><td><code>KeySet</code></td><td><code>*EncryptionKey</code></td><td>true</td></tr><tr><td><code>RoleIds</code></td><td><code>[]*primitive.ObjectID</code></td><td>false</td></tr><tr><td><code>Roles</code></td><td><code>[]*UserRoleEntity</code></td><td>false</td></tr><tr><td><code>Devices</code></td><td><code>[]*UserDevice</code></td><td>false</td></tr><tr><td><code>CreatedAt</code></td><td><code>*primitive.DateTime</code></td><td>false</td></tr><tr><td><code>UpdatedAt</code></td><td><code>*primitive.DateTime</code></td><td>false</td></tr></tbody></table>
