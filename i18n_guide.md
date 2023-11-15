# Carpentries translation guide

[Joel H. Nitta](https://www.joelnitta.com)

Source on GitHub: <https://github.com/joelnitta/carp-i18n-guide>

## Preface

As of writing (2023-11), there is no official support for translation of [The Carpentries](https://carpentries.org/) materials. This  **unofficial** guide is a work in progress based on using [Crowdin](https://crowdin.com/) as the translation platform for lessons written using the [Workbench](https://carpentries.github.io/workbench/) format. There are alternative systems that have been developed for translating The Carpentries lessons, for example [this one](https://carpentries-i18n-handbook.readthedocs.io/en/latest/) by David Pérez-Suárez using Transifex and the "Styles" lesson format.

### Concepts

- i18n: Stands for "internationalization", the process of maintaining a technical framework to support translation. Does not require knowledge of the target language, but does require technical knowledge.
- l10n: Stands for "localization", the process of translating strings into a different language and cultural context. Does require knowledge of the target language/culture, but does not require technical knowledge.

Community members may be involved in i18n, l10n, or both.

### About Crowdin

[Crowdin](https://crowdin.com/) is an online translation platform. We are using it for the following reasons:
  - supports parsing of \(R\)markdown documents
  - supports integration with github
  - supports right-to-left scripts
  - integration with machine-translation services
  - provides enterprise accounts for open-source projects

## General Crowdin setup

An organization on [Crowdin Enterprise](https://crowdin.com/enterprise) (separate from <https://crowdin.com/>) may have multiple translation projects. For example, the Bioconductor organization (<https://bioconductor.crowdin.com/>) has several projects, including both Carpentries lessons ("bioc-intro", "targets-workshops") and other projects:

![image](https://hackmd.io/_uploads/ryG6cqWVT.png)

This guide focuses on using Crowdin to translate Carpentries lessons built with [Workbench](https://carpentries.github.io/workbench/). In particular, we will use the Carpentries Incubator [targets workshop](https://bioconductor.crowdin.com/targets-workshop) as an example[^1].

[^1]: The original Carpentries Incubator `targets` workshop is at <https://github.com/carpentries-incubator/targets-workshop/>, but since I don't have owner-level access to the `carpentries-incubator` organization, I have set up a fork at <https://github.com/joelnitta/targets-workshop/> to demonstrate translation with Crowdin.

### Roles in Crowdin

Participants in the translation project may have different roles, which in turn have different permissions. 
Roles in Crowdin include manager, translator, and proofreader.
- **Manager** – has similar rights as a project owner except for the ability to manage some of the owner's Resources (for instance, configuring MT engines, advanced workflows, and more) and delete projects.
- **Proofreader** – can translate and approve strings.
Unlike the manager, the Proofreader doesn't have access to project settings.
- **Translator** – can translate strings and vote for translations added by other members.

## Guide for translators (l10n)

This section explains how to participate as a community member contributing to translation (l10n). For demonstration purposes, we show the [Bioconductor Crowdin project](https://bioconductor.crowdin.com/), since The Carpentries project is not yet set up. You may also want to consult the [general Crowdin documentation for volunteer translators](https://support.crowdin.com/enterprise/getting-started-for-volunteers/).

### Create an account

Create an account in the [Bioconductor Crowdin project](https://bioconductor.crowdin.com/) through [this link](https://accounts.crowdin.com/bioconductor/login).

You can either create an account in Crowdin by filling the requested details or through sign up using your GitHub, Facebook, Twitter, GitLab or Google account.

**Warning**: Bioconductor is using Crowdin Enterprise, which is **not** connected to crowdin.com and needs a separate account. If you have an account in crowdin.com, you will still need to sign up again in Crowdin Enterprise.

### Choose a file to translate

Once you create your account and log in to the Bioconductor workspace, you should see a dashboard including various on-going translation projects.

![image](https://hackmd.io/_uploads/HkABF5e4p.png)

For the purposes of this guide, click on the `targets-workshop` project. This project is to translate a [Carpentries Incubator lesson about the `targets` R package](https://github.com/joelnitta/targets-workshop) for writing data analysis workflows.

Next, choose a language to translate (currently, this project is set up for Japanese and Spanish).

After selecting a language, you will see a list of files that need to be translated.

![image](https://hackmd.io/_uploads/H1ej99lNa.png)

The **priority** for each file is indicated by the colored up arrows next the file name; red indicates high priority, so if possible, please translate those first.

The blue and green bars indicate how many words have been translated and approved, respectively. Machine translation is used as a first-pass, but requires human approval for use.

Choosing a file will take you to the translation editor window.

### Using the editor

The [Crowdin](https://crowdin.com/) editor is your friend.
You can use it to change translation language, proofread, add comments for contributors, contact the managers, vote on translations, view suggestions for translation from Translation Memory or find Machine Translation from Google, Crowdin, DeepL, and others.

Once you click on any file, you will be directed to the comfortable mode in the Crowdin crowdsourcing editor. 
There are different modes and editors inside Crowdin but we will only go through comfortable mode and proofreader mode in the Crowdin crowdsourcing editor.
You can find more information about the Crowdin Editor from the [documentation here](https://support.crowdin.com/enterprise/getting-started-for-translators/).

The comfortable mode is divided into four sections:
1. **Left Sidebar:** It contains all strings in the file that you will translate.
2. **Middle-top area:** The main working area where you edit/upvote the translations.
3. **Middle-bottom area:** This section contains suggestions from Translation Memory, Machine Translation (MT) suggestions, and translations by other project participants
4. **Right sidebar:** You can use it to add comments, report issues, and see the existing Glossary available for the strings.

![image](https://hackmd.io/_uploads/SyUroAe4a.png)

As shown in the image above, the Middle-top area (2) is the main working area with the source string on the top, and the section where you can type in translations below. 
Crowdin will show you suggestions for translation carried out using two different engines (DeepL and Crowdin Translate), which will show you several possible translations that you can further edit.

Strings may have the following statuses:

- ![icons](https://support.crowdin.com/assets/docs/untranslated_icon.png) - Untranslated
- ![icons](https://hackmd.io/_uploads/HkdL4s-Na.png =60x60) - Translated
- ![icons](https://the-turing-way.netlify.app/_images/approved_icon.png) - Approved
- ![icons](https://the-turing-way.netlify.app/_images/hidden_icon.png) - Hidden (visible only for project managers and proofreaders)


An active string is highlighted with the yellow color but you can turn on/off color highlight of strings by clicking on ![icons](https://the-turing-way.netlify.app/_images/preview_filter.png) and show translation preview using ![icons](https://the-turing-way.netlify.app/_images/eye.png).

Crowdin editor won't only show you suggestions of a translation made by the translation engine but also suggestions from translation for strings that are stored in Translation Memory \(TM\) if the string is has a similarity above 70%.
This avoids duplication of effort.

### Proofreading

By default, when you [join the project as a translator](#Create-an-account), you only have permission to translate strings, but not to approve or reject translations. Strings that have not been approved will not appear the in actual translated file.

To approve strings for translation, you need to first obtain permission as a Proofreader. Contact a translation manager via email or slack, providing your Crowdin username. The translation manager may then grant you permission to do proofreading.

Once you have obtained permissions, switch to Proofreading mode by clicking the Workflow button on the top menu, which should say `CROWDSOURCING` by default:

![image](https://hackmd.io/_uploads/ry1KHs-ET.png)

This brings up the Workflow menu, where you can select `PROOFREADING`:

![image](https://hackmd.io/_uploads/HJKyIo-NT.png)

The editor window looks basically the same, but now for each string there is a check button. Press the check to approval the string if the translation appears correct.

![image](https://hackmd.io/_uploads/rkr7PibNT.png)

### Viewing the translated lesson

Currently, there is no way to view the translated lesson online, but I plan to add this soon.

In the meantime, you will need to render (deploy) the website locally as [described below](#Deployment).

## Guide for maintainers (i18n)

To be a maintainer, you need to have maintainer permissions. For that, contact a translation manager via email or slack, providing your Crowdin username. The translation manager may then grant you permission to act as a maintainer.

For this guide, all translations are maintained via integration with GitHub. A single Carpentries lesson is selected to be integrated with a single Crowdin project.

### Maintainer console

From <https://bioconductor.crowdin.com/>, click on "Go to console", which brings up the maintainer interface.

![image](https://hackmd.io/_uploads/HklKuibEa.png)

From here, click on the project you want to work on, in our cases the "targets-workshop" (to add a new project, you need to contact someone with owner-level permissions of the Crowdin organization).

![image](https://hackmd.io/_uploads/BktTL3-ET.png)

### GitHub integration

#### `crowdin.yml` file

Before doing anything in Crowdin, first you will need to add a `crowdin.yml` file that describes how to set up the translation to the root of the lesson repo on the main branch. See the [`crowdin.yml` file ](https://github.com/joelnitta/targets-workshop/blob/main/crowdin.yml) for the `targets-workshop` lesson, and read the [official docs](https://developer.crowdin.com/configuration-file/).

The `crowdin.yml` file mostly consists of the `files` field, which lists each source file that should be translated (`source`) and where to put the resulting translated file (`translation`).

Note that the location of the translated file may be in a **new folder** that does not yet exist in the original repo. Globbing is used to match multiple files. Special fields are used like `%two_letters_code%` that will be filled in with a particular variable.

For example, if Japanese is set as a target language, the following yaml setting will put all translated markdown (`*.md`) files from the `./episodes` folder into `./locale/ja/episodes/` using the original file name:

```
files:
  - source: /episodes/*.md
    translation: /locale/%two_letters_code%/episodes/%original_file_name%
```

Note that all translated files are created on a [new branch](#About-branches).

#### Set up the integration

Read the [Crowdin docs about setting up a new GitHub integration](https://support.crowdin.com/enterprise/github-integration/?q=github%20integration#connecting-github-with-crowdin-enterprise).

Select "Source and translation files mode" when setting up the integration.

This shows the current Github integration settings for the `targets workshop` project:

![image](https://hackmd.io/_uploads/rkFwX2W46.png)

#### About branches

Notice in the integration settings that there is a "Service branch" called `l10n_main`. This is the branch where all the translations are written. You can see it on github here: <https://github.com/joelnitta/targets-workshop/tree/l10n_main>.

The `l10n_main` branch basically looks the same as `main`, except that it includes the `./locale/` folder containing all translations (one per language folder) as defined in `crowdin.yml`.

The `l10n_main` branch is updated (synced) once per hour, as defined in the settings. If you want to sync it immediately, you can click the "Sync Now" button:

![image](https://hackmd.io/_uploads/r1zbBnWET.png)

Although the Crowdin docs recommend regularly merging the service branch (`l10n_main`) into `main`, we are currently keeping them separate. This may change in the future.

### Maintaining strings

One important job of the maintainer is to flag strings that **should not** be translated, for example [fenced divs](https://carpentries.github.io/sandpaper-docs/style.html#fenced-divs) such as `:::::: callout` that are used to mark text with special formatting in Workbench. It would break the lesson if a translator tried to translate the word `callout` to something else, so it is better that they cannot modify it at all. The same goes for some code chunks, etc.

#### Hide individual strings

One way to do this is on a per-string basis in the editor. Once you have selected a string, click on the three dots icon, then select "Hide String":

![image](https://hackmd.io/_uploads/SyDM9aWE6.png)

#### Batch hide strings

However, this is tedious if you have a lot of strings to hide. In fact, fenced divs are a good example - there can be a lot of them in a lesson!

Fortunately, we can batch edit strings in the maintainer console. Click on "Sources" in the left sidebar, then "Strings". This shows all the strings in the project. You can filter them using the search bar. For example, to only show strings that are fenced divs, type `:::` in the search bar. You can them select them all and click the "hide" button. Yay! Now all the fenced divs are hidden from translators.

![image](https://hackmd.io/_uploads/HkY5j6WN6.png)


### Pre-translation

Lesson maintainers can translate entire files using machine translation ("MT") or translation memory ("TM"). Click the "Pre-translate" button and follow the menus.

![image](https://hackmd.io/_uploads/Hy6DvTbNT.png)

### Deployment

Currently, only local deployment of the lesson is available, via the [dovetail](https://github.com/joelnitta/dovetail) R package.

First, install `dovetail` in R with:

```
devtools::install_github("joelnitta/dovetail")
```

Then, open an R session in the root of the lesson repo. The lesson **must be set up** with a `crowdin.yml` file and GitHub integration as described [above](#GitHub-integration). Then, you can render a translated website (for example, into Japanese) with:

```
library(dovetail)
render_trans(lang = "ja")
```

The website will be built in the `./site/` folder, and a preview will appear in your browser. Note that although this uses the `l10n_main` branch, **it does not modify `main`** in any way.

To test this, I recommend cloning `https://github.com/joelnitta/targets-workshop`, then running the code above.

## License

### Summary

All original material is made available under the [Creative Commons
Attribution license][cc-by-human]. 

Some material has been derived from [The Turing Way](https://github.com/the-turing-way/the-turing-way) under the [CC-BY-4.0 license](https://github.com/the-turing-way/the-turing-way/blob/main/LICENSE.md). Changes were made by replacing "The Turing Way" with "The Carpentries" or "Bioconductor".

[cc-by-human]: https://creativecommons.org/licenses/by/4.0/
[cc-by-legal]: https://creativecommons.org/licenses/by/4.0/legalcode