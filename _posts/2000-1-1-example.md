---
layout: post
title: Example
date: 2020-02-11
Author: Author
tags: [tag1, tag2]
---


<div class="containerDiv">
	<textarea id="encryptOrDecriptMessage" readonly="readonly" style="display:none">
    替换成你加密后得到的字符串
	</textarea>
	<input type="text" id="key_1" placeholder="密钥">
	<input type="text" id="key_2" placeholder="密钥">
	<input type="text" id="key_3" placeholder="密钥">
	<div class="buttonsContainer">
	<input type="button" value="解密" onclick="decrypt()">
	</div>
	<p id="result">???</p>
</div>
