# Pokedex

The Pokédex project is (1) a Full MERN Stack Application that catalogues and provides data on all the species of Pokémon featured in the video game, anime and manga series as well as (2) a seperate Jamstack application which provides Documentation on the design and creation of the project in it's entirety. It is being actively developed and maintained by Kanto Pharmaceuticals, a non-commercial GitHub organization run by [@mattybakes](https://github.com/Kanto-Pharmaceuticals/pokedex/commits?author=mattybakes). The purpose of this application is purely academic and non-commercial.

## Getting Started

It should be noted that this repository contains many submodules in order to split code for other deployments. Some knowledge of `git` and `submodule` is required in order to correctly push commits without breaking pointer references. It is **highly** recommended that the `git` CLI is used in favor of typical GUI interfaces, such as VS code's Source Control panel in order to avoid confusion in chaining pushes.

### Cloning the Repository

This repository can be cloned as you would a normal repo, however, it is important to run:

```bash
yarn update
```

or

```bash
git submodule update --init --recursive --remote
git pull
```

afterwards in order to pull the submodule repositories to local.

### Updating the Repository After Changes

This repo uses `yarn` as it's package manager and provides a simple `yarn update` command that will quickly update all submodules to their latest branch. This must be run to update submodules as a `git pull` will not update changes.

### Pushing Changes From Submodules

If changes are made to submodules from within this repo, they must be pushed from within that submodules folder. Simply `cd` into the folder with the submodule repo that needs to be updated and execute your normal commands:

```bash
cd application/frontend
git add .
git commit -m "some changes"
git push
```

All parent submodules and repos have to be updated and pushed as well. In the example above, the following steps need to be carried out in order to persist the changes and pointers in the parent repo:

```bash
cd ..
git add .
git commit -m "updated submodule"
cd ..
git add .
git commit -m "updated submodule of submodule"
```

## Submodules

The Application and Documentation use two different types of architecture (due to their function), and have been separated into different submodules. Both feature submodules themselves, but for different reasons. The MERN Stack Application has separate submodules for Frontend and Backend for code re-usability. The Jamstack Documentation has seperated modules for Framework and Content in order to differentiate version control and commit history between the two.

- MERN Stack Application
  - Frontend
  - Backend
- Jamstack Documentation
  - Framework
    - Content

## Technologies Used

- [MongoDB](https://www.mongodb.com): Self-hosted database
- [ExpressJS](https://expressjs.com): Web framework package for Node.js
- [NGINX](https://nginx.org): Reverse-proxy and load balancing
- [React](https://reactjs.org): Frontend Framework
- [Node.js](https://nodejs.org/en/): Runtime for stack
- [Gatsby](https://www.gatsbyjs.com): A React based SSG framework
- [Markdown](https://github.github.com/gfm/): Simple lightweight markup
- [Typesense](https://github.com/typesense/typesense): Open source Algolia
- [GitHub Actions](https://github.com/features/actions): CI/CD Pipelines
- [adnanh](https://github.com/adnanh) / [webhook](https://github.com/adnanh/webhook): Webhooks for continuous build and testing
- [GoogleChrome](https://github.com/GoogleChrome) / [lighthouse-ci](https://github.com/GoogleChrome/lighthouse-ci): Benchmarking and Testing
- [Graylog2](https://github.com/Graylog2/graylog2-server): Log management
- [Prometheus](https://prometheus.io) + [Grafana](https://grafana.com): System and endpoint monitoring

## Figma Design Files

## Other Assets

## Credit

[msikma](https://github.com/msikma) / [pokesprite](https://github.com/msikma/pokesprite) : https://msikma.github.io/pokesprite/

[PokeAPI](https://github.com/PokeAPI) / [pokeapi](https://github.com/PokeAPI/pokeapi) : https://pokeapi.co

[joshwcomeau](https://github.com/joshwcomeau) : https://www.joshwcomeau.com
