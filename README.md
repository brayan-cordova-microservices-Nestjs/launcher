# Build en image

`docker-compose down`
`docker-compose up`
`docker-compose up --build`

## Develop Mode

1. Clone repository.
2. Create an `.env` file based on `.env.template`.
3. Then execute the command `docker-compose up --build` on your terminal to run the server in development mode.

### Steps to create Git Submodules

1. Create a new repository in GitHub
2. Clone the repository on the local machine.
3. Add the submodule, where `repository_url` is the url of the repository and `directory_name` is the name of the folder where you want the submodule to be saved (it must not exist in the project)

```
git submodule add <repository_url> <directory_name>
```

4. Add changes to the repository (git add, git commit, git push).
   Ex:

```
git add .
git commit -m "Add submodule"
git push
```

5. Initialize and update Sub-modules, when someone clones the repository for the first time, he/she should run the following command to initialize and update the sub-modules

```
git submodule update --init --recursive
```

6. To update the references of the sub-modules

```
git submodule update --remote
```

## Important

If working in the repository that has the sub-modules, **first update and push** the sub-module and **then** the main repository.

If you do it the other way around, you will lose references to the sub-modules in the main repository and you will have to resolve conflicts.
