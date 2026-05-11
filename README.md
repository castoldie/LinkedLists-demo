# LinkedLists-demo

A minimal, dependency-free Python implementation of a singly linked list. Educational/demo code — no build system, no tests, just one file: `llists.py`.

## What's in `llists.py`

Two classes:

### `Node`

Holds a `value` and a `next_node` reference. Exposes getters/setter for both fields.

| Method | Purpose |
|--------|---------|
| `__init__(value, next_node=None)` | Initialize with a value and (optionally) a next-node reference |
| `get_value()` | Return the node's value |
| `get_next_node()` | Return the next-node reference |
| `set_next_node(next_node)` | Update the next-node reference |

### `LinkedList`

Wraps a `head_node`. Supported operations:

| Method | Description | Complexity |
|--------|-------------|------------|
| `__init__(value=None)` | Initialize with an optional head value | O(1) |
| `get_head_node()` | Return the head-node reference | O(1) |
| `insert_beginning(new_value)` | Prepend a new value to the list | O(1) |
| `remove_node(value_to_remove)` | Linear scan, unlink first match by value | O(n) |
| `stringify_list()` | Walk the list and join values with newlines (skips `None`) | O(n) |

## Running

```bash
python3 llists.py
```

Or import interactively:

```python
from llists import LinkedList

ll = LinkedList()
ll.insert_beginning("apple")
ll.insert_beginning("banana")
print(ll.stringify_list())
```

## Use case

A linked list is useful when you want O(1) prepend without resizing an underlying array. The classic illustrative example is a to-do list: each task is a node, new tasks are added with `insert_beginning`, and completed tasks are removed with `remove_node`.

## Known quirks

- `LinkedList()` constructed with no argument creates a `Node(None)` head — so an "empty" list actually contains one sentinel node. `stringify_list()` silently skips `None` values so this is invisible from the outside.
- `remove_node(value)` does **not** gracefully handle the case where `value` is not present in the list — it walks until `current_node` is `None` and then calls `.get_value()` on it, raising `AttributeError`. Same problem with duplicates: only the first match is removed.

## Status

Demo / learning code. Not production-ready.
