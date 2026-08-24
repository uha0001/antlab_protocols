# GitHub Guide for the Ant Lab Protocol Repository

## Purpose

This guide is for lab members who have little or no experience with GitHub.

It starts from creating a GitHub account and then explains how to access, read, download, and edit protocols in the Ant Lab protocol repository.

Repository:

https://github.com/uha0001/antlab_protocols/tree/main

You do **not** need to use the command line or know Git to read or make simple edits to the protocols.

---

# 1. Create a GitHub Account

If you already have a GitHub account, skip to Section 2.

1. Go to **https://github.com/**
2. Click **Sign up**.
3. Enter your email address.
4. Create a password.
5. Choose a username.
6. Complete the verification steps requested by GitHub.
7. Check your email and verify your email address if prompted.
8. Sign in to GitHub.

Your GitHub username does not have to match your university username.

For lab use, it is helpful to use an email address you check regularly so you can receive repository invitations or notifications.

---

# 2. Access the Ant Lab Protocol Repository

Open the repository in a web browser:

https://github.com/uha0001/antlab_protocols/tree/main

If the repository is public, you can read and download the files without a GitHub account.

If editing access is restricted, you may need to:

1. create a GitHub account;
2. send your GitHub username to the repository owner;
3. accept the repository invitation sent through GitHub.

After accepting the invitation, you should be able to edit files if you have been given write access.

---

# 3. What is GitHub?

GitHub is a website used to store files and keep a history of changes.

For this repository, it is basically being used as a shared protocol folder with version tracking.

This means that:

- protocols can be viewed directly in a browser;
- Markdown (`.md`) files are displayed as normal formatted documents;
- previous versions are kept automatically;
- changes can be traced;
- protocols can be downloaded;
- several people can contribute without creating multiple versions such as `protocol_final_final2.docx`.

You do not need to understand programming to use this repository.

---

# 4. Finding a Protocol

After opening the repository, you will see folders and files.

A typical structure may look like:

```text
protocols/
├── 3d_printing/
├── dissections/
├── rna/
├── dna/
└── assays/
```

To find a protocol:

1. Click the relevant folder.
2. Click the `.md` file you want to read.

For example:

```text
protocols
└── dissections
    └── venom_gland_dissection.md
```

GitHub automatically displays Markdown files as formatted documents.

You do not need special software to read them.

---

# 5. Reading a Protocol

Once you open a `.md` file, the formatted protocol appears directly on the GitHub page.

You can scroll through it as you would any webpage.

Typical sections may include:

- Purpose
- Materials and Equipment
- Reagents
- Procedure
- Quality Control
- Notes and Troubleshooting
- Safety Considerations
- Version History

---

# 6. Downloading One Protocol

If you want to save one protocol to your computer:

1. Open the protocol file on GitHub.
2. Use the available **Raw** or download option near the top of the file.
3. Save the file to your computer.

Markdown files can be opened using:

- any text editor;
- Visual Studio Code;
- Obsidian;
- Typora;
- other Markdown-compatible software.

You can also copy the formatted text into Word if needed.

---

# 7. Downloading the Entire Repository

If you want a local copy of all protocols:

1. Go to the main repository page.
2. Click the green **Code** button.
3. Choose **Download ZIP**.
4. Save the ZIP file.
5. Extract the ZIP file on your computer.

You now have a local copy of the complete protocol repository.

Downloading the ZIP does **not** create a live connection to GitHub. If protocols are updated later, your downloaded copy will not update automatically.

---

# 8. Editing a Protocol Directly in the Browser

If you have a GitHub account and permission to edit the repository, small changes can be made directly on the website.

1. Open the protocol you want to edit.
2. Click the **pencil icon** or **Edit this file**.
3. Make your changes.
4. Review the changes before saving.
5. Enter a short description of what you changed.

Examples:

```text
Correct centrifugation time in RNA extraction protocol
```

```text
Add note about Lasius niger dissection
```

6. Commit/save the change.

GitHub keeps the previous version automatically.

---

# 9. What is a Commit?

A **commit** is a saved change in GitHub.

Think of it as an entry in the protocol's version history.

Each commit should have a short message describing what was changed.

Good examples:

```text
Add DNA extraction protocol
Correct RNA wash volume
Update 3D printer settings
Add troubleshooting note for venom gland dissection
```

Less useful examples:

```text
update
change
stuff
final
```

A clear commit message makes it easier for everyone to understand why the protocol changed.

---

# 10. Adding a New Protocol

If you have permission to edit the repository:

1. Open the folder where the new protocol belongs.
2. Click **Add file**.
3. Choose either:
   - **Create new file**, or
   - **Upload files**.

## Create a Markdown File Directly

Give the new file a name ending in `.md`.

For example:

```text
dna_extraction.md
```

Then write or paste the protocol into the editor.

When finished:

1. add a commit message;
2. commit/save the file.

## Upload an Existing File

1. Click **Add file**.
2. Choose **Upload files**.
3. Drag the file into the browser or select it from your computer.
4. Add a commit message.
5. Commit/save the upload.

---

# 11. File Naming

Use clear filenames with lowercase letters and underscores.

