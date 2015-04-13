## Commit Message Best Practice

* short single-line summary (less than 50 characters)
* optionally followed by a blank line and a more coomplete description
* keep each line to less than 72 characters
* write commit messages in present tense ("fix bug" or "fixes bug" not "fixed bug")
* bullet points are usually astericks or hyphens
* be clear and descriptive
    - bad "Fix "
    - good "Add missing > in index.html"
    - bad "Update login Code"
    - good "Change user authentication to use Blowfish"

###Good Example
```
Fixed bug where user can't signup.

Users were unable to register if they hadn't visited the plans
and pricing page because we expected that tracking
information to exist for the logs we create after a user
signs up.  I fixed this by adding a check to the logger
to ensure that if that information was not available
we weren't trying to write it.

[Fixes #2873942]
```