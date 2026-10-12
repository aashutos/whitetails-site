---
layout: page
title: WhiteTails
subtitle: Iterative regular expression find & replace for Visual Studio Code
show-avatar: false
---

WhiteTails is a focused **find and replace tool for Visual Studio Code**, designed for applying multiple regular-expression transformations to text files in sequence.

[Install from Marketplace](https://marketplace.visualstudio.com/){: .btn .btn-secondary}

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
{% assign daily_vsix_files = site.static_files | where: "extname", ".vsix" | where_exp: "file", "file.path contains '/releases/'" | sort: "modified_time" | reverse %}

{% if vsix_files.size > 0 %}
<table>
    <thead>
        <tr>
            <th>Version</th>
            <th>Filename</th>
            <th>Released</th>
            <th>Size</th>
        </tr>
    </thead>
    <tbody> 
        {% for file in daily_vsix_files %} 
        <tr>
            <td><code>{{ file.name | replace: "whitetails-", "" | replace: ".vsix", "" }}</code></td>
            <td><a href="{{ site.baseurl }}{{ file.path }}">{{ file.name }}</a></td>
            <td>{{ file.modified_time | date: "%b %d, %Y" }}</td>
            <td>{{ file.size | divided_by: 1024.0 | round: 2 }} KB</td>
        </tr> 
        {% endfor %} 
    </tbody>
</table>
{% else %}
_No releases available yet._
{% endif %}

## Nightly Builds {#nightly-build}

These VSIX packages are unstable build packages that are built nightly from the latest source code. Please use with caution.
{% assign daily_vsix_files = site.static_files | where: "extname", ".vsix" | where_exp: "file", "file.path contains '/nightly-build/'" | sort: "modified_time" | reverse %}

{% if daily_vsix_files.size > 0 %}
<table>
    <thead>
        <tr>
            <th>Version</th>
            <th>Filename</th>
            <th>Released</th>
            <th>Size</th>
        </tr>
    </thead>
    <tbody> 
        {% for file in daily_vsix_files %} 
        <tr>
            <td><code>{{ file.name | replace: "albicilla-", "" | replace: ".vsix", "" }}</code></td>
            <td><a href="{{ site.baseurl }}{{ file.path }}">{{ file.name }}</a></td>
            <td>{{ file.modified_time | date: "%b %d, %Y" }}</td>
            <td>{{ file.size | divided_by: 1024.0 | round: 2 }} KB</td>
        </tr> 
        {% endfor %} 
    </tbody>
</table>
{% else %}
_No daily releases available yet._
{% endif %}

---

*WhiteTails (Haliaeetus albicilla) — make repetitive text transformations repeatable.*
