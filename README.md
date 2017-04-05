# How to edit Chrome Themes

## Introduction
This is a guide to help you edit your existing Chrome themes to change the default text colors and background images on New Tab page. It is fairly simple to do, and should take around **15 minutes**.

## Getting started
You will need to have [Google Chrome](https://www.google.com/chrome/browser/desktop/) installed on your computer as well as some text editor. I like [Sublime Text](http://www.sublimetext.com/2) but feel free to use any editor you like better.

You will need to have downloaded a pre-existing Chrome theme to begin. Browse the [theme store](https://chrome.google.com/webstore/category/themes) to find one you like, and hit "Add to Chrome". Once you have a theme, we will want to find the folder it saves to.

# Find the folder with your theme
* ### Windows

	You will need to show hidden files to see the folder. Do this by opening the Control Panel. If you're on Windows 8 or newer, the fastest way is **Windows key+X**, then **P**. Click into **Appearance and Personalization**, then **Folder Options**. Go to the **View** tab. There will be a list of advanced settings - we want to find the *Hidden files and folders option*. There should be two radio options - select the Show hidden files, folders, and drives* one. Click Apply and you're done.

	Open File Explorer (Windows+x, e) and navigate to this folder. **User Name** shoul be replaced by your user name.
	`C:\Users\**User Name**\AppData\Local\Google\Chrome\User Data\Default\Extensions`
* ### OS X

	Open Terminal and type `defaults write com.apple.finder AppleShowAllFiles YES` to show hidden files. Navigate to `~/Library/Application Support/Google/Chrome/Default/Extensions` to find the folder containing Chrome extensions.
* ###Linux

	Open your file manager in root (`sudo nautilus` in Ubuntu) and press ctrl+h to see hidden files. Navigate to `~/.config/google-chrome/Default/Extensions/` to find the extensions. You could also enter into a Terminal: 'sudo vi ~/.config/google-chrome/Default/Extensions/' to edit the file directly.

## Find your theme
In the folder you opened, you will find a long list of folders, all of which have titles that look like random letters.
![](http://i.imgur.com/d2wpvII.png)

 One of these contains your theme, and the rest are other themes or extensions you have installed. Sort by Date Modified. The most recent one should be your theme, assuming this theme was the one you installed last. Open the folder, go into the version folder, and look for a file called **manifest.json**.

## Edit manifest.json

The **manifest.json** file is the "command center" for your theme. It controls the layout and details of your theme. Right-click it and open it with a text editor. If you're in the right folder, it'll look something like this![](http://i.imgur.com/9buKhEm.png)

You'll want to be careful with what you're editing in the manifest.json file, since it controls so much, but anything within the *theme* subsection should be fair game. [Google provides their own official documentation for theme attributes.](https://code.google.com/p/chromium/wiki/ThemeCreationGuide) You can change text colors by [changing the RGB values](http://www.colorpicker.com) associated with them.

![](http://i.imgur.com/ubP4q6I.png)

## Changing images

You'll also see an *images* subsection in the manifest.json. Here you can specify what images will be used, and where. To change an image, you'll need to put the changes in the images folder, which can be found in the same place you found your manifest.json. 
![](http://i.imgur.com/ssKEbBb.png)

For example, if you'd rather have a different background image on the New Tab page, just rename your image `eyes.png` and copy/paste it into the theme's images folder, replacing the current tab.png as you do. 

If you have a .jpg you want to use instead, that's fine. Just paste it into the images folder and change the line of code in the manifest to refer to your .jpg instead. In this example, if you had an image called cat.jpg, you would change line 22 to `"theme_ntp_background": "images/cat.jpg",`

## Confirming changes and using new theme

To see how your new theme looks, you can add it to Chrome. To do this, you'll need to enable Developer Mode. Go to Your chrome settings (chrome://extensions) and check the Developer Mode box. Click **Pack extension** and a window will open allowing you to select your folder. Navigate to your extension's version folder and select it.

![](http://i.imgur.com/eipyXle.png) 

Click OK and then you are ready to **Pack Extension**. You will receive a success message saying that Chrome made you a **.crx** and a **.pem**. The .crx is your new theme! Go back to that folder and double click it, opening it in Chrome. There should be a message at the bottom confirming that you want to continue adding the theme - go ahead and click continue, then OK, and that's it. Admire your new theme and give yourself a pat on the back - you just made your own awesome theme! 

