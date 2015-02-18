RENOTE URL Scheme
================

Fully supports `X-Callback-URL` protocol.
Supports two basic calls.

1. `new`: Adds a new note
2. `get`: Opens up RENOTE app, sends a URL-encoded note text after the user selects a Note. Requires `x-success` parameter.


### new

- Adds a new note in RENOTE
- required parameters: 
   - `text`: text to add to renote. 
- eg: `renote://x-callback-parameter/new?text=TEXT-TO-ADD`


### get

- Opens RENOTE in selection mode and sends across a User-selected note text via x-success protocol
