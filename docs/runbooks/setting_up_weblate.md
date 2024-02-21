# How to set up Weblate to translate a project in Github

## Introduction

This document describes how to set up Weblate to translate a project in Github.

When finished a project will be set up in the MoJ Weblate instance and the project will be linked to a Github repository, so that Webalte can create pull requests with translations.

## Prerequesites

You will need to have the following:

1. A Github account
2. A Weblate account
3. A project in Github that you want to translate
4. Send a request to MoJ Ops Engineering via slack to add the Weblate user `https://github.com/weblate` to the repository as a collaborator. This is so that Weblate can create pull requests with translations.

## Setup

### 1. Create a new project in Weblate

1. Go to the MoJ Weblate instance at [moj.weblate.cloud](https://moj.weblate.cloud) and log in.
2. Create a new project using the [Add New Translation Project page](https://moj.weblate.cloud/create/project/), fill in the details of your project and click "Save".
3. Add a new component to your project using the Add New Translation Component button on the project page.
4. Set a component name, choose a source language, set the Version control system to "Github Pull Request", and use the HTTPS address for your repository URL, for example `https://github.com/ministryofjustice/opg-weblate-demo-translation-project`. Set the branch to your default branch, for example `main`. Click "Continue".
5. Weblate will scan your repository and locate translatable files and their format. Select the option that matches your project, for example `File format JSON file, File mask lang/*.json` or specify a configuration manually and click "Continue".
6. Weblate will then ask for further details about the translation component, with details already filled in. Set the repository push URL to the ssh address of your repository, for example `git@github.com:ministryofjustice/opg-weblate-demo-translation-project.git`. Set the push branch to be something like `weblate-<component-name>`. Set the repository browser string by adding `blob/{{branch}}/{{filename}}#L{{line}}` to the end of your repository URL, for example `https://github.com/ministryofjustice/opg-weblate-demo-translation-project/blob/{{branch}}/{{filename}}#L{{line}}`.
7. Click "Save" to create the component.

Weblate will import the project, and show a Community Localisatoin Checklist. You can choose to address these later by going to `https://moj.weblate.cloud/guide/<project>/<component>/`.
