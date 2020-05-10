---
layout: page
title: 关于
permalink: /about/
---

# AES 加密

## 多密码加密

<div class="AES">
	<div class="keys">
        <input type="password" class="pwInput" id="key_1" placeholder="密钥1">
        <input type="password" class="pwInput" id="key_2" placeholder="密钥2">
        <input type="password" class="pwInput" id="key_3" placeholder="密钥3">
        <p><input type="checkbox" id="pwShow" value="pwShow" />是否明文显示密钥 </p>
        <script>        
          function checkPWShow() 
          {            
            document.getElementById("pwShow").onclick = function () {                
              var arr = new Array();                
              var items = document.getElementsByName("pwShow");                 
              if (document.getElementById("pwShow").checked) {
                document.getElementById("key_1").type="text";
                document.getElementById("key_2").type="text";
                document.getElementById("key_3").type="text";
              }
              else
              {
                document.getElementById("key_1").type="password";
                document.getElementById("key_2").type="password";
                document.getElementById("key_3").type="password";
              }
            };        
          };
          checkPWShow();    
        </script>
      </div>
	<div class="buttonsContainer">
		<input class="nbutton" type="button" value="加密" onclick="encrypt()">
		<button class="nbutton" id="ResultCopyer" onclick="ResultCopyer()">复制加密后内容</button>
		<font id="CopySuccessMessage"></font>
	  </div>
	<p id="result">莫得加密内容,请先加密</p>
	<div class="expandingArea">
   		<textarea rows="50" class="orginTxt" id="encryptOrDecriptMessage" placeholder="输入待加密文本" style="height:1em" autocomplete="off"></textarea>
		<script type="text/javascript">
		var observe;
		if (window.attachEvent) {
			observe = function (element, event, handler) {
				element.attachEvent('on'+event, handler);
			};
		}
		else {
			observe = function (element, event, handler) {
				element.addEventListener(event, handler, false);
			};
		}
		function init () {
			var text = document.getElementById('encryptOrDecriptMessage');
			function resize () {
				text.style.height = 'auto';
				text.style.height = text.scrollHeight+'px';
			}
			/* 0-timeout to get the already changed text */
			function delayedResize () {
				window.setTimeout(resize, 0);
			}
			observe(text, 'change',  resize);
			observe(text, 'cut',     delayedResize);
			observe(text, 'paste',   delayedResize);
			observe(text, 'drop',    delayedResize);
			observe(text, 'keydown', delayedResize);
			text.focus();
			text.select();
			resize();
		}
		init();
		</script>
	</div>
</div>