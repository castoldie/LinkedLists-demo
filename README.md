# Linked Lists

This code implements a linked list data structure using two classes: Node and LinkedList.

## Node Class

The Node class has two main properties:

- value: This represents the data stored in a node
- next_node: This is a reference to the next node in the linked list

### It has four methods:

- `__init__(self, value, next_node=None)`: Initializes the Node class with a value and a reference to the next node (which is set to None by default indicating the end of the list)
- `get_value(self)`: Returns the value of the node
- `get_next_node(self)`: Returns the reference to the next node
- `set_next_node(self, next_node)`: Updates the reference to the next node

## LinkedList Class

### The LinkedList class has a single property:

head_node: This is a reference to the first node in the linked list

### It has six methods:

- `__init__(self, value=None)`: Initializes the LinkedList class with an optional value to set as the head node
- `get_head_node(self)`: Returns the reference to the head node
- `insert_beginning(self, new_value)`: Adds a new Node(new_value) to the beginning of the linked list
- `stringify_list(self)`: Converts the linked list into a string representation
- `remove_node(self, value_to_remove)`: Removes a node with a specified value from the linked list

## Use Case
A linked list can be used to store a collection of data where each element is connected to the next. For example, consider a to-do list application where a linked list can be used to store tasks. Each task can be stored as a node in the linked list and linked to the next task. The insert_beginning method can be used to add a new task to the beginning of the list. The stringify_list method can be used to display the list of tasks. The remove_node method can be used to remove a completed task from the list.
