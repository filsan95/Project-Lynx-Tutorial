# LYNX - A GUIDE TO SETUP FOR MACS

## Introduction
Lynx is a text-based browser, meaning that it does not support images, audio or video content, which can be accessed through the terminal. So why would you want to use Lynx, as opposed to modern graphic web browsers (ie. Opera, Mozilla, Chrome etc.)?
1. Because it is light and fast
2. Because it bypasses all of the advertising material (which are graphical in nature)
3. Because it looks super rad to surf the web using the terminal
<p> This document serves as a brief guide on how to set-up and use the Lynx browser. To learn morn about Lynx checkout this <a href='https://en.wikipedia.org/wiki/Lynx_(web_browser)'>Wikipedia</a> article for a quick read, or visit the <a href='https://lynx.invisible-island.net/'>Lynx</a> website to find information on releases, and additional documentation.

## Setup Guide
1. Install the Lynx browser via terminal.
   
	```
	brew install lynx
	```
     If you do not have homebrew installed on your device, follow the steps in the link provided: https://brew.sh.

2. On your terminal, check where your Lynx file is located.
	```
	which lynx
	```
     Output: (Note: This is what your output should look like)
	  ```
	 /usr/local/bin/lynx
	  ```
3. You can also check which version of Lynx you have by running the following line of code:
   	```
	lynx --version
	```
   
## Browsing Guide
1. Run the Lynx browser
   
     For a quick search run: (Note: This method only works when searching for specific websites, and does not hold for natural language search)
	  ```
	  lynx <insert web address or website name w/o the brackets>
	  ```
     Alternatively, run the line below and press 'g' on your keyboard to make a search. For instance, you can visit Duck Duck Go or Google simply by typing in Duck Duck Go or Google after the 'URL to open:' prompt.

	  ```
	  lynx
	  ```

## Granting Cookie Access
One reoccuring issue you will encounter are a series of prompts asking for permission on cookies for every search. This is because most modern websites on the web use or require cookies. Given that the default setting for LYNX is to disable cookies, to bypass the persistant prompts, and for ease of use, it is highly recommended to permananlty enable cookies on your browser. To do so, take the following steps:

1. If you go to Lynx via your terminal, and press 'o', you will see the default settings. All fields with (!) can only be altered temporarily (for that specific session). As can be seen in the sample image below, the setting for cookies (see 'Cookies (!)' under 'Security and Privacy') appear to be permanantly unchangeable. Even though the cookie settings cannot be altered permanantly through the settings screen, there is a alternative method to enable cookies in Lynx for good. However, there are a number of requirements before we can make those changes.

    <img width="630" alt="image_001" src="https://github.com/filsan95/Project-Lynx_Tutorial/assets/75952698/ae08918a-12dc-463d-a2e5-c8d4559c33c3">


2. You will need to access your shell profile (Note: In this case I am using bash as my shell, if using zsh replace with the following: sudo nano ~/.zshrc or sudo nano ~/.zprofile. Additionally, you can opt to replace nano with vim or emacs if preffered.)
	  ```
	  sudo nano /bash_profile
	  ```
3. Once you run the above line, enter your computer password.
4. Then enter the following line into your file, and exit with CTRL + X then press 'Y' to save changes made.
	  ```
	  alias lynx='lynx -accept_all_cookies'
	  ```
   To give a bit more detail about what this line does, if we run the command below in a terminal we'll open the version of Lynx with cookies disabled.
   	  ```
	  lynx
	  ```
   However, if we run this line, we run a version of Lynx with the cookies enabled.
	  ```
	  lynx -accept_all_cookies
	  ```
   Instead of running this lengthy line everytime we wish to use Lynx with all the cookies enabled, we create an alias for this to run as <code>lynx</code> instead of <code>lynx -accept_all_cookies</code>.
  
6. To execute your changes, run the following line:
	  ```
	  source ~/.bashrc
	  ```
7. Exit terminal, and reopen to use.

