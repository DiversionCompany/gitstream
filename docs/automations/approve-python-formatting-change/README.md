# Approve Python Formatting Changes
Approve PRs that only contain formatting changes to Python files. 

![Approve Python Formatting Changes](approve_python_formatting_change.png)


Conditions (all must be true):

* All of the files end in `.py`.
* All changes are non-functional

Automation Actions:

* Approve the PR
* Apply a `code-formatting` label.
* Post a comment that explains the automation.

!!! example "Approve Python Formatting Changes"
    ```yaml+jinja
    --8<-- "docs/downloads/automation-library/approve_python_formatting_change.cm"
    ```
    <div class="result" markdown>
      <span>
      [:octicons-download-24: Download this example as a CM file.](/downloads/automation-library/approve_python_formatting_change.cm){ .md-button }
      </span>
    </div>