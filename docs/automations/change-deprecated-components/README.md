# Change Deprecated Components

Request changes when a PR includes one or more deprecated components.

![Change Deprecated Components](change_deprecated_components.png)

Conditions (all must be true):

* A PR contains one or more references to functions, methods, or classes that have been designated as deprecated.

Automation Actions:

* Add a `deprecated-component` label to the PR
* Request changes to the PR and post a comment that explains what deprecated component was included and what the alternative is.

!!! example "Change Deprecated Components"
    ```yaml+jinja
    --8<-- "docs/downloads/automation-library/change_deprecated_components.cm"
    ```
    <div class="result" markdown>
      <span>
      [:octicons-download-24: Download this example as a CM file.](/downloads/automation-library/change_deprecated_components.cm){ .md-button }
      </span>
    </div>