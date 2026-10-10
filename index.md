---
layout: page
title: WhiteTails
subtitle: Iterative regular expression find & replace for Visual Studio Code
show-avatar: false
---

<div style="text-align: center; margin: 2rem 0 3rem;">

WhiteTails is a focused **find and replace tool for Visual Studio Code**, designed for applying multiple regular-expression transformations to text files in sequence.

[Install from Marketplace](https://marketplace.visualstudio.com/){: .btn .btn-secondary}

</div>

## Why WhiteTails?

A single regular-expression replacement is often not enough. WhiteTails lets you define a sequence of transformations and execute them against your document as one repeatable operation.

### 🔎 Regular expressions

Use familiar Java-style regular-expression patterns for precise text transformations.

### 🔁 Multiple transformations

Create several find/replace operations and apply them sequentially.

### ✏️ In-place editing

Apply the transformation sequence directly to the active text document.

### 🧩 Native VS Code workflow

WhiteTails is designed to work naturally within Visual Studio Code and its existing editor workflow.

## Example

A sequence of transformations might look like this:

```text
Find:    ^old_(.*)$
Replace: new_$1

Find:    \s+$
Replace:

Find:    foo
Replace: bar
```

Each operation is applied in order, allowing the output of one transformation to become the input to the next.

## Installation {#installation}

1. Open **Visual Studio Code**.
2. Open the **Extensions** view.
3. Search for **WhiteTails**.
4. Install the extension.
5. Open a supported text file and launch WhiteTails.

[Open the Visual Studio Marketplace](https://marketplace.visualstudio.com/){: .btn .btn-primary}

## Usage {#usage}

Open WhiteTails from the extension command or the relevant editor context menu.

Add your find/replace transformations, review their order, and execute them against the active document.

## Releases {#download}

VSIX releases for direct download/installation onto VS Code:
{% assign vsix_files = site.static_files | where: "extname", ".vsix" | sort: "modified_time" | reverse %}

{% if vsix_files.size > 0 %}

| Version | Filename | Released | Size |
|---------|----------|----------|------|
{% for file in vsix_files %}
| `{{ file.name | replace: "whitetails-", "" | replace: ".vsix", "" }}` | [{{ file.name }}]({{ site.baseurl }}{{ file.path }}) | {{ file.modified_time | date: "%b %d, %Y" }} | {{ file.size | divided_by: 1024.0 | round: 2 }} KB |
{% endfor %}

{% else %}
No releases available yet.
{% endif %}

---

*WhiteTails (Haliaeetus albicilla) — make repetitive text transformations repeatable.*
