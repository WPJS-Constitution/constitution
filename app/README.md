# WPJS Constitution Assembler

Version 1 is a read-only JavaScript single-page application. It reads the current main-branch commit directly from GitHub, follows the Topic order in the Master Record Index, and assembles each Topic's linked clause files into a timestamped Markdown compilation.

The assembler includes only clause files. It does not include Topic design notes or open questions. The downloaded file records the source commit ID and keeps hidden Markdown source comments for each clause, so the compiled wording can be traced back to its Topic file.

## Run it

The app has no build step and uses no external JavaScript packages. Once the app and source repository are publicly readable, open index.html in a modern browser and select **Assemble Markdown**. The app fetches one consistent commit snapshot, displays a preview, and lets you download the result as a .md file. No clone of the Constitution repository is needed.

The source repository is currently private. While it remains private, the no-login app cannot read its files from GitHub. It will report that public read access is unavailable. Repository visibility and main-branch protection must be handled before the app is put into public use.

## Version 1 boundaries

- Read-only: the app cannot change the repository or create a pull request.
- The compilation uses the latest snapshot listed for each Topic in the MRI, whether or not that Topic is closed.
- The output is a working compilation and does not mean that the Constitution has been approved or adopted.
- A generation timestamp and the source commit SHA are included in the Markdown output.

Version 2 may add a contribution form that submits proposed clause changes as a pull request. It must use a secure GitHub authentication flow and must not put a write token in the browser code. Repository branch protections must continue to require a pull request and the designated approval before anything reaches main.
