# Ovation Green
Localization processes in Ovation Green are aimed at providing localized UI text for users from different countries. Follow the guidelines below to make sure that the localization is conductrd correstly and effectively. 
## General localization guidelines
You need to update localization files separately for the old and new Ovation Green applications – web application and SCADA – and for different versions starting from 5.8.0. 

> [!NOTE]
> Make sure to check out the corresponding branch (5.8.0, 5.8.1, and so on) before you make any changes. 

When there is an update that relates to more than one version of Ovation Green, first, update the oldest version, create a commit and push changes for the following one, then, repeat these actions for the version that comes after, and so on until this update is in all of the versions. This way, you minimize conflicts and manual work. 

Localization involves two types of files – _pot_ and _po_. The _pot_ files contain the original (English) text, and the _po_ files contain the localized text (currently, we fully localize to German (_de_) and Chinese (_zh_.) Usually, there are several _po_ files per a _pot_ file. 

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
- **PC** repository > **scada** > **src** > **i18n** for SCADA.
- **PC** repository > **web** > **web-app** > **i18n** for web application.  
2. Run the **cmd** terminal.  
3. In the **cmd** terminal, run the command to get a modified _pot_ file: 
- **yarn build: locale-extract** for SCADA.
- **npm build: i18n** for web application. 
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

## Localize text
There are several options for localizing Ovation Green files:
-	Using Translate By Google.
-	Manually in Poedit.
-	Using external localization services.

### Localize text in Translate By Google
1.	Go to the **PC** repository > **.libs** > **Node** > **TranslateByGoogle**.
2.	Run the **cmd** terminal. 
3.	_(Only when you use the tool for the first time)_ Run the **yarn build** command to build the tool. 
4.	Run the **node .** command to start the tool. 
5.	When the menu opens, use the arrow keys to navigate to the **Translate PO files** command and press **Enter** to run it. 
6.	When the **Choose language** menu appears, use the arrow keys to navigate to the needed language and press **Enter** to select it.
7.	When the **Choose file** menu appears, use the arrow keys to navigate to the needed file and press **Enter** to select it.
> [!NOTE]
> When you select the file that already has some strings translated, Translate By Google will only translate the strings that haven’t been translated yet. 

### Localize text in Poedit
1.	Open the _po_ file that you want to localize.
2.	Click the string that needs to be translated. 
3.	In the **Translation** section, enter the translation of the string.
   
![localize text in Poedit](https://github.com/ovationgreen/scada-readme/assets/150123119/73a99e50-304e-470d-9827-d07ed6770158)
> [!NOTE]
> Turn on the **Needs work** toggle to point out that the translation isn’t finished yet.

4. Save your changes.

## Add a new localization language
There are several ways you can add a new localization language. Doing it via the Translate By Google tool is more efficient, but if you need to add a new language only for a specific file or set of files, use Poedit.

### Add a new localization language with Translate By Google 
When you add a new localization language by using the Translate by Google tool, all _po_ files for a new localization language are created and named automatically.  

For that: 
1. Go to the **PC** repository > **.libs** > **Node** > **TranslateByGoogle**. 
2. Run the **cmd** terminal.  
3. _(Only when you use the tool for the first time)_ Run the **yarn build** command to build the tool.  
4. Run the **node .** command to start the tool.  
5. When the menu opens, use the arrow keys to navigate to the **Add new language** command and press **Enter** to run it.  
6. Use the arrow keys to navigate to the needed language and press **Enter** to add it.  
> [!NOTE]
> The program automatically creates all the needed _po_ files for the chosen language, and you can find them in the directory properly stored (in the relevant folders) and named (_de_ for German, _zh_ for Chinese, _el_ for Greek, and so on.) 

7. Add the created files to the repository for localization.  

### Add a new localization language with Poedit
> [!NOTE]
> Repeat these actions for every _pot_ file that you want to add a new language for and for every new language.

1. Go to the **PC** repository > location of the _pot_ file that you want to add a new localization language for.
2. Open the _pot_ file in Poedit.
3. On the ribbon, click **File** > **New**.
   
![add a new localization language with Poedit](https://github.com/ovationgreen/scada-readme/assets/150123119/684c112f-7467-426d-b95b-e17189ffec7c)

5. In the **Translation Language** window, select the needed language from the **Language of the translation** drop-down list and click **OK**.
6. Click **Update from pot file**.
7. In the **Open translation template** window, select the _pot_ file which you want to add a new localization language for.  
   The new _po_ file opens automatically, and you can start translating the strings right away.
8. To save the new localization file, on the ribbon, click **File** > **Save as…**, select the file location, name the file according to the naming conventions (_de_ for German, _zh_ for Chinese, _el_ for Greek, and so on), and click **Save**.   

## Add a new language to Ovation Green
When you want to add a new language to Ovation Green, it is not enough to submit new localization language files to the repository; you also need to add the language to the tool itself.  

For that: 
1. Go to **PC** repository > **scada** > **src** > **constants**. 
2. Open the **Locale.ts** file.  
3. Run the **cmd** terminal.  
4. In the `/** A locale strings that represents a specific geographical, political, or cultural region. */ ` section, make sure that the localization language is listed in the _export const ENGLISH = ‘ en ‘ ;_ format.  
5. In the `/** locale type. */` section, make sure that the localization language is listed in the _typeof ENGLISH_ format. 
6. If the localization language has to be: 
- Supported – make sure it is listed in the `/** just for test. *?/` section in the `export const SUPPORTED: locale[ ] = [ENGLISH, CHINESE, YOUR LANGUAGE]` line.
- Tested – make sure it is listed in the `/** just for test. *?/` section in the _SUPPORTED.push(UKRAINIAN)_ format.
  
![add localization language to Ovation Green_1](https://github.com/ovationgreen/scada-readme/assets/150123119/5435fa0c-73f4-4552-908f-2f8736db4f90)

7. Go to **PC** repository > **scada** > **src** > **workspaces**. 
8. Open the _locale_dev.ts_ file. 
9. Run the **cmd** terminal.  
10. In the `* localization with dev setup.` section, make sure that the localization language is listed in the `export default function applyDevTranslation() {` section in the _const en = require(‘i18n/en.po‘);_ format and in the _ttag.addLocale(ENGLISH, en);_ format.
    
![add localization language to Ovation Green_2](https://github.com/ovationgreen/scada-readme/assets/150123119/92e07ee8-2cee-417a-b741-6dcaaafc77d5)

12. Go to **PC** repository > **scada** > **src** > **target**. 
13. Open the _package.json_ file. 
14. Make sure that the localization language is listed in the `“build:locale”` line in the _&& react - scripts build --locale en -- no-clean”_ format.
    
![add localization language to Ovation Green_3](https://github.com/ovationgreen/scada-readme/assets/150123119/53fa621a-1c8d-42ee-a467-1bb78594ac50)

16. Commit all of the modified files to the repository. 

## Manage localization for Ovation Green dashboards 
Localization of dashboards in Ovation Green stands as a separate process because dashboards are configurable and can be localized by clients. However, we support the localization of several basic dashboards.  
You can localize Ovation Green dashboards manually and by using the Translate By Google tool.  

### Localize Ovation Green dashboards in Translate By Google
1. Go to the **PC** repository > **.libs** > **Node** > **TranslateByGoogle**. 
2. Run the **cmd** terminal.  
3. _(Only when you use the tool for the first time)_ Run the **yarn build** command to build the tool.  
4. Run the **node .** command to start the tool.  
5. When the menu opens, use the arrow keys to navigate to the **Translate dashboards** command and press **Enter** to run it.  
6. Open the location of the dashboard (_json_) files at the **PC** repository > **install** > **config** and commit the files to the repository. 

### Localize Ovation Green dashboards manually 
1. Open Ovation Green in the admin mode.  
2. In the upper-right corner, click the user image to open the user account settings.  
3. Click **Language** and select the language for localization.
   
![localize dashboards_1](https://github.com/ovationgreen/scada-readme/assets/150123119/c82ea1e5-9f2d-4400-acb1-cbfd61343e0d)

5. Open the dashboard that you want to localize.  
6. Right-click the item that you want to provide a localized name for and select **Edit** (in any language, it is the first option on the list).   
7. Near the **Name** field, click **Language**.
![localize dashboards_3](https://github.com/ovationgreen/scada-readme/assets/150123119/9456308d-843d-4e6e-85d0-5f2d1df4e0f0)

8. When the **Name** field empties, enter the localized name for the item there.
9. Click **OK**.
10. Repeat these actions for all the items that you need to localize.
11. On the ribbon, click **Save** to save your changes.
    
![localize dashboards_5](https://github.com/ovationgreen/scada-readme/assets/150123119/26fad50b-6593-4160-9f6d-97b8feebf37a)

13. Commit your changes.

## Use the Translate By Google tool
- [Normalize localization files in Translate By Google](https://github.com/ovationgreen/scada-readme/blob/main/git/Manage%20localization%20processes.md#normalize-localization-files)
- [Localize text in Translate By Google](https://github.com/ovationgreen/scada-readme/blob/main/git/Manage%20localization%20processes.md#localize-text-in-translate-by-google)
- [Localize dashboards in Translate By Google](https://github.com/ovationgreen/scada-readme/blob/main/git/Manage%20localization%20processes.md#localize-ovation-green-dashboards-in-translate-by-google)
### Track localization completion in Translate By Google 
You may need to check whether there are any untranslated strings in any documents.  
For that, use the Translate by Google tool: 
1. Go to the **PC** repository > **.libs** > **Node** > **TranslateByGoogle**.
2. Run the **cmd** terminal.
3. _(Only when you use the tool for the first time)_ Run the **yarn build** command to build the tool.
4. Run the **node .** command to start the tool.
5. When the menu opens, use the arrow keys to navigate to the **Show translation status** command and press **Enter** to run it.
6. When the **Choose language:** menu opens, use the arrow keys to navigate to the needed language and press **Enter** to select it.

You’ll see a list of all available _po_ files for the selected language and the number of translated and not translated strings for them together with the numbers of the detected words and characters for translation.  
![view not translated strings in Translate By Google](https://github.com/ovationgreen/scada-readme/assets/150123119/28075b89-4a42-41fd-b3bd-b4ca9cf8f71a)

## Commit localization updates
There are several options for committing localization files updates: 
- For a localization manager: 
1. [Commit changes](https://github.com/ovationgreen/scada-readme/blob/main/git/pr/README.md#create-a-commit-and-push-changes) to the branch you are working in.
2. Go to the branch of the next version, accept all the changes from the previous version, and repeat the process of updating localization files.  
- Via [pull request](https://github.com/ovationgreen/scada-readme/blob/main/git/pr/README.md#create-a-commit-and-push-changes). 


