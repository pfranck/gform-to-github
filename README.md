# gform-to-github

## Introduction

Script to create a file from Google form - Can be transform into a static CMS generator

## Demo

- Go on form: [https://forms.gle/XwZVMZjpzhyKP4qT8](https://forms.gle/XwZVMZjpzhyKP4qT8)
- feel the info of the form
- info is commited to `gform` branch in directory `demo/responses`

## Get started

### Requirements

To create your how project need to have:

- a github project with a branch call `gform`
- a Personal Access Token for github with scope `repo` - you can created via [https://github.com/settings/tokens](https://github.com/settings/tokens)

### Step 1: create form

Create a Google Form and associated a Google Spreadsheet to it. You can for example duplicate this form : [https://docs.google.com/forms/d/1cyaYx6pV0G5XhZqJ0Jhs3Oe0K-xqzBTQmQ4Eb4ZYB-k/edit?usp=sharing](https://docs.google.com/forms/d/1cyaYx6pV0G5XhZqJ0Jhs3Oe0K-xqzBTQmQ4Eb4ZYB-k/edit?usp=sharing)

### Step 2: associate a Google Script to your form

Open the Google Spreadsheet and go on `tools > Script Editor`

### Step 3: create the script

Copy-past the content of `connect-gform-to-github.gs`.
You then need to adapt the following global variables:

- YOUR_USERNAME
- YOUR_REPO
- GITHUB_KEY

You then need to adapt the function `createJsonFileContent` to match the value return by your Google form

### Step 4: Associate script to a trigger

On the script app go `Edit > Current project's triggers`
Add a trigger with following values:

- _Choose which function to run_: **onFormSubmit**
- _Select event source_: **From Spreadsheet**
- _Select event type_: **On Form submit**

### Step 5: Test that your data is recieved correctly

## Debug

You can find the log execution of the function in: [https://script.google.com/home/executions](https://script.google.com/home/executions)
