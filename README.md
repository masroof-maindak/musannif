# Musannif

Server for Musannif, A sophisticated collaborative Markdown editor designed for teams, enabling seamless real-time collaboration and creativity.

## TODO

- [x] Init a basic logger - create wrapper over zerolog
- [x] Mete out system architecture - how to approach horizontal scaling?
- [ ] CI/CD: Publish new 'release' whenever a tagged commit is pushed
- [ ] v1.0 File/'Note' management on disk & simple web-client for single user to create/edit their notes
- [ ] v2.0 Real-time collaboration -> Note sharing via URL - let guests view notes
- [ ] v3.0 User directory/Team management
- [ ] ???

## Architecture

### Core Ideas

- Clients communicate diffs back and forth through a central server that resolves conflicts should any arise
- If a central server is reaching computational limits, it informs a master server to spin up a new server to handle the load, and transmits data to it, as well as transferring clients to it
- CHECK: Move database to a separate server that communicates with the master and/or worker servers
