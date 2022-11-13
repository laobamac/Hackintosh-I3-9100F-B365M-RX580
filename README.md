# I3-9100F-B365M-RX580
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
<td>Intel(R) Core I3-9100F 4C4T Processor</td>
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
<td>集成显卡</td>
<td>无</td>
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
<td>瑞昱 ALC662 (layout-id：16)</td>
</tr>
<tr>
<td>无线网卡</td>
<td>BCM943224PCIEBT2（EFI内不带驱动！）</td>
</tr>
</tbody>
</table>

# 目前情况
<ul dir="auto">
<li><strong>休眠</strong> 完全支持 同时实现<strong>电源小憩</strong></li>
</ul>
</li>
<li><strong>HDMI</strong> 完全支持
<ul dir="auto">
<li>最低分辨率1366*768，不支持1680*1050，否则可能会损坏你的显示器。3*DP与HDMI工作正常，DVI无法输出</li>
</ul>
</li>
<li><strong>独立显卡</strong> 完全支持  报错请刷VBIOS
<ul dir="auto">
<li>可以使用 <code>ADPMInjector</code> 来获得更好的电源管理支持</li>
</ul>
</li>
<ul dir="auto">
<li><strong>博通蓝牙</strong> 完全支持 请自行添加<code>BlueToolFixup.kext</code>
<ul dir="auto"> 
<ul dir="auto">
<ul dir="auto">
<ul dir="auto">
<ul dir="auto">
<ul dir="auto">
<ul dir="auto">
<li>在 macOS12 上，英特尔蓝牙支持更多蓝牙4.x设备</li>
<li>阅读 <a href="https://github.com/daliansky/XiaoMi-Pro-Hackintosh/wiki/%E8%93%9D%E7%89%99%E8%A7%A3%E5%86%B3%E6%96%B9%E6%A1%88">蓝牙解决方案</a></li>
<li>你也可以尝试 <a href="https://github.com/AppleBluetooth">AppleBluetooth</a> 发布的 <a href="https://github.com/AppleBluetooth/IOBluetoothFixup">IOBluetoothFixup</a>，<a href="https://github.com/AppleBluetooth/IntelBluetoothFamily">IntelBluetoothFamily</a> 和 <a href="https://github.com/AppleBluetooth/OpenFirmwareManager">OpenFirmwareManager</a>，请阅读 <a href="https://github.com/AppleBluetooth/IntelBluetoothFamily#usage">IntelBluetoothFamily Usage</a></li>
</ul>
</li>
<li><strong>英特尔无线网卡</strong> 性能不佳
<ul dir="auto">
<li>推荐使用 macOS Big Sur 或更高版本；macOS 版本低于11的话需要重建缓存重启如果英特尔无线网卡不工作</li>
<li>购买 USB网卡 或者支持的内置网卡</li>
<li>阅读 <a href="https://openintelwireless.github.io/itlwm/FAQ.html" rel="nofollow">Frequently Asked Questions</a> 来获取详细信息</li>
</ul>
</li>
<li><strong>瑞昱USB SD读卡器</strong> 需要额外操作来工作
<ul dir="auto">
<li>阅读 <a href="https://github.com/0xFireWolf/RealtekCardReader/blob/main/Docs/FAQ.md">FAQ</a> 来获取详细信息并添加 <a href="https://github.com/0xFireWolf/RealtekCardReader">RealtekCardReader</a> + <a href="https://github.com/0xFireWolf/RealtekCardReaderFriend">RealtekCardReaderFriend</a></li>
<li>你也可以转成使用 VMware 来让它工作，见 <a href="https://github.com/ManuGithubSteam/XiaoMi-Pro-2018-HackintoshOC/wiki/2.0-Setup-SD-Card-Reader">2.0 Setup SD Card Reader</a></li>
</ul>
</li>
<li>其他都工作正常</li>
</ul>
