# OpenCore Hackintosh for I3-9100F-B365M-RX580
# 电脑配置
<table>
<thead>
<tr>
<th>规格</th>
<th>详细信息</th>
</tr>
</thead>
<tbody>
<tr>
<td>处理器</td>
<td>Intel(R) Core I3-9100F@3.6Ghz 4C4T Processor</td>
</tr>
<tr>
<td>内存</td>
<td>24GB DDR4 2400/2133MHz</td>
</tr>
<tr>
<td>硬盘</td>
<td>华南金牌 NVMe固态 128G <del>日立500G机械</del></td>
</tr>
<tr>
<td>有线网卡</td>
<td>Realtek RTL 8111 千兆网卡</td>
</tr>
<tr>
<td>独立显卡</td>
<td>讯景（XFX）RX580 4G 2304SP（发生报错请自行刷写BIOS）</td>
</tr>
<tr>
<td>显示器</td>
<td>Aigon FHD 1920x1080</td>
</tr>
<tr>
<td>声卡</td>
<td>瑞昱 ALC662 六声道 高保真音频</td>
</tr>
<tr>
<td>无线网卡</td>
<td>博通 BCM943224PCIEBT2</td>
</tr>
</tbody>
</table>

# 目前情况
<ul dir="auto">
</ul>
</li>
<li><strong>睡眠</strong> 完全支持 同时实现<strong>电源小憩</strong></li>
</ul>
</li>
<li><strong>USB的S3唤醒</strong> 完全支持</li>
</ul>
</li>
<li><strong>隔空投送-接力</strong> 在<code>macOS Big Sur</code>完全支持，在<code>macOS Monterey</code><code>macOS Ventura</code>只能单向，更换CS2、CD网卡解决</li>
</ul>
</li>
<li><strong>随航</strong>不支持！由于没有核显，所以无法使用。</li>
</ul>
</li>
<li><strong>HDMI</strong> 完全支持
<ul dir="auto">
<li>最低分辨率1366*768，不支持1680*1050，否则可能会损坏你的显示器。3*DP与HDMI工作正常，DVI无法输出</li>
</ul>
</li>
<li><strong>独立显卡</strong> 完全支持  报错请刷VBIOS
<ul dir="auto">
<li>可以使用 <code><strong>AGPMInjector.kext</strong></code> 来获得更好的电源管理支持</li>
</ul>
</li>
<ul dir="auto">
</ul>
</li>
<li><strong>博通蓝牙</strong> 完全支持 如果是94360CS2、CD等免驱卡请自行删除<code>BlueToolFixup.kext</code><code>BrcmPatchRAM3.kext</code><code>BrcmFirmwareData.kext</code>
<ul dir="auto"> 
</ul>
</li>
<li>支持原生<strong>CPU电源管理</strong>等其他功能,已经使用<code>MacPro7,1</code>来获得<code>H264</code>以及<code>HEVC</code>硬解支持</li>
</ul>
<ul dir="auto"> 
</ul>
</li>
<li><strong>USB3.0可能无法跑满</strong><code>150M/s</code>的速度，实测只有<code>42M/s</code>左右
<ul dir="auto">
  <li>定制USB端口似乎并无法解决这个问题</li></br>
  <li>测试11.x-13.x 均未能达到Windows中的<code>130M/s</code>(PS:3.0固态U盘)</li>
</ul>
</li>

# BIOS设置
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

# 使用方法
<ul dir="auto">
<li>准备安装U盘：参考OC官方配置，十分好用：<a href="https://dortania.github.io/OpenCore-Install-Guide/installer-guide/mac-install.html#setting-up-opencore-s-efi-environment" rel="nofollow">USB Creation</a>，包含macOS、Windows、Linux的U盘制作。</li>
<li>(重要)使用OCAT打开我提供的EFI的config.plist 重新生成SystemSerialNumber/SystemUUID/MLB</li>
<li>将当前提供的EFI放入U盘EFI磁盘目录下，表示使用当前EFI进行引导</li>
<li>开机配置主板各项配置，以及设置U盘UEFI启动顺序第一</li>
<li>插入U盘，选择U盘UEFI启动，进行安装系统</li>
<li>安装完成进入系统，成功!</li>
</ul>

# 双系统时间错误
<li>这是一个很常见的macOS + Windows的冲突，因为计时方式不同。</li></br>
<li>解决方式也很简单，在Windows下管理员cmd执行</li></br>
<div class="snippet-clipboard-content notranslate position-relative overflow-auto" data-snippet-clipboard-copy-content="Reg add HKLM\SYSTEM\CurrentControlSet\Control\TimeZoneInformation /v RealTimeIsUniversal /t REG_DWORD /d 1"><pre class="notranslate"><code>Reg add HKLM\SYSTEM\CurrentControlSet\Control\TimeZoneInformation /v RealTimeIsUniversal /t REG_DWORD /d 1</code></pre></div>

# 设置默认启动项
<ul dir="auto">
<li>
<p dir="auto"><code>config.plist</code>勾上仿冒苹果快捷键<code>PollAppleHotKey</code>，在启动选择界面，先选中要启动的项，然后按键盘的 <code>Ctrl</code> + <code>Enter</code> 进入系统即可</p>
</li>
<li>
<p dir="auto">也有看到说在 <code>设置</code>-<code>启动磁盘</code> 可选择默认启动项,修改后重启</p>
</li>
</ul>

# 鸣谢
<ul dir="auto">
  <li>感谢<a href='https://space.bilibili.com/244390800'>@乌龙蜜桃来一打</a>提供的显示器断电思路</li>
<li>最好的入门教程：<a href="https://dortania.github.io/OpenCore-Install-Guide/" rel="nofollow">OpenCore Install Guide</a></li>
<li>中文教程：<a href="https://blog.xjn819.com/post/opencore-guide.html" rel="nofollow">Xjn的博客</a></li>
<li>中文文档 &amp; kexts集合下载：<a href="https://oc.skk.moe/" rel="nofollow">OpenCore中文文档</a></li>
<li>镜像下载 &amp; 中文教程：<a href="http://blog.daliansky.net" rel="nofollow">黑果小兵</a></li>
</ul>
