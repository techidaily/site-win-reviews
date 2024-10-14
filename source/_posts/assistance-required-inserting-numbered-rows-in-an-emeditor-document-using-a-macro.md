---
title: "Assistance Required: Inserting Numbered Rows in an EmEditor Document Using a Macro"
date: 2024-10-13T16:59:26.639Z
updated: 2024-10-14T16:56:56.918Z
tags:
  - product
categories:
  - emeditor
thumbnail: https://thmb.techidaily.com/93d0d2f898ab9f2aada0c8c4eae12b5163704e3e0107a7a0c827d88713775503.png
---

## Assistance Required: Inserting Numbered Rows in an EmEditor Document Using a Macro

Viewing 10 posts - 1 through 10 (of 10 total)

* Author  
Posts
* March 30, 2010 at 7:18 pm [#8240](https://tools.techidaily.com/emeditor/products/)  
[![](https://secure.gravatar.com/avatar/7b5f4b0747b67d5f8b87e5b7dd57367b?s=80&d=identicon&r=g)zhouzh2](https://www.emeditor.com/forums/users/zhouzh2/ "View zhouzh2's profile")  
Participant  
I wrote this for inserting number row. both in this kind:  
a=1  
	b=2  
	c=3  
	..  
	 and:  
a = 1  somethinghere  
	b = 2  somethinghere  
	c = 3  somethinghere  
	..  
	 It is supposed to work from number 0 to 99 or 99 to 0.  
/*insertNumbers.jsee*/  
	/*Insert numbers in a row*/  
	    
	var i = prompt("Please enter the start number (not larger than 99)", 0);  
	var n = prompt("Please enter the end number (not larger than 99)", 1); //promote  
	    
	if ((i == "")|| (n == "")){Quit();};  
	if ((i > 99)|| (i < 0) || (n > 99)||(n < 0)) {alert("Error!"); Quit();}; //errors  
	    
	cfg = document.Config;  
	var userVSsetting = cfg.General.VirtualSpace;  
	cfg.General.VirtualSpace = 'true';  
	cfg.Save(); //enable VirtualSpace so that when inserting at '^a=nb=n...' will run normally.  
	    
	status = "Inserting - Please Wait...";  
	    
	if (i < n) {  
		n++;  
		while (i < 10){  
			document.selection.Text=i;  
			document.selection.LineDown(false,1);  
			document.selection.CharLeft(false,1);  
			i++;  
			if (i == n) {insertEnd();};  
		};  
		while (i <= 99){  
			document.selection.Text=i;  
			document.selection.LineDown(false,1);  
			document.selection.CharLeft(false,1);  
			document.selection.CharLeft(false,1);  
			i++;  
			if (i == n) {insertEnd();};  
		};  
	}; //ascending  
	    
	else {  
		n--;  
		while (i >= 10){  
			document.selection.Text=i;  
			document.selection.LineDown(false,1);  
			document.selection.CharLeft(false,1);  
			document.selection.CharLeft(false,1);  
			i--;  
			if (i == n) {insertEnd();};  
		};  
		while (i < 10){  
			document.selection.Text=i;  
			document.selection.LineDown(false,1);  
			document.selection.CharLeft(false,1);  
			i--;  
			if (i == n) {insertEnd();};  
		};  
	}; //descending  
	    
	function insertEnd(){  
		cfg.General.VirtualSpace = userVSsetting;  
		cfg.Save();  
		status = "Inserting Completed";  
		Quit();  
	};  
	 However, this macro will be trapped in a loop under a certain situation, i.e. when 1<i<10 and="" n="">10, or when 10<i<=99 and="" n<10="" (however="" the="" latter="" will="" not="" always="" appear.)="" but="" i="" cannot="" find="" out="" why.="" anyone="" please="" help="" me="" with="" that="" :-(<="" p=""></i<=99></i<10>  
April 3, 2010 at 11:34 am [#8269](https://tools.techidaily.com/emeditor/products/)  
[![](https://secure.gravatar.com/avatar/7b5f4b0747b67d5f8b87e5b7dd57367b?s=80&d=identicon&r=g)zhouzh2](https://www.emeditor.com/forums/users/zhouzh2/ "View zhouzh2's profile")  
Participant  
no one interested?:-(
April 6, 2010 at 5:46 am [#8304](https://tools.techidaily.com/emeditor/products/)  
[![](https://secure.gravatar.com/avatar/9dac5ab27354edc3ff070db8ce1a1a66?s=80&d=identicon&r=g)ToadLoadin](https://www.emeditor.com/forums/users/ToadLoadin/ "View ToadLoadin's profile")  
Member  
Hi zhouzh2,  
 If your “somethinghere” in every line is exactly the same:  
>  
>  
> a=1  
>  
> b=2  
>  
> c=3  
>  
> ..  
>  
> and:  
>  
>  
>  
> a = 1  somethinghere  
>  
> b = 2  somethinghere  
>  
> c = 3  somethinghere  
>  
> ..  
 perhaps you could use “Insert Number Sequence” plugin, the Simplified Chinese version is here.  
April 6, 2010 at 4:13 pm [#8307](https://tools.techidaily.com/emeditor/products/)  
[![](https://secure.gravatar.com/avatar/7b5f4b0747b67d5f8b87e5b7dd57367b?s=80&d=identicon&r=g)zhouzh2](https://www.emeditor.com/forums/users/zhouzh2/ "View zhouzh2's profile")  
Participant  
Thanks ToadLoadin :-)  
 I know there is such a plug-in.  
 However, a 32bit plug-in will not work on a 64bit Emeditor.  
 Furthermore, I would prefer a macro if the macro can do what I want, since it saves hardware recourse.  
 “somethinghere” is not what I want to insert. This is just one of the situation when inserting numbers. Under the above two situation a macro should behave accoradingly to insert numbers correctly. To surpass this I temporarily enables the VirtualSpace and restores it when finished.  
 The problem here is when entering a start number greater than 2, the macro will stack in a infinite loop, but I can’t find out why…from I point of view, this macro should run correctly :-?  
April 21, 2010 at 12:49 pm [#8390](https://tools.techidaily.com/emeditor/products/)  
[![](https://secure.gravatar.com/avatar/9dac5ab27354edc3ff070db8ce1a1a66?s=80&d=identicon&r=g)ToadLoadin](https://www.emeditor.com/forums/users/ToadLoadin/ "View ToadLoadin's profile")  
Member  
Hi zhouzh2,  
 I modified your macro to this:  
cfg = document.Config;  
	var userVSsetting = cfg.General.VirtualSpace;  
	cfg.General.VirtualSpace = 'true';  
	cfg.Save(); //enable VirtualSpace so that when inserting at '^a=nb=n...' will run normally.  
	    
	var i = prompt("Please enter the start number (not larger than 99)", 0);  
	var n = prompt("Please enter the end number (not larger than 99)", 1); //promote  
	    
	if ((i == "")|| (n == "")){Quit();};  
	if ((i > 99)|| (i < 0) || (n > 99)||(n < 0)) {alert("Error!"); Quit();}; //errors  
	    
	// Get current cursor position  
	    var iCol = document.selection.GetActivePointX(eePosLogicalA);  
	    var iLine = document.selection.GetActivePointY(eePosLogical);  
	// Caculate the number of lines  
	    var nLines = Math.abs(i-n)+1;  
	    
	status = "Inserting - Please Wait...";  
	    
	for (var j=0; j < nLines; j++) {  
	    document.selection.SetActivePoint(eePosLogicalA, iCol, iLine+j);  
	    if (i < n) { //ascending  
	    	document.selection.Text = i;  
	    	i++;  
	    } else { //descending  
	    	document.selection.Text = i;  
	    	i--;  

	    
	cfg.General.VirtualSpace = userVSsetting;  
	cfg.Save();  
	status = "Inserting Completed";  
	Quit();  
 And observed an interesting issue, as you noticed:  
> when 1<i10, or when 10<i<=99 and n<10  
 The first number inserted will be the biggest one, I guess that’s why your macro fall into a infinite loop, but I can not figure out why this happens, perhaps a bug? 8-)  
April 22, 2010 at 2:36 pm [#8395](https://tools.techidaily.com/emeditor/products/)  
[![](https://secure.gravatar.com/avatar/7b5f4b0747b67d5f8b87e5b7dd57367b?s=80&d=identicon&r=g)zhouzh2](https://www.emeditor.com/forums/users/zhouzh2/ "View zhouzh2's profile")  
Participant  
Hi ToadLoadin,  
 Thanks a lot for your help. Your macro is a lot elegant than my silly one :-)  
 Yeah I agree with you that this is strange and might be a bug, not so sure though.  
 Any other JavaScript expert please come to our rescue :-?  
 (Yutaka? 8-))  
April 23, 2010 at 4:58 pm [#8401](https://tools.techidaily.com/emeditor/products/)  
[![](https://secure.gravatar.com/avatar/a5419c90a5fab214126e05752d74da1c?s=80&d=identicon&r=g)tonne](https://www.emeditor.com/forums/users/tonne/ "View tonne's profile")  
Participant  
Try  
 if (Math.abs(i) < Math.abs(n)) { //ascending  
April 24, 2010 at 1:49 am [#8402](https://tools.techidaily.com/emeditor/products/)  
[![](https://secure.gravatar.com/avatar/9dac5ab27354edc3ff070db8ce1a1a66?s=80&d=identicon&r=g)ToadLoadin](https://www.emeditor.com/forums/users/ToadLoadin/ "View ToadLoadin's profile")  
Member  
> tonne wrote:  
> Try  
> if (Math.abs(i) < Math.abs(n)) { //ascending  
 That works!\~\~ :-) But…why that works? :-(
April 24, 2010 at 8:22 am [#8403](https://tools.techidaily.com/emeditor/products/)  
[![](https://secure.gravatar.com/avatar/a5419c90a5fab214126e05752d74da1c?s=80&d=identicon&r=g)tonne](https://www.emeditor.com/forums/users/tonne/ "View tonne's profile")  
Participant  
prompt returns a string; is “2” < "10" ?  
April 24, 2010 at 9:55 am [#8404](https://tools.techidaily.com/emeditor/products/)  
[![](https://secure.gravatar.com/avatar/9dac5ab27354edc3ff070db8ce1a1a66?s=80&d=identicon&r=g)ToadLoadin](https://www.emeditor.com/forums/users/ToadLoadin/ "View ToadLoadin's profile")  
Member  
> tonne wrote:  
> prompt returns a string; is “2” < "10" ?  
 OIC, it’s a string comparison instead of integer one.  
 Thank you! :-D
* Author  
Posts

Viewing 10 posts - 1 through 10 (of 10 total)

* You must be logged in to reply to this topic.

<ins class="adsbygoogle"
     style="display:block"
     data-ad-format="autorelaxed"
     data-ad-client="ca-pub-7571918770474297"
     data-ad-slot="1223367746"></ins>

<ins class="adsbygoogle"
     style="display:block"
     data-ad-client="ca-pub-7571918770474297"
     data-ad-slot="8358498916"
     data-ad-format="auto"
     data-full-width-responsive="true"></ins>

<span class="atpl-alsoreadstyle">Also read:</span>
<div><ul>
<li><a href="https://screen-recording.techidaily.com/new-best-screenshots-software-series/"><u>[New] Best Screenshots Software Series</u></a></li>
<li><a href="https://eaxpv-info.techidaily.com/new-final-step-guide-free-yourself-from-youtube-shorts-for-2024/"><u>[New] Final Step Guide Free Yourself From YouTube Shorts for 2024</u></a></li>
<li><a href="https://visual-screen-recording.techidaily.com/new-premier-productions-first-impression-for-2024/"><u>[New] Premier Productions First Impression for 2024</u></a></li>
<li><a href="https://youtube-web.techidaily.com/ed-achieving-video-popularity-mastering-youtube-thumbnail-selection-for-2024/"><u>[Updated] Achieving Video Popularity Mastering YouTube Thumbnail Selection for 2024</u></a></li>
<li><a href="https://facebook.techidaily.com/detailed-breakdown-of-every-action-on-your-facebook-page/"><u>Detailed Breakdown of Every Action on Your Facebook Page</u></a></li>
<li><a href="https://win-reviews.techidaily.com/emeditor-text-editor-update-introducing-the-essential-unicode-utf8-sort-string-plugin/"><u>EmEditor Text Editor Update: Introducing the Essential Unicode UTF8 Sort String Plugin!</u></a></li>
<li><a href="https://win-reviews.techidaily.com/fixing-the-persistent-folders-issue-in-file-shares-with-emeditor-text-editor/"><u>Fixing the 'Persistent Folders Issue' In File Shares with EmEditor Text Editor</u></a></li>
<li><a href="https://win-reviews.techidaily.com/how-to-use-emeditor-with-mapped-drives-in-linux-a-text-editing-guide/"><u>How to Use EmEditor with Mapped Drives in Linux - A Text Editing Guide</u></a></li>
<li><a href="https://ios-unlock.techidaily.com/in-2024-how-do-you-remove-restricted-mode-on-apple-iphone-12-pro-by-drfone-ios/"><u>In 2024, How Do You Remove Restricted Mode on Apple iPhone 12 Pro</u></a></li>
<li><a href="https://android-frp.techidaily.com/in-2024-ultimate-guide-on-samsung-galaxy-f34-5g-frp-bypass-by-drfone-android/"><u>In 2024, Ultimate Guide on Samsung Galaxy F34 5G FRP Bypass</u></a></li>
<li><a href="https://win11-tips.techidaily.com/mend-erratic-scrolls-in-your-digital-display/"><u>Mend Erratic Scrolls in Your Digital Display</u></a></li>
<li><a href="https://win-reviews.techidaily.com/quickly-close-unused-tab-feature-in-emeditor-text-editing-efficiency-enhancement/"><u>Quickly Close Unused Tab Feature in EmEditor - Text Editing Efficiency Enhancement</u></a></li>
<li><a href="https://buynow-reviews.techidaily.com/top-picks-why-the-oneplus-nord-n10-5g-stands-out-in-a-crowded-market/"><u>Top Picks: Why the OnePlus Nord N10 5G Stands Out in a Crowded Market</u></a></li>
</ul></div>

<!-- affiliate ads begin -->
<a href="https://appsumo.8odi.net/c/5597632/2130871/7443" target="_top" id="2130871">
  <img src="//a.impactradius-go.com/display-ad/7443-2130871" border="0" alt="https://techidaily.com" width="728" height="90"/>
</a>
<img height="0" width="0" src="https://appsumo.8odi.net/i/5597632/2130871/7443" style="position:absolute;visibility:hidden;" border="0" />
<!-- affiliate ads end -->

