### GitLab CI/CD Basics:

1. **.gitlab-ci.yml**: Create a `.gitlab-ci.yml` file in the root of your GitLab repository to define your CI/CD pipeline.

2. **Pipeline Stages**: Define stages for your pipeline, such as `build`, `test`, `deploy`, etc., to organize your jobs.

3. **Jobs**: Jobs are tasks within a stage. You can define multiple jobs in each stage.

4. **Runners**: GitLab Runners are agents that execute your CI/CD jobs. You can use shared runners provided by GitLab or set up your own runners.

### .gitlab-ci.yml Example:

```yaml
stages:
  - build
  - test
  - deploy

build:
  stage: build
  script:
    - echo "Building the application"

test:
  stage: test
  script:
    - echo "Running tests"

deploy:
  stage: deploy
  script:
    - echo "Deploying to production"
  only:
    - master  # Only deploy on changes to the master branch
```

### Job Configuration:

- `script`: Define the commands to be executed for the job.
- `only`/`except`: Define when the job should run based on branches, tags, or other criteria.
- `artifacts`: Specify files or directories to be passed between jobs in the pipeline.

### Variables:

You can define variables in GitLab CI/CD:

```yaml
variables:
  DATABASE_URL: "postgres://user:password@database:5432/mydb"
```

These variables can be accessed in your job scripts.

### Caching:

Cache dependencies to speed up subsequent pipelines:

```yaml
cache:
  paths:
    - node_modules/
```

### Artifacts:

Pass files between jobs using artifacts:

```yaml
job1:
  script:
    - echo "Creating artifact"
  artifacts:
    paths:
      - build/

job2:
  script:
    - echo "Using artifact from job1"
  dependencies:
    - job1
```

### Runner Tags:

You can use runner tags to specify where a job should run:

```yaml
job:
  tags:
    - docker
```

### Triggering Manual Jobs:

You can define manual jobs that require manual intervention to run:

```yaml
manual_job:
  stage: deploy
  script:
    - echo "Manually deploy to production"
  when: manual
```

### Environments:

Define environments for deployment and track the status:

```yaml
deploy_to_production:
  stage: deploy
  script:
    - echo "Deploy to production"
  environment:
    name: production
    url: https://example.com
```

### Secrets:

Store and use secret variables securely in GitLab CI/CD:

```yaml
variables:
  SECRET_API_KEY:
    vault: my-vault-path
```

### Custom GitLab Runners:

Set up custom GitLab Runners for specific requirements or environments.

### Troubleshooting:

Use GitLab CI/CD logs, artifacts, and the `.gitlab-ci.yml` file to diagnose and fix pipeline issues.

### GitLab CI/CD Documentation:

Refer to the official GitLab CI/CD documentation for in-depth information: [GitLab CI/CD Documentation](https://docs.gitlab.com/ee/ci/)

This cheat sheet provides a basic overview of GitLab CI/CD. Refer to the documentation for more advanced configurations and features.