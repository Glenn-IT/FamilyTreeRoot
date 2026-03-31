# Data Schema Reference

Each person in the family tree is represented by a flat JSON object in an array stored in `localStorage` under the key `familyTree`.

---

## Person Object

| Field | Type | Required | Description |
|---|---|---|---|
| `id` | `string` | ✅ | Unique identifier (e.g. `"p1"`, `"p12"`) |
| `firstName` | `string` | ✅ | Person's first name |
| `lastName` | `string` | ✅ | Person's last name / family name |
| `birth` | `string` | ❌ | Birth year (e.g. `"1985"`) or `""` if unknown |
| `death` | `string` | ❌ | Death year (e.g. `"2020"`) or `null` if living |
| `gender` | `"male" \| "female" \| "other"` | ✅ | Used for default avatar icon and card colour |
| `role` | `"patriarch" \| "matriarch" \| "parent" \| "child"` | ✅ | Displayed as badge on the card |
| `photo` | `string \| null` | ❌ | Base64 Data URL of the person's photo, or `null` |
| `spouseId` | `string \| null` | ❌ | `id` of this person's spouse, or `null` |
| `parentIds` | `string[]` | ✅ | Array of parent `id`s (0, 1, or 2 entries) |
| `childrenIds` | `string[]` | ✅ | Array of children `id`s |

---

## Full Example

```json
[
  {
    "id": "p1",
    "firstName": "Robert",
    "lastName": "Anderson",
    "birth": "1935",
    "death": "2010",
    "gender": "male",
    "role": "patriarch",
    "photo": null,
    "spouseId": "p2",
    "parentIds": [],
    "childrenIds": ["p3"]
  },
  {
    "id": "p2",
    "firstName": "Margaret",
    "lastName": "Anderson",
    "birth": "1938",
    "death": null,
    "gender": "female",
    "role": "matriarch",
    "photo": null,
    "spouseId": "p1",
    "parentIds": [],
    "childrenIds": ["p3"]
  },
  {
    "id": "p3",
    "firstName": "James",
    "lastName": "Anderson",
    "birth": "1962",
    "death": null,
    "gender": "male",
    "role": "parent",
    "photo": null,
    "spouseId": "p4",
    "parentIds": ["p1", "p2"],
    "childrenIds": ["p5", "p6"]
  }
]
```

---

## Relationship Rules

- A person can have **0 or 1 spouse** (`spouseId`).
- A person can have **0, 1, or 2 parents** (`parentIds`).
- `childrenIds` is maintained on **both** parents for consistency.
- When a member is deleted, all `spouseId`, `parentIds`, and `childrenIds` references to that member are automatically removed.
- IDs are generated sequentially (`p1`, `p2`, ...) and are **not reused** within a session.
