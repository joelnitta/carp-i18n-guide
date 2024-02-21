# Carpentries translation guide

[Joel H. Nitta](https://www.joelnitta.com)

Source on GitHub: <https://github.com/joelnitta/carp-i18n-guide>

## Preface

As of writing (2024-02), there is no official support for translation of [The Carpentries](https://carpentries.org/) materials. This  **unofficial** guide is a work in progress based on using [Crowdin](https://crowdin.com/) as the translation platform for lessons written using the [Workbench](https://carpentries.github.io/workbench/) format. [Another system](https://carpentries-i18n-handbook.readthedocs.io/en/latest/) by David Pérez-Suárez for translating Carpentries lessons in the "Styles" lesson format using Transifex is no longer being maintained.

### Concepts

- i18n: Stands for "internationalization", the process of maintaining a technical framework to support translation. Does not require knowledge of the target language, but does require technical knowledge.
- l10n: Stands for "localization", the process of translating strings into a different language and cultural context. Does require knowledge of the target language/culture, but does not require technical knowledge.

Community members may be involved in i18n, l10n, or both.

### Organization

Broadly, there are three main parts to the translation workflow:

- **Localization** (l10n): Actual translation of strings. This can performed by any interested member of the Carpentries community with sufficient knowledge of the source and target languages. No technical knowledge such as using Git, GitHub, or the command line, is needed.
- **Project Management** (i18n): Setting up Carpentries lessons to be able to be translated on Crowdin, and specifying target language. This is restricted to members of the Carpentries Core Team.
- **Language Coordination** (l10n and i18n): Maintenance the translated version of a particular lesson, including proofreading and deploying the translated lesson. Can be done by Carpentries community members who have been granted Language Coordinator status by the Core Team. There is no official support yet for deployment of translated lessons, so this needs to be done at the grass-roots level by the community.

Each of these is described in its own sub-guide below (the guides for [translators](#Guide-for-Translators), [project managers](#Guide-for-Project-Managers), and [language coordinators](#Guide-for-Language-Coordinators), respectively).

There is also a very short guide for [lesson authors](#Guide-for-Lesson-Authors) about how to write Carpentries lessons in the source language so that they can be easily translated.

## About Crowdin

### Features

[Crowdin](https://crowdin.com/) is an online translation platform. We are using it for the following reasons:
  - supports parsing of \(R\)markdown documents
  - supports integration with github
  - supports right-to-left scripts
  - integration with machine-translation services
  - provides enterprise accounts for open-source projects

### Organizations and projects

An organization on Crowdin may have multiple translation projects. For example, the Carpentries organization (<https://carpentries.crowdin.com/>) has several projects, each corresponding to a workshop (`shell-novice`, `python-novice-gapminder`):

![image](https://hackmd.io/_uploads/r1PE3cfhp.png)

<!-- In particular, we will use the Carpentries Incubator [targets workshop](https://bioconductor.crowdin.com/targets-workshop) as an example[^1].

[^1]: The original Carpentries Incubator `targets` workshop is at <https://github.com/carpentries-incubator/targets-workshop/>, but since I don't have owner-level access to the `carpentries-incubator` organization, I have set up a fork at <https://github.com/joelnitta/targets-workshop/> to demonstrate translation with Crowdin. -->

### Roles in Crowdin

Participants in the translation project may have different roles, which in turn have different permissions. 
Roles in Crowdin include translator, proofreader, language coordinator, manager, and owner (in order of lower to higher permissions granted)

- **Translator** – can translate strings and vote for translations added by other members.
- **Proofreader** – can translate and approve strings.
- **Language Coordinator** - manage certain features of a project only within languages they have access to, in addition to translating and proofreading. This includes managing project members and join requests, generating project reports, creating tasks, and pre-translating project content.
- **Manager** – has similar rights as a project owner except for the ability to manage some of the owner's Resources (for instance, configuring MT engines, advanced workflows, and more) and delete projects.
- **Owner** - can do everything.

Any member of the Carpentries community can become a translator, proofreader, or language coordinator. Only members of the Core Team may be manager or owner.

Anybody can immediately join a project as a translator by signing up for a Crowdin account and going to the project website; for any other role, somebody at a higher level needs to grant you the role.

## Guide for Translators

This section explains how to participate as a community member contributing to translation (l10n). You may also want to consult the [general Crowdin documentation for volunteer translators](https://support.crowdin.com/enterprise/getting-started-for-volunteers/).

### Create an account

Create an account in the [Carpentries Crowdin account](https://carpentries.crowdin.com/) through [this link](https://accounts.crowdin.com/carpentries/login).

You can either create an account in Crowdin by filling the requested details or through sign up using your GitHub, Facebook, Twitter, GitLab or Google account.

**Warning**: The Carpentries is using Crowdin Enterprise, which is **not** connected to crowdin.com and needs a separate account. If you have an account in crowdin.com, you will still need to sign up again in Crowdin Enterprise.

### Choose a file to translate

Once you create your account and log in to the Carpentries workspace, you should see a dashboard including various on-going translation projects.
In the Carpentries workspace, each project corresponds to a lesson.

![image](https://hackmd.io/_uploads/r1PE3cfhp.png)

Choose one of the lessons that you wish to translate, then choose a language to translate. If you don't see the language that you are interested in, contact one of the managers to request it be added.

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
1. **Left Sidebar (1):** It contains all strings in the file that you will translate.
2. **Middle-top area (2):** The main working area where you edit/upvote the translations.
3. **Middle-bottom area (3):** This section contains suggestions from Translation Memory, Machine Translation (MT) suggestions, and translations by other project participants
4. **Right sidebar (4):** You can use it to add comments, report issues, and see the existing Glossary available for the strings.

![image](https://hackmd.io/_uploads/SyUroAe4a.png)

As shown in the image above, the **Middle-top area (2)** is the main working area with the source string on the top, and the section where you can type in translations. 
Crowdin will show you suggestions for translation carried out using two different engines (DeepL and Crowdin Translate), which will show you several possible translations that you can further edit.

Strings may have the following statuses:

- ![icons](https://support.crowdin.com/assets/docs/untranslated_icon.png =60x60) - Untranslated
- ![icons](https://hackmd.io/_uploads/HkdL4s-Na.png =60x60) - Translated
- ![icons](https://the-turing-way.netlify.app/_images/approved_icon.png) - Approved
- ![icons](https://the-turing-way.netlify.app/_images/hidden_icon.png) - Hidden (visible only for project managers and proofreaders)


An active string is highlighted with the yellow color but you can turn on/off color highlight of strings by clicking on ![icons](https://the-turing-way.netlify.app/_images/preview_filter.png) and show translation preview using ![icons](https://the-turing-way.netlify.app/_images/eye.png).

Crowdin editor won't only show you suggestions of a translation made by the translation engine but also suggestions from translation for strings that are stored in Translation Memory \(TM\) if the string is has a similarity above 70%.
This avoids duplication of effort.

### Proofreading

By default, when you [join the project as a translator](#Create-an-account), you only have permission to translate strings, but not to approve or reject translations. Strings that have not been approved will not appear the in actual translated file.

To approve strings for translation, you need to first obtain permission as a Proofreader. Contact a Language Coordinator via email or slack, providing your Crowdin username. The Language Coordinator may then grant you permission to do proofreading.

Once you have obtained permissions, switch to Proofreading mode by clicking the Workflow button on the top menu, which should say `CROWDSOURCING` by default:

![image](https://hackmd.io/_uploads/ry1KHs-ET.png)

This brings up the Workflow menu, where you can select `PROOFREADING`:

![image](https://hackmd.io/_uploads/HJKyIo-NT.png)

The editor window looks basically the same, but now for each string there is a check button. Press the check to approval the string if the translation appears correct.

![image](https://hackmd.io/_uploads/rkr7PibNT.png)

### Viewing the translated lesson

After your translations have been approved, if the lesson website is set up correctly, you should be able to see the newly translated website by syncing the fork as described in the [Guide for Language Coordinators](#Forking-a-lesson-for-community-deployment).

## Guide for Project Managers

This section describes how to set up new Carpentries translation projects, and manage existing ones. To do this, you need to have at least [Manager permissions in Crowdin](#Roles-in-Crowdin), so it is meant for Carpentries Core Team members.

For this guide, all translations are maintained via integration with GitHub.

A single Carpentries lesson is selected to be integrated with a single Crowdin project.

### Maintainer console

From <https://carpentries.crowdin.com/>, click on "Go to console", which brings up the maintainer interface.

From here, click on the project you want to work on, in our cases the "targets-workshop" (to add a new project, you need to contact someone with owner-level permissions of the Crowdin organization).

![image](https://hackmd.io/_uploads/BktTL3-ET.png)

### GitHub integration

#### `crowdin.yml` file

Before doing anything in Crowdin, first you will need to add a `crowdin.yml` file that describes how to set up the translation to the root of the lesson repo on the main branch. See the [`crowdin.yml` file ](https://github.com/swcarpentry-ja/git-novice/blob/main/crowdin.yml) for the `git-novice` lesson, and read the [official docs](https://developer.crowdin.com/configuration-file/).

The `crowdin.yml` file mostly consists of the `files` field, which lists each source file that should be translated (`source`) and where to put the resulting translated file (`translation`).

Note that the location of the translated file may be in a **new folder** that does not yet exist in the original repo. Globbing is used to match multiple files. Special fields are used like `%two_letters_code%` that will be filled in with a particular variable.

For example, if Japanese is set as a target language, the following yaml setting will put all translated markdown (`*.md`) files from the `./episodes` folder into `./locale/ja/episodes/` using the original file name:

```
files:
  - source: /episodes/*.md
    translation: /locale/%two_letters_code%/episodes/%original_file_name%
```

The [dovetail](https://github.com/joelnitta/dovetail) R package provides the function `use_crowdin_yml()` which will write the correctly formatted YAML file to a lesson.

Note that all translated files are created on a [new branch](#About-branches).

#### Set up the integration

Read the [Crowdin docs about setting up a new GitHub integration](https://support.crowdin.com/enterprise/github-integration/?q=github%20integration#connecting-github-with-crowdin-enterprise).

Part of this involves setting up the Crowdin GitHub app, which is a bit more complicated if you are connecting it to an organization GitHub account (not an individual GitHub account).

Select "Source and translation files mode" when setting up the integration.

This shows the current Github integration settings for the [`targets workshop`](https://github.com/carpentries-incubator/targets-workshop/) project:

![image](https://hackmd.io/_uploads/rkFwX2W46.png)

##### Setting up the Crowdin GitHub App for an organization GitHub account

Here are some more details about installing the Crowdin GitHub app for an organization GitHub account:

- Open the GitHub Marketplace from the top-left corner of GitHub.com by clicking the three bars, then clicking Marketplace.

![image](https://hackmd.io/_uploads/Sklml0IVa.png)

- Search for the Crowdin app and select it
- Scroll to the bottom of the page and select the "Open Source" (free) plan
- Enter the name of the GitHub account or organization you want to add

![image](https://hackmd.io/_uploads/rym1-R84p.png)

#### About branches

Notice in the integration settings that there is a "Service branch" called `l10n_main`. This is the branch where all the translations are written. You can see an example of one on github here: <https://github.com/swcarpentry-i18n/shell-novice/tree/l10n_main>.

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

### Export settings

It is possible to customize the conditions required for a translated string to be exported (that is, for the translation to show up in the `l10n_main` branch). You might think we would just want to export all translated strings, but it is generally a good idea to require that a proofreader who understands the target language has checked any string that will be exported, especially if you are using any sort of automated translation (e.g., machine translation or translation memory).

To do so, go to "Settings" -> "Export", select "Export translations with a specific number of approvals" and set this to at least 1. This ensures a human is in the loop when translations are exported

![image](https://hackmd.io/_uploads/r1XqbRas6.png)

### Deployment

Deployment of the lesson is available via the [dovetail](https://github.com/joelnitta/dovetail) R package.

At a high level, this involves fetching the `l10n_main` branch, then copying the translated files into a temporary directory, building the lesson with {sandpaper}, then moving the lesson webpage into the `./site` folder.

Deployment in the cloud (online) requires a modified the `sandpaper-main.yaml` GitHub workflow. [Here is an example](https://github.com/swcarpentry-ja/git-novice/blob/main/.github/workflows/sandpaper-main.yaml) of such a modified file.

The modifications make it so that the `l10n_main` branch is checked out instead of `main`, which is then used by `dovetail` to build the translated lesson. The workflow will trigger whenever there is a push to `l10n_main`.

You can see an example of a continuously deployed, translated lesson (in Japanese) at <https://swcarpentry-ja.github.io/git-novice/>. This translation will get re-built everytime there are newly translated strings approved in the Crowdin project.

[dovetail](https://github.com/joelnitta/dovetail) can also perform local deployment, as described in the [Guide for Language Coordinators](#Local-deployment).

## Guide for Language Coordinators

The job of a Language Coordinator is twofold: first, they manage translations in Crowdin and second, they deploy the translated website.

### Managing translations in Crowdin

Your main job here is to proofread translations, or to assign project members to be proofreaders.

Crowdin has no way to set restrictions on who can proofread which strings, so it is possible for example to approve your own translation.

As a Language Coordinator, you should decide what kind of workflow and rules you want to apply to proofreading. If you are OK with project members approving their own translations, that's fine. If you want to use a different approach, you should let the other project members know. It is up to you.

### Deploying the translated website

Eventually, we hope that Carpentries will set up infrastructure so that all translated versions of a lesson can be deployed from a single repository. That is not the case yet. In the meantime, each regional community can create their own fork to host a translated website.

This explains how you can set up a translated lesson website for a given lesson/language combination (for example, `git-novice` in Japanese).

1. Find the lesson you want to translate in one of the Carpentries`i18n` GitHub accounts, for example https://github.com/swcarpentry-i18n/python-novice-gapminder.
2. Click on "Fork".
3. Select the target organization and repository name (it is recommended to keep the name of the repository unchanged from the default). For example, https://github.com/swcarpentry-ja/python-novice-gapminder.
    - If you are translating lessons as a regional community, it is recommended to set up a regional organization to host them. For example, https://github.com/swcarpentry-ja/ for Software Carpentry in Japan. You need to have permissions to add repos to the organization.
4. Before forking, **uncheck** "Copy the `main` branch only"
5. Set the `LANG_CODE` GitHub action secret (basically, a variable)
    - Go to Settings -> Secrets and variables -> Actions
    - Click the "New repository secret" button ![image](https://hackmd.io/_uploads/rkXz4v-n6.png)
    - Set the name of the secret to `LANG_CODE` and type the two-letter language code (e.g., for Japanese, `ja`) ![image](https://hackmd.io/_uploads/HJbFEDWnp.png)
    - Click "Add Secret"
6. Make sure that workflows are enabled (they are usually turned off by default in forks)
    - Go to Settings -> Actions -> General
    - Select "Allow all actions and reusable workflows" ![image](https://hackmd.io/_uploads/BJVOww-3T.png)
    - Click the Actions tab, then click the button that says "I understand my workflows, go ahead and enable them" ![image](https://hackmd.io/_uploads/r1t2vD-h6.png)
    - Click on the name of **each workflow** and click the "Enable workflow button" (some automated workflows don't have the button, but click it wherever you see it) ![image](https://hackmd.io/_uploads/SJxVOwZ3T.png)
7. Specify the settings for GitHub pages: Go to Settings -> Pages, then select `gh-pages` for the branch and `/ (root)` for the folder.  ![image](https://hackmd.io/_uploads/S1gi-GzMhT.png)
8. Pull the latest changes from `l10n_main` by syncing the fork
    - Click on the branches drop-down menu, select `l10n_main`, then click "Sync Fork" ![image](https://hackmd.io/_uploads/BJ7OlMMnp.png)

The workflow is configured to run automatically whenever the `main` or `l0n_main` branches are updated (such as by syncing the fork as described immediately above). You can also manually trigger a run by clicking the "Run workflow" button.

The `l10n_main` branch of the repo in the Carpentries`i18n` GitHub account (for example https://github.com/swcarpentry-i18n/python-novice-gapminder) gets automatically updated with any new translations from Crowdin once every 30 minutes. So that means if you make new translations in Crowdin, you may have to wait up to 30 minutes before you can press the "Sync Fork" button as described above and have the changes appear.

### Local deployment

Generally, you want to deploy the website using GitHub so that others can see it.

However, sometimes (for example testing and debugging) it is useful to deploy the translated website locally. You can do so using the `dovetail` R package.

First, install `dovetail` in R with:

```
devtools::install_github("joelnitta/dovetail")
```

Open an R session in the root of the lesson repo. The lesson **must be set up** with a `crowdin.yml` file and GitHub integration as described [above](#GitHub-integration). Then, you can render a translated website (for example, into Japanese) with:

```
library(dovetail)
render_trans_from_branch(lang = "ja")
```

The website will be built in the `./site/` folder, and a preview will appear in your browser. Note that although this uses the `l10n_main` branch, **it does not modify `main`** in any way.

To test this, I recommend cloning `https://github.com/joelnitta/targets-workshop`, then running the code above.

## Guide for Lesson Authors

There are a few things lesson authors in the source language can do to help with translation.

1. **Do not hard-wrap lines** at 80 characters (or whatever number they would normally use). Crowdin needs to be able to detect sentences, and if it encounters a line break it will split the text at that point into different sentences. This makes translation (especially machine translation) difficult.
2. **Use the hash-pipe** (`#|`) for writing code chunk options. It is easier to handle options written with the hash-pipe since they each appear on their own line.
3. **Do not mix HTML and Markdown**. The Crowdin markdown parser may delete some instances of HTML, breaking the website.

## Development notes

The deployment scheme described here is very simple, and does not yet include multilingual publishing of a lesson on a single website. This is probably fine for unofficial, local usage, but not for official lessons (websites).

One possible part of a more complicated deployment could be to use `l10n_main` as CI to test that the translation does not break the webpage (for example by inserting a typo into a code chunk). If rendering the translated website from `l10n_main` works, it could then be merged into `main`, then the real translation could be built from the `locale/` directory in `main`.

## License

All original material is made available under the [Creative Commons
Attribution license][cc-by-human]. 

Some material has been derived from [The Turing Way](https://github.com/the-turing-way/the-turing-way) under the [CC-BY-4.0 license](https://github.com/the-turing-way/the-turing-way/blob/main/LICENSE.md). Changes were made by replacing "The Turing Way" with "The Carpentries" or "Bioconductor".

[cc-by-human]: https://creativecommons.org/licenses/by/4.0/
[cc-by-legal]: https://creativecommons.org/licenses/by/4.0/legalcode