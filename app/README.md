# WPJS Constitution Assembler

This is a read-only JavaScript single-page application. It reads the repository directly from GitHub and assembles a timestamped Markdown file; it does not require a local clone.

## Run it

Open `index.html` in a modern browser after the app and source repository are publicly readable. The app lists **Current working draft** and any numbered edition records it finds. It uses GitHub's public read APIs and needs no token or external JavaScript package.

## What the choices mean

- **Current working draft** follows the latest Topic snapshots in `register/master-record-index.md`, in MRI order. It can include ongoing, unclosed Topics.
- **Constitution Version N** is listed when `versions/constitution-vN.md` exists. That edition record has a `# Constitution Version N` heading and a `## Topics` list containing every Topic ID. The edition index lists Topics only; its number implies the matching `VN` snapshot for each Topic.
- For a numbered edition, the app reads `topics/<topic-folder>/VN/index.md` for each Topic, then assembles every clause linked under **Clauses in this Topic version**, in MRI order. It checks that the edition includes every Topic in the MRI and that each Topic index identifies the expected version.

The app pins all reads to one `main` commit, includes its SHA and the local build timestamp in the output, and puts a hidden source-path comment before each clause for traceability. A missing Topic snapshot, missing clause, duplicate clause ID, or incomplete edition stops the build with an explanation.

## Current repository state

The repository currently has only `BASE` Topic snapshots and no numbered Constitution edition record. The selector will therefore offer the current working draft and report that no numbered editions have been recorded yet. It will list numbered editions as their edition indexes are added in future.

The output is a compilation, not a decision that the Constitution has been formally approved or adopted. Version 1 is read-only. A future proposal-submission feature must use secure authentication and must never embed a GitHub write token in browser code.

