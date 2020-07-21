---


---

<h1 id="tmux">tmux</h1>
<h2 id="config-file">Config file</h2>
<p>In <code>~/.tmux.conf</code>:</p>
<pre class=" language-vim"><code class="prism  language-vim"># History
<span class="token keyword">set</span> <span class="token operator">-</span>g <span class="token keyword">history</span><span class="token operator">-</span>limit <span class="token number">10000</span>

# search <span class="token keyword">mode</span> VI
<span class="token keyword">set</span><span class="token operator">-</span><span class="token builtin">window</span><span class="token operator">-</span>option <span class="token operator">-</span>g <span class="token keyword">mode</span><span class="token operator">-</span>keys <span class="token keyword">vi</span>

run<span class="token operator">-</span><span class="token keyword">shell</span> <span class="token operator">/</span><span class="token keyword">opt</span><span class="token operator">/</span>tmux<span class="token operator">-</span>logging<span class="token operator">/</span>logging<span class="token operator">.</span>tmux
</code></pre>
<h2 id="shortcuts">Shortcuts</h2>
<p><kbd>ctrl</kbd>+<kbd>b</kbd> : Prefix<br>
Prefix then :<br>
<kbd>c</kbd> : new tmux window<br>
<kbd>,</kbd> : rename window<br>
<kbd>3</kbd> : switch to window n°3<br>
<kbd>alt</kbd><kbd>shift</kbd><kbd>p</kbd> : save history output in log file<br>
<kbd>%</kbd> : Vertical split<br>
<kbd>"</kbd> : Horizontal split<br>
<kbd>Arrows</kbd> : Switch pane<br>
(maintaining <kbd>ctrl</kbd>)<kbd>Arrows</kbd> :  resize pane<br>
<kbd>z</kbd> : Zoom in/out</p>
<h3 id="vi-search-mode">VI search mode</h3>
<p>Prefix and <kbd>[</kbd> : VI edit mode<br>
In VI mode:<br>
<kbd>space</kbd> : selection mode. Use arrow key or Pg Up/Down to select lines you want to copy.<br>
<kbd>enter</kbd> : Copy the selection in a buffer. Hitting enter will quit VI edit mode.<br>
<kbd>]</kbd> : In VI mode, paste the buffer content</p>

