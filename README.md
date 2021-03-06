---
page_type: sample
products:
- office-teams
- office-365
languages:
- typescript
urlFragment: microsoft-teams-build2017-weather
description: "This project was inspired by, and ported to TypeScript from, the WeatherBuddy project."
name: "Microsoft Teams - Weather Bot"
extensions:
  contentType: samples
  createdDate: 5/8/2017 9:13:19 AM
---

# microsoft-teams-build2017-weather

This project is intended to be merged with a project created by the Microsoft Teams App Generator (https://www.npmjs.com/package/generator-teams).

This project was inspired by, and ported to TypeScript from, the [WeatherBuddy project](https://github.com/ispeakcomputer/weather_webapp_javascript) created by [Ryan (aka ispeakcomputer)](https://github.com/ispeakcomputer). 

The WeatherBuddy project, in turn, relies on the [OpenWeatherMap Font project](http://websygen.github.io/owfont/), which is also embedded in this project.

## Instructions

* Create a Microsoft Teams app using the App Generator and add it to a Git repository (as was described in the session, and as these instructions assume).
* Type the following in your project directory to merge this project with yours, grab the OpenWeatherMap Font project, and to tweak your project.json file to support jQuery:
```
git remote add weather https://github.com/OfficeDev/microsoft-teams-build2017-weather.git
git fetch weather
git merge --allow-unrelated-histories weather/master
git submodule init
git submodule update
npm install --save @types/jquery
```
Next, copy/paste the new HTML and TypeScript. Open `c:\dev\teamsbld-yourlastname` in your IDE (in Visual Studio Code, File -> Open Folder...). Expand the src/app/scripts and src/app/web folders; this is where the files you are going to modify are located. 
* Open src/app/\*Tab.ts, e.g. teamsBuildTab.ts. This is the file that was generated by the app generator.
* Open src/app/weatherTab.ts. Select all the text in this file, copy it to the clipboard, and replace the code in \*Tab.ts with it.
* Open src/app/\*Config.html and src/app/\*Tab.html, e.g. teamsBuildConfig.html and teamsBuildTab.html. These were generated by the app generator. Look for the following code in the two .html files, except that *YourLastName* will be your real last name:

```javascript
  <script type='text/javascript'>
    var c = new teamsbldYourLastName.teamsBuildConfigure();
    function onChange(val) {
      c.setValidityState(val.length !== 0);
    }
  </script>
```
* Open src/app/weatherTabConfig.html and src/app/weatherTab.html. Select all the text in these files, copy it to the clipboard, and use it to replace the HTML in \*Config.html and \*Tab.html, respectively.
* At the bottom of the HTML in each of these files, change *teamsbldYourLastName* to its original value, e.g. from *teamsbldYourLastName* to *teamsbldSmith*.
```javascript
  <script type='text/javascript'>
    var c = new teamsbldSmith.teamsBuildConfigure();
    function onChange(val) {
      c.setValidityState(val.length !== 0);
    }
  </script>
```
Save all your files. Commit your changes and push your changes to Azure.

## Contributing

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/). For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.
