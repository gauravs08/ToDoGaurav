# ToDo Service

For this task you'll write a To-Do server and command-line client.

Feel free to change these minimal requirements if you think something would be
better in a different way, but keeping the features of adding, deleting, and
listing ToDo items.

Create a branch named after you (your first name) in this repository and commit all your work products there.

## Coding tasks

The command line app should support the following flags:

- `todo -l`
  - Would list my current ToDo items.
- `todo -i {JSON ToDo here}`
  - Would insert a new ToDo item with arbitrary JSON content. Server assigns the
    ID.
- `todo -d ID`
  - Would delete the ToDo with a given ID.

The server should expose a REST API to support the 3 basic CLI operations.
