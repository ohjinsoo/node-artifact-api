# Node Artifact Api
This is a node wrapper for the [official Valve Artifact API](https://github.com/ValveSoftware/ArtifactDeckCode), with Typescript support

**Installation**

Install with NPM

```bash
npm i --save node-artifact-api
```

import singular methods, or full api as object

```javascript
import { decodeDeck, getSet } from 'node-artifact-api';

// OR

import * as ArtifactApi from 'node-artifact-api';
```

then use any of the methods below.

Project written in Typescript and has types support out of the box.

## Features

* Fetching card set by ID
* Fetching card by ID
* In-memory caching
* Decoding deck codes

More is coming soon, especially once the Beta is released on the 19th and I can play with the client directly for more test data.

[For a full API Documentation, click here](https://github.com/ammuench/node-artifact-api/blob/master/API.md)

## Feature Roadmap
The following is a list of features planned for release with this API in the coming weeks:

* ~~Individual Card Fetching~~ (**Done in v0.3.0!**)
* System for passing a "caching" middleware (In Progress)
    * In memory caching completed with **v0.3.0!**
* ~~Deck Decoding~~ (**Done in v0.2.0!**)
* Deck Encoding (Not Started)

## Caching
As of **v0.3.0** the `getCard` and `getSet` methods cache in-memory according to [Valve's API Guidelines](https://github.com/ValveSoftware/ArtifactDeckCode#card-set-api):
```markdown
After receiving the response, you must then request the JSON file from the host specified. In this example, "https://some host/some path/somefile.json". Please cache the provided JSON for AT LEAST until the expire time provided.
```

By default the above methods will use this caching rule.  Cache can be cleared with an optional parameter provided to each method.  It is not advised to clear caches outside of the API rules unless you are having issues or are handling caching separately, in order to avoid being blocked from accessing the API.

## Contributors
Feel free to open a PR or log an issue if you would work on this repo.  

Thank you to the following people for contributing so far!

* [seanmadi](https://github.com/seanmadi)
