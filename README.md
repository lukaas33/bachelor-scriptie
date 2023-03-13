This repository contains the bachelor thesis of Lucas van Osenbruggen.

This is the thesis itself and the code is contained in [another repo](https://github.com/lukaas33/VA-star-allele-calling).

It is written in LaTex and integrated with several tools.

The following workflow is used:

## Track files to read

Use the Pocket extension.

Find files on the [Pocket website](https://getpocket.com/saves).

## Summarize

Summarize articles in the [Drive Folder](https://drive.google.com/drive/folders/1xDHmReizvvLMOJcNg4HUaGAqlAxRJNt6).

## Update references

Use the Mendeley web importer to add a reference to the library.

Refresh via Overleaf.

## Track notation

Create custom commands for notation.

## Track terms and abbreviations

Add glossary items for difficult or domain specific terms and abbreviations.

## Compile LaTex project

### Use Overleaf:

[Overleaf project](https://www.overleaf.com/project/63d0f043a9db7b7953152609)

### Local:

1. Use the LaTex workshop VSCode extension.

2. [Install MiTex](https://miktex.org/download/ctan/systems/win32/miktex/setup/windows-x64/basic-miktex-22.10-x64.exe)

3. [Install Perl](https://strawberryperl.com/download/5.32.1.1/strawberry-perl-5.32.1.1-64bit.msi)

4. [Install Inkscape](https://inkscape.org/release/inkscape-1.2.2/windows/64-bit/msi/dl/)

5. Set the settings to:

```json
    "latex-workshop.latex.recipes": [
        {
            "name": "pdflatex -> bibtex -> pdflatex * 2",
            "tools": [
                "pdflatex",
                "biber",
                "makeglossaries",
                "pdflatex"
            ]
        }
    ],
    "latex-workshop.latex.tools": [
        {
            "name": "pdflatex",
            "command": "pdflatex",
            "args": [
                "-synctex=1",
                "--shell-escape",
                "-interaction=nonstopmode",
                "-file-line-error",
                "-output-directory",
                "%OUTDIR%",
                "%DOC%"
            ],
            "env": {}
        },
        {
            "name": "biber",
            "command": "biber",
            "args": [
              "--output-directory",
              "%OUTDIR%",
              "main.bcf"
            ]
        },
        {
            "name": "makeglossaries",
            "command": "makeglossaries",
            "args": [
              "-d",
              "%OUTDIR%",
              "main",
            ]
        }
    ]

```