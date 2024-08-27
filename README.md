## Launch Development

1. Clone repository
2. Create `.env` file based on `.env.template`
3. Execute command to rebuild submodules `git submodule update --init --recursive`
4. Run `docker compose up --build` to start
5. Run `docker compose -f docker-compose.prod.yml build --no-cache` for Production


### Steps to create Git Submodules


1. Create a new repository on GitHub
2. Clone the repository on local machine
3. Add the submodule, where `repository_url` is the url of the repository and `directory_name` is the name of the folder where you want the submodule to be stored (it should not exist in the project)
```
git submodule add <repository_url> <directory_name>
```
4. Add changes to repository (git add, git commit, git push)
Ex:
```
git add .
git commit -m ‘Add submodule’
git push
```
5. Initialise and update Sub-modules, when someone clones the repository for the first time, they should run the following command to initialise and update the sub-modules
```
git submodule update --init --recursive
```
6. To update the submodule references
```
git submodule update --remote
```



## PRODUCTION
1. Clone the repository
2. Create .env based on .env.template
3. Run following command
```
docker compose -f docker-compose.prod.yml build
```
Run containers
```
docker compose -f docker-compose.prod.yml up
```


## Importante
If working in the repository that has the sub-modules, **first update and push** the sub-module and **then** the main repository. 

If you do it the other way around, you will lose references to the sub-modules in the main repository and you will have to resolve conflicts.


