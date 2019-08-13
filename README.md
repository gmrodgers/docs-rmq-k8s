# RabbitMQ for Pivotal CF docs

## Branches in this Content Repo

The master branch is the tree-trunk, so **always** make changes you want carried forward in this branch. This includes:

* Unreleased features
* Doc bug fixes
* Doc reorganization or enhancement

Then, if necessary, immediately cherry-pick/copy any changes that you want to push immediately to production into the appropriate branches listed below:

| Branch Name| Use for… |
|------------| ---------|
| master     | 0.1 (staged here: http://docs-pcf-staging.cfapps.io/rabbitmq-kubernetes/0-n/index.html) |


[docs-book-rmq-k8s]: https://github.com/pivotal-cf/docs-book-rmq-k8s/blob/master/config.yml


## Book Repo

**docs-book-rmq-k8s** is the book repo:

* **Edge** branch is for the next unreleased version, available on staging at this link:
http://docs-pcf-staging.cfapps.io/rabbitmq-kubernetes/0-n/index.html

* **Master** branch is for the published/live releases listed above.


### Staging Environment

When a commit is made into any of the above branches, the documentation is deployed by
[this concourse build][docs-staging-deploy]. All the supported versions will be accessible on the
[staging website][docs-staging].

[docs-staging-deploy]: https://wings.concourse.ci/teams/cf-docs/pipelines/cf-services?groups=rmq-k8s
[docs-staging]:        http://docs-pcf-staging.cfapps.io/rabbitmq-kubernetes/

### Style Sheet

Use this section to specify spelling of special words for RabbitMQ for PCF:

+ on-demand plan
+ shared-VM plan
+ dedicated-VM plan
+ RabbitMQ Management UI

### Making Your Documentation Changes Live

Click the deploy button in the pipeline! Living the dream :-D

### Tag Management

We do not need to maintain older versions of the documentation so we are electing to not use tags to snapshot the state of the documentation for each previous patch version.

### Contributing Documentation

If there is some documentation to add for an unreleased patch version of RabbitMQ then create a branch off of the **live** branch you intend to modify and create a pull request against that branch. Once the version that change is targeting is released, the pull request can be merged and will be live the next time a documentation deployment occurs.

If the documentation is meant to be target several released versions, then you will need to create a pull request for each individual minor version.

### Partials

Cross-product partials for **Pivotal RabbitMQ for Kubernetes** are single sourced from the [PCF Docs Partials](https://github.com/pivotal-cf/docs-partials) repository.

### Releasing a New Minor Version

Since **master** is the latest and greatest documentation, the process would be to cut a **x.x-live** branch for the version that **master** was targeting during that time. A corresponding section in **config.yml** in the [docs-book-pcfservices][docs-book-pcfservices] repository would also need to be made.

After this point, **master** will then be the target for the next version of the RabbitMQ product tile.
