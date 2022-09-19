# Pokedex

The Pokédex project is (1) a Full MERN Stack Application that catalogues and provides data on all the species of Pokémon featured in the video game, anime and manga series as well as (2) a seperate Jamstack application which provides Documentation on the design and creation of the project in it's entirety. It is being actively developed and maintained by Kanto Pharmaceuticals, a non-commercial GitHub organization run by @mattybakes. The purpose of this application is purely academic and non-commercial.

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
