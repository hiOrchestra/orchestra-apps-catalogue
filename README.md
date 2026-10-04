# Orchestra apps catalogue

The apps an Orchestra workspace can install with one click: a CRM, a helpdesk,
a booking page, forms, website analytics, a hiring desk. Each one runs inside
the workspace that installs it: its data, its automations and its pages live
there, and nothing leaves it unless the app says so and a person approves it.

This repository is the catalogue's index. Orchestra curates it: an app or a
new version reaches workspaces only when it is merged here.

## What is here

- `catalog.json`: one entry per app.
  - The listing: what it is, for whom, the three questions it answers, and its main action.
  - What it creates: tables, the team's desk, public pages.
  - What it needs: an agent, integrations.
  - **What can leave the workspace**, in plain words.
  - Its version, and its package with the package's sha256.
- `apps/<id>/<id>-<version>.tgz`: the package. A workspace downloads it, refuses it
  unless its sha256 is the one `catalog.json` names, and runs its installer.

## How an install works

From the portal, an admin opens Canvas → Catalogue, picks an app, reads what it
creates and what it can send out, chooses the agent that runs it, and installs.

The installer converges:

- tables only grow;
- example data goes only into empty tables;
- an app's access (public or not) is never changed;
- installing again is how an app is updated.

When it ends, the portal lists what a person still has to do: approve the
tables, open the public pages, connect an integration.

## Versions

A version is a promise. A package `<id>-<version>.tgz` never changes once
published; new code gets a new version.

## Status

v0.1: Orchestra's own apps, all free. Publishing by other developers, paid
apps and forks come later. See the plan in Orchestra's Linear (project
"Catálogo de apps").
