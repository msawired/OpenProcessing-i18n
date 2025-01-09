# OpenProcessing-i18n
This project includes OpenProcessing translation and internationalization files. Feel free to contribute to add your own language or make changes.

## Status
This project is currently in testing phase and covers a limited part of the website.
Languages supported at the moment are English (en), Japanese (ja), Portuguese (pt), and Turkish (tr).
Pages currently translated: 
- Sketch (87%)
- User (65%)
- Top Navigation (100%)

## Rules of Conduct
[To be defined]

## How It Works
Users can change their preferred language under user profile settings. The website loads and uses lang.mjs file in this repo to look up translations of phrases used on the website. Default language is English (en).  If user chose a different language on their OpenProcessing settings, then each word is replaced with the translation. If a translation is not found, it falls back to its English version.

## How to Contribute
You can contribute by adding your own language, or making updates to existing ones.
All the phrases from the website are being added to lang.mjs in a continued manner. You can follow this repo to get any updates on the master branch.
To contribute,
- Create a fork of this repo.
- Make your changes and additions on **lang.mjs** file. Also, look for any *null* values (eg. 'ja': null). These are new phrases that need translation.
- Test it live by going to the related page on [openprocessing.org](https://openprocessing.org) and run the code below in native browser console. This will load lang.mjs from your own branch. 
```
	//format: OP.loadLanguage([language],[repo],[branch],);
	OP.loadLanguage('ja'); //loads Japanese from msawired/OpenProcessing-i18n/lang.mjs 'master' branch
	OP.loadLanguage('ja','msawired/OpenProcessing-i18n') //loads Japanese from msawired/OpenProcessing-i18n/lang.mjs, 'master' branch by default
	OP.loadLanguage('ja','msawired/OpenProcessing-i18n', 'test') //loads Japanese from msawired/OpenProcessing-i18n/lang.mjs 'test' branch
```
- If things look right, make a pull request. Your changes will be reviewed and will be merged if approved.
- Sometimes, particularly with long translations, somethings may break on the website visually (e.g. A phrase may not fit a button with a fixed size). If you spot such issues, please create an issue in this repo.   

## lang.mjs Format
This file contains the phrases used on the website in json format, grouped by sections, in the format below:
```
"sectionName": {
	"phraseLabel": {
		"description": "Tab", //where this phrase is used
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
- "description" is there to help you look up where and when the phrase is displayed.
- "en" is the official English translation of the phrase. All other translations should follow this English version as closely as possible.

For any questions, reach out at info@openprocessing.org.

