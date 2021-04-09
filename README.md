# git-flow-workflow
The github actions in this repo are configured to be used with the git flow workflow

The worflow works as follow

The developer creates feature branches locally. Then he/she publish the feature branch. This will trigger the 
development.yml action. This is intended to be used for building and unit testing the code.

The developer then closes the feature and this gets merged to development env. Nothing happens with github actions.

Once there is a version to be tested and publish the github action draft-release.yml is called with a version number

The draft-release.yml will checkout the develop enviroment, build, test, and deploy to staging. More steps to keep testing can de used.
Once all the testing passed, then the github action will create a release branch. Update de changelog, commit and publish the release. 
And finally it creates a PR to master

When th PR is apporved then the publish-release.yml action kicks in. This created the release, and it could deploy to production. 
Finally a pull request is created to merge the master to develop enviroment

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
