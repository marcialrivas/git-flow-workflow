# git-flow-workflow
Git Flow workflow with Git Actions

## Actions

### development.yml

1. on push:
    * branch feature
2. chekout
3. build
4. unit test
5. static analysis


### draft-release.yml

1. on workflow_dispatch:
    * add version number
2. checkout develop
3. Build
4. Unit Test
5. Deploy Staging
6. Integration
7. chekout develop
8. create release branch from development
9. update changelog
10. init git
11. update version
12. commit
13. push release to remote
14. creates pull request to master


### publish-release.yml

1. on pull_request:
    * branch master and status close
2. Create release
3. Merger master to develop
