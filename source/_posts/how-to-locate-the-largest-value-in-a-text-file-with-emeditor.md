---
title: How to Locate the Largest Value in a Text File with EmEditor
date: 2024-10-03T17:37:57.620Z
updated: 2024-10-08T17:36:55.137Z
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
<li><a href="https://youtube-lab.techidaily.com/ed-2024-approved-escalate-your-channels-popularity-to-1kplus/"><u>[Updated] 2024 Approved Escalate Your Channel's Popularity to 1K+</u></a></li>
<li><a href="https://fox-blue.techidaily.com/updated-digital-frontier-leaders-the-quintessential-cloud-picks-for-your-needs/"><u>[Updated] Digital Frontier Leaders The Quintessential Cloud Picks for Your Needs</u></a></li>
<li><a href="https://article-tips.techidaily.com/updated-in-2024-rendering-reality-realistic-3d-text-effects/"><u>[Updated] In 2024, Rendering Reality Realistic 3D Text Effects</u></a></li>
<li><a href="https://some-approaches.techidaily.com/updated-unveiling-the-world-in-a-whole-view-video-edition/"><u>[Updated] Unveiling the World in a Whole View Video Edition</u></a></li>
<li><a href="https://mondly-stories.techidaily.com/a-tapestry-of-classroom-vocabulary-international-day-honors/"><u>A Tapestry of Classroom Vocabulary: International Day Honors</u></a></li>
<li><a href="https://win-reviews.techidaily.com/convert-videos-on-mac-at-no-cost-top-free-mac-video-conversion-tools/"><u>Convert Videos on Mac at No Cost: Top Free Mac Video Conversion Tools</u></a></li>
<li><a href="https://win-reviews.techidaily.com/easy-methods-for-data-restoration-on-external-drives/"><u>Easy Methods for Data Restoration on External Drives</u></a></li>
<li><a href="https://win-reviews.techidaily.com/easy-tutorial-on-recovering-voice-recordings-from-your-ios-device/"><u>Easy Tutorial on Recovering Voice Recordings From Your iOS Device</u></a></li>
<li><a href="https://win-reviews.techidaily.com/effortlessly-transform-your-vob-files-into-high-quality-mov-videos/"><u>Effortlessly Transform Your VOB Files Into High-Quality MOV Videos</u></a></li>
<li><a href="https://win-reviews.techidaily.com/enhanced-handbrake-replacement-superior-stability-and-diverse-output-formats-with-audio-support/"><u>Enhanced Handbrake Replacement: Superior Stability & Diverse Output Formats with Audio Support</u></a></li>
<li><a href="https://bypass-frp.techidaily.com/in-2024-easy-guide-how-to-bypass-honor-x50-frp-android-10111213-by-drfone-android/"><u>In 2024, Easy Guide How To Bypass Honor X50 FRP Android 10/11/12/13</u></a></li>
<li><a href="https://visual-screen-recording.techidaily.com/in-2024-uncharted-territory-6-secrets-to-documenting-your-minecraft-journey/"><u>In 2024, Uncharted Territory 6 Secrets to Documenting Your Minecraft Journey</u></a></li>
<li><a href="https://win-reviews.techidaily.com/optimal-techniques-for-capturing-high-quality-voip-conversations/"><u>Optimal Techniques for Capturing High-Quality VoIP Conversations</u></a></li>
<li><a href="https://win-reviews.techidaily.com/step-by-step-guide-capturing-your-epic-fortnite-battles-across-desktop-and-mobile/"><u>Step-by-Step Guide: Capturing Your Epic Fortnite Battles Across Desktop & Mobile</u></a></li>
<li><a href="https://win-reviews.techidaily.com/step-by-step-guide-merging-multiple-photos-into-a-single-pdf-file/"><u>Step-by-Step Guide: Merging Multiple Photos Into a Single PDF File</u></a></li>
<li><a href="https://solve-help.techidaily.com/the-ultimate-guide-to-choosing-an-excellent-book-reading-app-for-ipads/"><u>The Ultimate Guide to Choosing an Excellent Book Reading App for iPads</u></a></li>
<li><a href="https://android-pokemon-go.techidaily.com/ultimate-guide-to-get-the-meltan-box-pokemon-go-for-oppo-reno-8t-drfone-by-drfone-virtual-android/"><u>Ultimate guide to get the meltan box pokemon go For Oppo Reno 8T | Dr.fone</u></a></li>
</ul></div>

<!-- affiliate ads begin -->
<a href="https://appsumo.8odi.net/c/5597632/2118326/7443" target="_top" id="2118326">
  <img src="//a.impactradius-go.com/display-ad/7443-2118326" border="0" alt="https://techidaily.com" width="728" height="90"/>
</a>
<img height="0" width="0" src="https://appsumo.8odi.net/i/5597632/2118326/7443" style="position:absolute;visibility:hidden;" border="0" />
<!-- affiliate ads end -->

