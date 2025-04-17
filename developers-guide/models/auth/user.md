---
icon: user
---

# User

| Field Name  | Type                    | Required |
| ----------- | ----------------------- | -------- |
| `ID`        | `*primitive.ObjectID`   |          |
| `Email`     | `*string`               | ✅        |
| `Password`  | `*string`               | ✅        |
| `KeySet`    | `*EncryptionKey`        | ✅        |
| `RoleIds`   | `[]*primitive.ObjectID` |          |
| `Roles`     | `[]*UserRoleEntity`     |          |
| `Devices`   | `[]*UserDevice`         |          |
| `CreatedAt` | `*primitive.DateTime`   |          |
| `UpdatedAt` | `*primitive.DateTime`   |          |
