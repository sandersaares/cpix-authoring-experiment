# CPIX authoring experiment

The example content is based on a partially converted CPIX 2.1 draft 8. It is not meant to be used for "real world usage", just as a document authoring experiment.

The main components of the experimental workflow are:

1. The document is authored using Bikeshed format, which is a mixture of HTML and Markdown.
1. A compilation step is required generating output from the Bikeshed document.
1. The output is a single HTML file (which may reference external images and other resources).

The emphasis of the first experiment is to determine whether current editors are comfortable with the file format.

# Example output

See http://media.axprod.net/temp/cpix-authoring-experiment/

# Tools required

For editing the Bikeshed file format, Visual Studio Code is a relatively convenient editor, supporting basic syntax highlighting and integrating very well with Git source control.

The compiler is accessed over web API, so there is no need to install any software. A couple of shell scripts enable you to use it:

* Generate.sh compiles the input document Cpix.bs into an Index.html file.
* Validate.sh checks the document for errors and warnings.

You can run these scripts anywhere you have a Linux-style environment (including Windows Subsystem for Linux). There is also a [Bikeshed web interface](https://api.csswg.org/bikeshed/) available for manual submission.

# How to edit as primary editor

The workflow from the perspective of a primary editor who operates directly in the repository master branch:

1. Clone the repository (or pull latest changes if you have already cloned it in the past).
1. (Optionally) make any changes you desire.
1. Execute Validate.sh to check document validity.
1. Execute Generate.sh to generate output.
1. View output in your web browser to check it manually.
1. Commit any changes and push them to GitHub.

# How to contribute

1. Fork the repository (or [pull changes from upstream](https://help.github.com/articles/merging-an-upstream-repository-into-your-fork/) if you have already forked it in the past).
1. Create a new branch named after your contribution (e.g. `xyzdrm-signaling`).
1. (Optionally) make any changes you desire.
1. Execute Validate.sh to check document validity.
1. Execute Generate.sh to generate output.
1. View output in your web browser to check it manually.
1. Commit any changes and push them to GitHub.
1. Create a GitHub Pull Request against the master branch of the primary repository, describing your contribution.
1. Wait for review and eventual merging.
1. Delete your branch once the contribution has been merged.

Any changes a contributor makes make to the affected branch in their fork (e.g. as a response to review comments) will be reflected automatically in the pull request.