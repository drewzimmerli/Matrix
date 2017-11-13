# Vision

Provide an all-encompassing dashboard for any and all written communication
needs - whether synchronous or asynchronous.

Automatically score communication by priority and make them part of a todo
list.

Provide full automation mechanisms on all of this.


# Data Structure

The storage backends are structured using `Connection` objects. Example
connections:

- IMAP
- HipChat
- Github
- …

Each connection synchronises its messages (`Message`) locally, so they are
available efficiently. Those messages are then grouped and de-duplicated into
threads, potentially across connections.

These threads are stored in channels. The default channels come from the
connections (e.g. mailboxes, chat channels, etc.) but additional virtual
channels (Views) can be added in the user interface.


    Connection --> Channel --> Message --> Thread <-- View



