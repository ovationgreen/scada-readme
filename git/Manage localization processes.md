# Ovation Green
Localization processes in Ovation Green are aimed at providing localized UI text for users from different countries. Follow the guidelines below to make sure that the localization is conductrd correstly and effectively. 
## General localization guidelines
You need to update localization files separately for the old and new Ovation Green applications–web application and SCADA–and for different versions starting from 5.8.0. 

> [!NOTE]
> Make sure to check out the corresponding branch (5.8.0, 5.8.1, and so on) before you make any changes. 

When there is an update that relates to more than one version of Ovation Green, first, update the oldest version, create a commit and push changes for the following one, then, repeat these actions for the version that comes after, and so on until this update is in all of the versions. This way, you minimize conflicts and manual work. 

Localization involves two types of files – _pot_ and _po_. The _pot_ files contain the original (English) text, and the _po_ files contain the localized text (currently, we fully localize to German (de) and Chinese (zh.) Usually, there are several _po_ files per a _pot_ file. 

> [!IMPORTANT]
> It is best not to edit _pot_ files manually. 

## View localization files
1. Go to one of several localization files locations: 

- **PC** repository > **java** > **server** > **resources** > **localization** > **po** – for all server messages and status codes descriptions.
- **PC** repository > **web** > **web-app** > **i18n** – for the web application.
- **PC** repository > **scada** > **src** > **i18n** – for SCADA. 

Open and review the needed _pot_ and _po_ files in the Poedit app.

### General overview of a localization file
This is what a localization file looks like. The text lines are named _localization strings_.
![localization file](https://github.com/ovationgreen/scada-readme/assets/150123119/8494e50c-f795-451f-b544-36d4868885ea)

Some localization strings may have both Singular and Plural options. It means that some words are used in both forms and you need to provide translations for both of them.  
Be attentive because sometimes, there are not just several word forms, but also several cases of words that require specific endings. All of these forms and cases of words need to be listed as separate localization strings and translated.  
![localization file_plural](https://github.com/ovationgreen/scada-readme/assets/150123119/364d7ee8-3735-42a9-aee7-ff9a87a6fe76)

## Update localization files
Before making any updates to your localization files, you may need to make sure that the related _pot_ file is up to date. For that, regenerate a _pot_ file.  
This process differs for SCADA and web application localization files.  
> [!NOTE]
> This is necessary to build the application from scratch and ensure that the newly generated _pot_ file has a full set of strings.

0. _(Only for SCADA)_ Go to the **PC** repository > **web** > **scada** > **node modules** and delete the _.cache_ folder.  
1. Open the location of the _pot_ file:  

a. **PC** repository > **scada** > **src** > **i18n** for SCADA. 

b. **PC** repository > **web** > **web-app** > **i18n** for web application.  

2. Run the **cmd** terminal.  

3. In the **cmd** terminal, run the command to get a modified _pot_ file: 

a. **yarn build: locale-extract** for SCADA. 
b. **npm build: i18n** for web application. 
> [!NOTE]
> This command checks the original _pot_ file, adds the localization strings that were added to the source files, and deletes the localization strings that were deleted from the source file since the last update. As a result, the _pot_ file is updated with all changes that were missing since the previous review.

## Normalize localization files
After you generate an updated _pot_ file, you need to normalize it. Do it before committing the file to the repository for localization. 
> [!NOTE]
> When you perform this action, it normalizes all SCADA and web application _pot_ and _po_ files. 

To normalize a _pot_ file means to remove all unnecessary details such as line numbers, to sort all the strings, and to ensure that separate strings are provided for each locale form.  
For that, use the Translate by Google tool: 
1. Go to the **PC** repository > **.libs** > **Node** > **TranslateByGoogle**. 
2. Run the **cmd** terminal.  
3. Run the **yarn install** command. 
4. _(Only when you use the tool for the first time)_ Run the **yarn build** command to build the tool.  
5. Run the **node .** command to start the tool.  
6. When the menu opens, use the arrow keys to navigate to the **Maintenance: update, sort, trim** command and press **Enter** to run it.  
> [!NOTE]
> When the tool finishes the maintenance, it provides a short report on findings and actions performed. The **TRIMMED** label near a file’s name means that there was something deleted in the file, and the **UPDATED** label means that something was added there in correspondence to the new _pot_ file.  
![use Translate By Google](https://github.com/ovationgreen/scada-readme/assets/150123119/85552ddd-bfb7-4988-ac27-b4731637c866)




