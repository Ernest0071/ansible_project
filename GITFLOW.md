# Introduction

We are begining with a strict implementation of gitflow workflow to allow for more control on how changes are introduced to our playbook.

As the number of contributors have increased, it has become necessary for strict control over the code base. 


## What is gitflow workflow

Head to [Atlassian Gitflow workflow write up](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow) and the [original nvie post](https://nvie.com/posts/a-successful-git-branching-model/)


The idea behind this is to make sure we have have multiple different versions of our ansible billbox playbooks run for different purpose to support what runs in different environments. Let's experiment this approach and see how codes are checked in the develop and master branch and confirm if its prevents overlaping of files.

The simple way of using the gitflow workflow is to use it through a git application. I suggest using [fork](https://git-fork.com/) . It's allows you to use the community version and that gives you most of the capability we need.

## How does it work

We are starting with version `3.0.0` which is arbitrary because I have not really executed this project with the [semver](https://semver.org/) in mind. We now have to.


So everyone including myself will fork from develop to either start  a feature. This can be any new addition in terms of playbooks. Like adding integration playbooks. Once that is tested, the feature is ready and closed in order to have it in merged back in the develop branch. Then a release is created with a minor version increment ie we will increase from `3.0.0` to `3.1.0` (since we are starting from 3.0.0). We will make sure that release is stabled and when it is, we close it in order to have it create a tag and get merged back in both `develop` and `master` branch.


