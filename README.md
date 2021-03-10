# OpenProcessing-i18n
This project includes OpenProcessing translation and internationalization files. Feel free to contribute to add your own language or make changes.

## Status
This project is currently in testing phase and covers a limited part of the website.
Languages supported at the moment are English (en), Japanese (ja), and Portuguese (pt).
Pages currently translated: 
- Sketch (87%)
- User (50%)
- Top Navigation (90%)

At the moment, numbers and dates are *not* localized.

## Rules of Conduct
[To be defined]

## How It Works
Users can change their preferred language under user profile settings. The website loads and uses lang.js file in this repo to look up translations of phrases used on the website. Default language is English (en).  If user chose a different language on their OpenProcessing settings, then each word is replaced with the translation. If a translation is not found, it falls back to its English version.

## How to Contribute
You can contribute by adding your own language, or making updates to existing ones. Please email info@openprocessing.org to join as a contributor to this project.
All the phrases from the website are being added to lang.js in a continued manner. You can follow this repo to get any updates on the master branch.
To contribute,
- Reach out to info@openprocessing.org to join this repo as a collaborator.
- Create a branch to make your changes.
- Make your changes and additions. Also, look for any *null* values (eg. 'ja': null). These are new phrases that need translation.
- Test it live by going to the related page on [openprocessing.org](https://openprocessing.org) and run the code below in native browser console. This will load lang.js from your own branch. 
```
	//format: OP.loadLanguage([language],[branch title],[github username]);
	OP.loadLanguage('ja'); //loads Japanese from msawired/OpenProcessing-i18n/lang.js 'master' branch
	OP.loadLanguage('ja','my-branch') //loads Japanese from msawired/OpenProcessing-i18n/lang.js 'my-branch' branch
	OP.loadLanguage('ja','my-branch', 'user') //loads Japanese from [user]/OpenProcessing-i18n/lang.js 'my-branch' branch
```
- If things look right, make a pull request. Your changes will be reviewed by language maintainers and will be merged if approved.
- Sometimes, particularly with long translations, somethings may break on the website visually (e.g. A phrase may not fit a button with a fixed size). If you spot such issues, please create an issue in this repo.   

## lang.js Format
This file contains the phrases used on the website in json format, grouped by sections, in the format below:
```
"sectionName": {
	"phraseLabel": {
		"implemented": false, //if website support not implemented yet.
		"description": "Tab", 
		"en": "Sketches",
		"ja": "モード",
		"pt": "Esboços",
		...
	}
}
```
### Read-only Values
Values below will only be set by super-admins. These are created or changed as new phrases are added to the website.
- "sectionName" usually refers to the page it refers to. (camelCase) 
- "phraseLabel" is used for looking up the phrase. (camelCase)
- "implemented" exists and set to false if the website doesn't support this yet. These are used as a placeholder, and its implementation on the website is pending. Once implementation is ready, "Implemented" is removed (instead of setting it to true) to keep the file size small. *You will not be able to see your changes with OP.setLanguage function for these phrases*
- "description" is there to help you look up where and when the phrase is displayed.
- "en" is the official English translation of the phrase. All other translations should follow this English version as closely as possible.

### Translation Values
Translations are added with the format "languageShort": "Value":
```
"ja": "ユーザー",
"es": "usuario",
"fr": "utilisateur",
...
```