Good examples:

```text
venom_gland_dissection.md
rna_extraction.md
ctab_dna_extraction_small_ants.md
ant_feeder_3d_printing.md
```

Avoid filenames such as:

```text
protocol_final.md
protocol_final2.md
protocol_really_final.md
```

GitHub already stores the version history, so filenames do not need to contain version numbers or the increasingly desperate word `final`.

---

# 12. Basic Markdown

Protocols are written in Markdown because it is simple and displays cleanly on GitHub.

## Headings

```markdown
# Main title

## Section

### Subsection
```

## Bullet Points

```markdown
- item one
- item two
- item three
```

## Numbered Steps

```markdown
1. First step
2. Second step
3. Third step
```

## Bold Text

```markdown
**important**
```

## Italic Text

```markdown
*Lasius niger*
```

## Filenames or Code

Use backticks:

```markdown
`rna_extraction.md`
```

## Tables

```markdown
| Version | Change |
|---|---|
| v1 | Initial protocol |
| v2 | Updated wash step |
```

GitHub automatically formats these when the file is displayed.

---

# 13. Adding Images

Images can be useful for:

- dissections;
- equipment setup;
- plate layouts;
- 3D-printing orientation;
- troubleshooting.

A simple approach is to create an `images` folder inside the relevant protocol folder.

Example:

```text
protocols/
└── dissections/
    ├── venom_gland_dissection.md
    └── images/
        └── venom_gland_example.jpg
```

The image can then be included in Markdown using:

```markdown
![Venom gland example](images/venom_gland_example.jpg)
```

Use informative filenames rather than names such as:

```text
IMG_1234.jpg
```

---

# 14. Making Larger Changes Safely

For small corrections, editing the file directly is usually sufficient.

For larger changes, it may be useful to:

1. create a separate branch;
2. make the changes there;
3. open a pull request;
4. review the changes before merging them into the main repository.

If you are unfamiliar with branches or pull requests, ask someone familiar with GitHub for help.

You do not need to learn these features just to read protocols or fix a small typo.

---

# 15. What is a Pull Request?

A **pull request** is a proposed set of changes that can be reviewed before becoming part of the main repository.

It is useful when:

- a protocol is being substantially rewritten;
- several people are contributing;
- a change should be checked before becoming the current version.

It is generally unnecessary for very small corrections.

---

# 16. Using GitHub Desktop

If you plan to edit protocols frequently, **GitHub Desktop** is an optional way to work with the repository without using command-line Git.

A typical workflow is:

1. Install GitHub Desktop.
2. Sign in using your GitHub account.
3. Clone the repository to your computer.
4. Edit the Markdown files locally.
5. Open GitHub Desktop.
6. Review the changed files.
7. Enter a short commit message.
8. Click **Commit**.
9. Click **Push origin** to upload the changes to GitHub.

This is optional.

For reading protocols and making occasional edits, the GitHub website is usually enough.

---

# 17. Before Editing a Protocol

Before changing an existing method, consider whether the change is:

- a typo or formatting correction;
- a clarification;
- a tested protocol modification;
- an experimental change that has not yet been validated.

Important experimental changes should be described clearly in the commit message and, when appropriate, in the protocol itself.

For example:

```text
Changed venom gland sample number from 20 to 30 after pilot RNA extraction.
```

This is much more useful than silently replacing `20` with `30`.

---

# 18. Working Protocols vs. Validated Protocols

Some protocols in this repository may still be under development.

If a method is being optimized, this should be stated near the top of the protocol.

For example:

```markdown
> **Working protocol:** Parameters are still being optimized.
```

If a protocol has been validated and is routinely used, that can also be stated.

This helps distinguish established procedures from experimental modifications.

---

# 19. Suggested Protocol Structure

To keep protocols consistent, use approximately the following structure:

```markdown
# Protocol Title

## Purpose

## Materials and Equipment

## Reagents

## Sample Preparation

## Procedure

## Quality Control

## Notes and Troubleshooting

## Safety Considerations

## Version History
```

Not every protocol requires every section.

---

# 20. If You Accidentally Change Something

Do not panic.

GitHub keeps a history of previous versions.

If something is accidentally deleted or changed, the previous version can usually be recovered from the file history.

This is one of the major advantages of keeping protocols in GitHub instead of maintaining a collection of files named:

```text
protocol_final.docx
protocol_final2.docx
protocol_final_REAL.docx
```

---

# 21. Quick Reference

## I do not have a GitHub account

Go to **github.com → Sign up → create an account → verify your email**.

## I only want to read a protocol

Open the repository → open the relevant folder → click the `.md` file.

## I want all protocols on my computer

Open the repository → **Code → Download ZIP**.

## I want to correct a protocol

Sign in → open the file → **Edit** → make the change → add a commit message → commit.

## I want to add a protocol

Open the appropriate folder → **Add file** → create or upload the file → commit.

## I cannot edit the repository

Send your **GitHub username** to the repository owner so that access can be provided if appropriate.

## I want to see what changed

Open the file or repository history and inspect the commits.

---

# Repository

**Ant Lab Protocols**

https://github.com/uha0001/antlab_protocols/tree/main
