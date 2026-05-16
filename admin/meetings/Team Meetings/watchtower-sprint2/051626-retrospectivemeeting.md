# Sprint 2 Retrospective Meeting
## Date: 5/16/26
## Time: 2:00 - 2:30 PM
## Location: Zoom
## Attendees: Sean, Kevin, Dishita, Stephanie, Zayn, Nicholas, Maxime
## Pre-Meeting Notes:
- From dashboard: we need endpoints and error schema; need to understand the api key generation
  
## Agenda: 
1. Each team shares progress
- SDK: 
    - have setup whole pipeline of error catching, batching it, sending it 
    - working on initializing it(how user will deploy the code)
- Backend:
    - designed error schema
    - deployed a server that stores whole thing in SQL database
    - checked with SDK, they sent a post that was stored in the server 
    - made API key generator -> can be generated with post
    - SDK can use API key generator but it's insecure because right now anyone can generate an API key and send requests
    - need to finish endpoints for dashboard team
- Process docs
    - grinding ADRs; dming Powell but he takes a while
    - trying to make custom style guide 
    - not so hidden SWE rubric? how is our current progress aligning with that?
- dashboard:
    - pretty much have proof of concept for dashboard, have a lot of UI done, but not connected to backend yet
    - need to fill in endpoints



## Decisions made: 
1. Does dashboard need login info from user when they make account?
- API key generated to event load, no specific login info needed
2. Should there be an authentication key per user, and an API key per project?
- hard coded accounts for now, have hard coded authentication key per user
- each project under each user(account)needs their own API key because if all projects used the same API key, errors would be clustered
    - on SDK side, user will need one unique API key for each project
3. Do we hard code authentication key for certain accounts for now?
- need to consider in the future, when we release the project and more users are using it, need to implement way to dynamically generate authentication keys for users, but for now **in the scope of testing** we can hard code authentication keys for certain accounts
- mention that having elaborate logining system is not in the MVP of this project, so we can hard code authentication keys for certain accounts for now, but in the future when we release the project and more users are using it, we need to implement way to dynamically generate authentication keys for users
4. Thoughts on deployment?
- SDK made ADR on using `npm install watchtower` to deploy the SDK, and then user can initialize it in their code by using the API key that is generated for each project
- think about user experience, is this process accessible for users? We can argue our users are other devs, so they should be familiar with this process
- we can have a page on dashboard that explains how to deploy the SDK, something like "put this command into your `index.js`" or something -> have dashboard page with all copy-and-paste commands for users 


## Action items:
- conventional commits
- follow style guide for code formatting(once it gets approved)

