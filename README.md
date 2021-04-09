# git-flow-workflow
Git Flow workflow with Git Actions

## Actions

### development.yml

1. on push:
    * branch development
2. chekout
3. build
4. unit test
5. static analysis


### draft-release.yml

1. on workflow_dispatch:
    * add version number
2. chekcout
3. create release branch from development
4. update changelog
5. init git
6. update version
7. commit
8. push release to remote
9. creates pull request to master


### publish-release.yml

1. on pull_request:
    * branch master and status close
2. Create release
3. Merger master to develop
