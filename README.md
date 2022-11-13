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
</ul>
</li>
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
<li>可以使用 <code>AGPMInjector</code> 来获得更好的电源管理支持</li>
</ul>
</li>
<ul dir="auto">
</ul>
</li>
<li><strong>博通蓝牙</strong> 完全支持 请自行添加<code>BlueToolFixup.kext</code>
<ul dir="auto"> 
</ul>
</li>
<li>支持原生<strong>CPU电源管理</strong>等其他功能,已经使用<code>MacPro7,1</code>来获得<code>H264</code>以及<code>HEVC</code>硬解支持</li>
</ul>
