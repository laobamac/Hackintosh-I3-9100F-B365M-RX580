# OpenCore Hackintosh for I3-9100F-B365M-RX580
<a href='README. Md '>Chinese</a>|<a href='README en. md'>English</a></br>
#Computer configuration
<table>
<thead>
<tr>
<th>Specification</th>
<th>Details</th>
</tr>
</thead>
<tbody>
<tr>
<td>Processor</td>
<td>Intel(R) Core I3-9100F@3.6Ghz 4C4T Processor</td>
</tr>
<tr>
<td>Memory</td>
<td>24GB DDR4 2400/2133MHz</td>
</tr>
<tr>
<td>Hard disk</td>
<td>South China Gold NVMe Solid 128G<del>Hitachi 500G Machinery</del></td>
</tr>
<tr>
<td>Wired network card</td>
<td>Realtek RTL 8111 Gigabit Network Card</td>
</tr>
<tr>
<td>Independent graphics card</td>
<td>Xunjing (XFX) RX580 4G 2304SP (In case of error, please write the BIOS by yourself)</td>
</tr>
<tr>
<td>Display</td>
<td>Aigon FHD 1920x1080</td>
</tr>
<tr>
<td>Sound card</td>
<td>Ruiyu ALC662 six channel high fidelity audio</td>
</tr>
<tr>
<td>Wireless network card</td>
<td>Broadcom BCM943224PCIEBT2</td>
</tr>
</tbody>
</table>

#Current situation
<ul dir="auto">
</ul>
</li>
<li><strong>Sleep</strong>Fully supports simultaneous<strong>power nap</strong></li>
</ul>
</li>
<li><strong>USB S3 Wakeup</strong>Fully supported</li>
</ul>
</li>
<li><strong>Aerial delivery relay</strong>It is fully supported in<code>macOS Big Sur</code>, and can only be one-way in<code>macOS Monterey</code><code>macOS Ventura</code>. It can only be solved by replacing CS2 and CD network cards</li>
</ul>
</li>
<li><strong>Follow flight</strong>Not supported! It cannot be used because it is not checked</li>
</ul>
</li>
<li><strong>HDMI</strong>Full support
<ul dir="auto">
<li>The minimum resolution is 1366 * 768, and 1680 * 1050 is not supported, otherwise your display may be damaged. 3 * DP and HDMI work normally, and DVI cannot output</li>
</ul>
</li>
<li><strong>Independent graphics card</strong>Fully supports error reporting. Please click VBIOS
<ul dir="auto">
<li>You can use<code><strong>AGPMInjector Kext</strong></code>for better power management support</li>
</ul>
</li>
<ul dir="auto">
</ul>
</li>
<li><strong>Broadcom Bluetooth</strong>Full support. If it is a 94360CS2, CD or other free drive card, please delete it yourself.<code>BlueToolFixup. kext</code><code>BrcmPatchRAM3. kext</code><code>BrcmFirmwareData. kext</code>
<ul dir="auto">
</ul>
</li>
<li>Support native<strong>CPU power management</strong>and other functions.<code>MacPro7,1</code>has been used to obtain<code>H264</code>and<code>HEVC</code>hard solution support</li>
</ul>
<ul dir="auto">
</ul>
</li>
<li><strong>USB3.0 may not be able to run at the speed of</strong><code>150M/s</code>. The measured speed is only about<code>42M/s</code>
<ul dir="auto">
<li>Customizing the USB port does not seem to solve this problem</li>
<li>Test 11. x-13. x fails to meet the requirements of<code>130M/s</code>in Windows (PS: 3.0 solid USB flash disk)</li>
</ul>
</li>

#BIOS Settings
<li>Disabe</li>
<li>Fast Boot</li>
<li>VT-D</li>
<li>CSM</li>
<li>Intel SGX</li>
<li>CFG Lock</li>
</br>
<li>Enable</li>
<li>VT-x</li>
<li>Above 4G decoding</li>
<li>Hyper-Threading</li>
<li>EHCI/XHCI Hand-off</li>
<li>OS type: Windows UEFI Mode (Clear Secure Boot Keys or choose Other type)</li>

#Usage
<ul dir="auto">
<li>Prepare to install the USB flash disk: refer to the official OC configuration, which is very useful:<a href=“ https://dortania.github.io/OpenCore-Install-Guide/installer-guide/mac-install.html#setting -Up-opencore-s-efi-environment "rel=" nofollow ">USB Creation</a>, including USB flash disk creation for macOS, Windows, and Linux</li>
<li>(Important) Use OCAT to open the config of the EFI I provide Plist Regenerate SystemSerialNumber/SystemUUID/MLB</li>
<li>Put the currently provided EFI into the USB flash drive EFI disk directory, indicating that the current EFI is used for booting</li>
<li>Power on to configure various configurations on the motherboard, and set the starting sequence of U disk UEFI as the first</li>
<li>Insert the USB stick, select the USB stick UEFI to start, and then install the system</li>
<li>After installation, enter the system successfully</ li>
</ul>

#Dual system time error
<li>This is a very common conflict between macOS and Windows, because the timing methods are different</li></br>
<li>The solution is also simple. The administrator cmd executes it under Windows</li></br>
<div class="snippet-clipboard-content notranslate position-relative overflow-auto" data-snippet-clipboard-copy-content="Reg add HKLM\SYSTEM\CurrentControlSet\Control\TimeZoneInformation /v RealTimeIsUniversal /t REG_DWORD /d 1"><pre class="notranslate"><code>Reg add HKLM\SYSTEM\CurrentControlSet\Control\TimeZoneInformation /v RealTimeIsUniversal /t REG_DWORD /d 1</code></pre></div>

#Set Default Startup Entry
<ul dir="auto">
<li>
<p dir="auto"><code>config. plist</code>Tick the shortcut key of counterfeit apple<code>PollAppleHotKey</code>, select the item to be started in the startup selection interface, and then press<code>Ctrl</code>+<code>Enter</code>on the keyboard to Enter the system</p>
</li>
<li>
<p dir="auto">It has also been seen that you can select the default boot item in<code>Settings</code>-<code>Boot Disk</code>, and restart after modification</p>
</li>
</ul>

#Acknowledgement
<ul dir="auto">
<li>Thanks<a href=' https://space.bilibili.com/244390800 '>@ A dozen Oolong peach</a>The idea of powering off the display provided</li>
<li>Best Getting Started Tutorial:<a href=“ https://dortania.github.io/OpenCore-Install-Guide/ " rel="nofollow">OpenCore Install Guide</a></li>
<li>Chinese Tutorial:<a href=“ https://blog.xjn819.com/post/opencore-guide.html "Rel=" nofollow ">Xjn's blog</a></li>
<li>Chinese Document; Download the kexts collection:<a href=“ https://oc.skk.moe/ "Rel=" nofollow ">OpenCore Chinese documents</a></li>
<li>Image Download& Chinese Tutorial:<a href=“ http://blog.daliansky.net "Rel=" nofollow ">Black Fruit Soldier</a></li>
</ul>

#Links
<li><a href=' https://apple.laobamac.fun/ '>The tribal pavilion of Laoba Heiguo - Blog is quiet and farsighted</a></li>
<li>Bili Bili<a href=' https://space.bilibili.com/504306154/ '>Laoba takes you to play Blackberry's homepage</a></li>
