# Label Missing Jira Info
Label PRs that don't reference a Jira ticket in the title or description. This uses regex to detect Jira ticket formats in the title (e.g. ABC-1234), and URLs to Jira tickets in the description.

![Label Missing Jira](/automations/integrations/jira/label-missing-jira-info/label_missing_jira_info.png)

Conditions (all must be true):

* The PR lacks a Jira ticket number in the title, or a link to a Jira ticket in the PR description.

Automation Actions:

* Apply a `missing-jira` label.

!!! example "Label Missing Jira Info"
    ```yaml+jinja
    --8<-- "docs/downloads/automation-library/integrations/jira/label_missing_jira_info.cm"
    ```
    <div class="result" markdown>
      <span>
      [:octicons-download-24: Download this example as a CM file.](/downloads/automation-library/integrations/jira/label_missing_jira_info.cm){ .md-button }
      </span>
    </div>