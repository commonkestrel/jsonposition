# Json Position

Json Position is json library for finding the path to json at an index in the original string.
Similar to extensions in most IDEs to get path to cursor position.

## Examples

```rust
use json_position::dot_path;

let json = "[9, {\"name\": \"b\", \"fields\": [null, null, 87, 4], \"path\": \"file.txt\"}]";
let position = json.find("87").unwrap();

let dotted = dot_path(json, position).expect("Invalid JSON");
assert_eq!(dotted, "$.1.field2.2");
```
