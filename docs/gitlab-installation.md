# GitLab installation 

**Step 1:** To start using gitStream with GitLab source code hosting, make sure you installed gitStream for [GitLab](https://api.gitstream.cm/auth/grant/gitlab).

!!! note 

	Automation rules by gitStream are executed on behalf of the user account used to install it. We recommend using a new dedicated account in GitLab and authenticate gitStream with it, e.g. `gitstream-cm`.

**Step 2:** Once installation completes, add the following 2 configurations files in the root of each of the selected repositories - it should be added to the default branch (usually `master` or `main`).

!!! note 

	In GitLab uses a single CI/CD file `.gitlab-ci.yml`, if you already have one in your repository, you should edit it and add the content of the `gitlab-ci.yml` below at the bottom of the file. Otherwise, you can just add the file to your repo.  

Download the files:

1. [`.cm/gitstream.cm`](/downloads/gitstream.cm)
2. [`.gitlab-ci.yml`](/downloads/.gitlab-ci.yml)

Or, if you prefer, copy and paste their content:

=== ":octicons-file-code-16: `.cm/gitstream.cm`"

    ```yaml+jinja
    --8<-- "docs/downloads/gitstream.cm"
    ```
=== ":octicons-file-code-16: `.gitlab-ci.yml`"

    ```yaml+jinja   
    --8<-- "docs/downloads/.gitlab-ci.yml"
    ```

## Configuration files

Eventually, the following files should exist in each of the selected repos:

```
.
├─ .cm/
│  └─ gitstream.cm
├─ .gitlab-ci.yml
```

| File and path         | Reason |
|-----------------------|----------------------------------------|
| `.cm/*.cm`    | Under the repo's `.cm` directory, any file that ends with `.cm` will be used by gitStream to specify automation rules, you can edit these files |
| `.gitlab-ci.yml` | Used by gitStream to execute automation rules in your GitLab repo so source code doesn't get to outside services |

## Permissions

!!! attention 

	When renaming or adding new repositories, you must re-authenticate gitStream in [GitLab using OAuth](https://api.gitstream.cm/auth/grant/gitlab)

The required permissions are: 

| Permissions           | Reason |
|----------------------|-------------------------------------------------------|
| Read API | Access the authenticated user's API and get the relevant events |
| Read repository | To read the code on monitored repositories |
| Write repository | To allow gitStream to approve PRs once all conditions are met |
| Read user profile | Used to identify users |
| Read user email | Used to identify users |

## gitStream actions

Automation rules by gitStream are executed on behalf of the user account used to install it. We recommend using a new dedicated account in GitLab for installing gitStream, e.g. `gitstream`

Since GitLab doesn't support a bot entity, some gitStream actions are annotated with special watermark to be able to tell if those actions were made by gitStream or by the user, in case a real user account was used to install gitStream. 

The water mark is added as follows:

| Action  | Field   | Watermark |
| ------- | ------- | --------- |
| Label   | label's description | "by gitStream" |
| Comment | comment's last line | "by gitStream" |
| Request change | comment's last line | "Change requested by gitStream" |