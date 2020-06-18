---


---

<h1 id="nmap">Nmap</h1>
<h2 id="port-specification">Port Specification</h2>

<table>
<thead>
<tr>
<th>Scan</th>
<th>Examples</th>
</tr>
</thead>
<tbody>
<tr>
<td>Port scan all ports</td>
<td><code>nmap 192.168.1.1 -p-</code></td>
</tr>
<tr>
<td>Port scan from service name</td>
<td><code>nmap 192.168.1.1 -p http,https</code></td>
</tr>
</tbody>
</table><h2 id="scan-technique">Scan technique</h2>

<table>
<thead>
<tr>
<th>Scan</th>
<th>Examples</th>
</tr>
</thead>
<tbody>
<tr>
<td>TCP SYN port scan (Default)</td>
<td><code>nmap 192.168.1.1 -sS</code></td>
</tr>
<tr>
<td>TCP connect port scan (Default without root privilege)</td>
<td><code>nmap 192.168.1.1 -sT</code></td>
</tr>
<tr>
<td>UDP port scan</td>
<td><code>nmap 192.168.1.1 -sU</code></td>
</tr>
<tr>
<td>TCP ACK port scan</td>
<td><code>nmap 192.168.1.1 -sA</code></td>
</tr>
<tr>
<td>TCP Window port scan</td>
<td><code>nmap 192.168.1.1 -sW</code></td>
</tr>
<tr>
<td>TCP Maimon port scan</td>
<td><code>nmap 192.168.1.1 -sM</code></td>
</tr>
</tbody>
</table><h2 id="service-and-version-detection">Service and version detection</h2>

<table>
<thead>
<tr>
<th>Scan</th>
<th>Examples</th>
</tr>
</thead>
<tbody>
<tr>
<td>Attempts to determine the version of the service running on port</td>
<td><code>nmap 192.168.1.1 -sV</code></td>
</tr>
<tr>
<td>Enables OS detection, version detection, script scanning, and traceroute</td>
<td><code>nmap 192.168.1.1 -A</code></td>
</tr>
</tbody>
</table><h2 id="nse-script">NSE Script</h2>

<table>
<thead>
<tr>
<th>Scan</th>
<th>Examples</th>
</tr>
</thead>
<tbody>
<tr>
<td>Scan with default NSE scripts. Considered useful for discovery and safe</td>
<td><code>nmap 192.168.1.1 -sC</code></td>
</tr>
</tbody>
</table><p><a href="https://resources.infosecinstitute.com/nmap/">https://resources.infosecinstitute.com/nmap/</a></p>
<p><a href="https://www.frameip.com/scanner-port-tcp-udp/#72-8211nmap">https://www.frameip.com/scanner-port-tcp-udp/#72-8211nmap</a></p>
<p><a href="https://nmap.org/">https://nmap.org/</a></p>
<p><a href="https://www.softwaretestinghelp.com/ddos-attack-tools/">https://www.softwaretestinghelp.com/ddos-attack-tools/</a></p>

