---
title: How to Locate the Largest Value in a Text File with EmEditor
date: 2024-10-08T16:45:03.258Z
updated: 2024-10-14T16:51:32.807Z
tags:
  - product
categories:
  - emeditor
thumbnail: https://thmb.techidaily.com/f1294d51d8e0560c6776b360116bd819890055c0bb65c23b15603692f6dffac9.jpg
---

## How to Locate the Largest Value in a Text File with EmEditor

November 5, 2011 at 6:14 pm [#9804](https://tools.techidaily.com/emeditor/products/) 

[![](https://secure.gravatar.com/avatar/f29c043a3cc5c5dac8db4e62939893e9?s=80&d=identicon&r=g)Stefan](https://www.emeditor.com/forums/users/Stefan/ "View Stefan's profile")

Participant

No, an RegEx is an pattern matching system only.  
 There are very little comparing features.

 You will need to use an macro/script for that.  
 How that macro will work and what you will get as   
 result depends on your real current needs and how   
 the rest of the line looks a like: are that digits   
 and tabs the only signs in such an line?

 Here is an quick example code.  
Be sure to use this always with copies of your importent documents.   
 Because i don’t have an impression what could get worse.  
 If anyone should improve this script for you we will need an   
 better example how the rest of such an line will look a like.

 Ahh, and this script will work only with tabs as delimiter  
 or it have to be adjusted as one needs.
	  

	////===== Description: ==================  

	//// Click into an line and execute this macro/script.  

	//// The line will split at tab stops   

	//// and if an part is detected as an number  

	//// the greatest number is stored as vBiggestNumber for your use.  
	  

	//// ====== Setting: ====================  

	//// Split line at tab. Use your own delimiter if needed:  

	SplitAt = "t";  
	  

	//// ====== Work: ======================  

	//// Get current line content:  

	document.selection.SelectLine();  

	CurrLine = document.selection.text;  

	//// Call function to split str and find biggest number:  

	vBiggestNumber = ReturnLargedNumber(CurrLine, SplitAt);  
	  

	//// ====== End: =======================  

	//// Do something with the result:  

	alert('result: >' + vBiggestNumber + '<');  

	//document.selection.Collapse();  

	//document.selection.NewLine();  

	document.selection.text = vBiggestNumber;  
	  

	////======================================  

	////======== Function =====================  

	function ReturnLargedNumber(str,delim)  

	    Tokens = str.split(delim);  

	    vMaxNumber = 0;  

	    for (x = 0; x < Tokens.length; x++)   

	       vCurrentNumb = Tokens[x];   

	       if (!isNaN(vCurrentNumb))  

	          if (Number(vCurrentNumb) > vMaxNumber)  

	            vMaxNumber = vCurrentNumb;  

	 return vMaxNumber;  

	  

	 HTH? :-D

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
<li><a href="https://facebook-video-footage.techidaily.com/new-2024-approved-engaging-youtube-summaries-with-tailored-templates/"><u>[New] 2024 Approved Engaging YouTube Summaries with Tailored Templates</u></a></li>
<li><a href="https://article-helps.techidaily.com/updated-drone-motors-choose-the-5-best-motors-for-your-quadcopter-for-2024/"><u>[Updated] Drone Motors Choose the 5 Best Motors for Your Quadcopter for 2024</u></a></li>
<li><a href="https://facebook-record-videos.techidaily.com/updated-top-editors-for-youtube-writers-and-creators-all-free/"><u>[Updated] Top Editors for YouTube' Writers and Creators - All Free</u></a></li>
<li><a href="https://win-reviews.techidaily.com/assistance-required-inserting-numbered-rows-in-an-emeditor-document-using-a-macro/"><u>Assistance Required: Inserting Numbered Rows in an EmEditor Document Using a Macro</u></a></li>
<li><a href="https://win-forum.techidaily.com/effective-remedies-when-windows-explorer-frequently-fails-uncover-secrets/"><u>Effective Remedies When Windows Explorer Frequently Fails - Uncover Secrets</u></a></li>
<li><a href="https://win-reviews.techidaily.com/efficiently-edit-your-documents-at-home-with-emeditor-a-comprehensive-text-editor-program/"><u>Efficiently Edit Your Documents at Home with EmEditor - A Comprehensive Text Editor Program</u></a></li>
<li><a href="https://win-reviews.techidaily.com/emeditor-text-editor-update-introducing-the-essential-unicode-utf8-sort-string-plugin/"><u>EmEditor Text Editor Update: Introducing the Essential Unicode UTF8 Sort String Plugin!</u></a></li>
<li><a href="https://hardware-help.techidaily.com/get-your-tp-link-adapter-up-to-date-download-latest-drivers-for-windows-11-8-and-7/"><u>Get Your TP-Link Adapter Up to Date: Download Latest Drivers for Windows 11, 8 & 7</u></a></li>
<li><a href="https://win-reviews.techidaily.com/how-to-use-emeditor-with-mapped-drives-in-linux-a-text-editing-guide/"><u>How to Use EmEditor with Mapped Drives in Linux - A Text Editing Guide</u></a></li>
<li><a href="https://win-reviews.techidaily.com/professional-text-editing-with-emeditor-version-700-beta-advanced-features/"><u>Professional Text Editing with EmEditor Version 7.00 BETA - Advanced Features</u></a></li>
<li><a href="https://extra-information.techidaily.com/scripting-stimulating-screen-grabbers/"><u>Scripting Stimulating Screen-Grabbers</u></a></li>
<li><a href="https://technical-tips.techidaily.com/step-by-step-guide-adding-programming-codes-into-microsoft-word/"><u>Step-by-Step Guide: Adding Programming Codes Into Microsoft Word</u></a></li>
<li><a href="https://win-reviews.techidaily.com/troubleshooting-emeditors-typographical-issue-correcting-an-erroneous-cursor-positioning-error/"><u>Troubleshooting EmEditor's Typographical Issue: Correcting an Erroneous Cursor Positioning Error</u></a></li>
</ul></div>

<!-- affiliate ads begin -->
<a href="https://bluettius.sjv.io/c/5597632/2139117/17108" target="_top" id="2139117">
  <img src="//a.impactradius-go.com/display-ad/17108-2139117" border="0" alt="https://techidaily.com" width="320" height="90"/>
</a>
<img height="0" width="0" src="https://bluettius.sjv.io/i/5597632/2139117/17108" style="position:absolute;visibility:hidden;" border="0" />
<!-- affiliate ads end -->

