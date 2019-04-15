---
layout:     post
author:     Estuary
header-img: img/post-bg-hacker.jpg
catalog: true
tags:
    - Binary-Files
---

<h1><strong>Introduction</strong></h1>
You can have a quick trying with all binaries, which can be downloaded from following link:
<pre class="disqus"><code>http<span class="variable">s:</span>//github.<span class="keyword">com</span>/open-estuary/estuary/releases
</code></pre>
<p class="disqus">Here, you can click the ‘Latest release’ on left of page firstly, then download any files in the version as you like.</p>

<pre>e.g.: wget -c https://github.com/open-estuary/estuary/releases/download/bin-v1.2/Image
</pre>
<p class="disqus">All binaries and their descriptions are listed as follows, how to use these binaries, please refer to the respective hacking manuals under Documents Section.</p>

<pre class="disqus"><code><span class="code">+----------------------------+</span>------------------------------------+       
|  <strong>FILE NAME</strong>                 |    <strong>DESCRIPTION</strong>                     |
<span class="code">+----------------------------+</span>------------------------------------+    
<span class="header">|  UEFI_D01.fd               |    UEFI binary for D01 board       |
|  UEFI_D02.fd               |    UEFI binary for D02 board       |
+----------------------------+------------------------------------+</span>
<span class="header">|  CH02_TEVBC_V03.bin        |    CPLD binary, power controll     |
+----------------------------+------------------------------------+</span>
|  bl1.bin                   |    Trust Fireware binaries         |
|  fip.bin                   |                                    |
<span class="code">+----------------------------+</span>------------------------------------+
|  grubarm32.efi             |    grub binary for arm32           |                  
|  grubaa64.efi              |    grub binary for arm64           |
<span class="code">+----------------------------+</span>------------------------------------+       
|  grub.cfg                  |    grub configure                  |        
<span class="code">+----------------------------+</span>------------------------------------+       
<span class="header">|  Image_D01                 |    kernel image for D01 platform   |
|  Image_D02                 |    kernel image for D02 platform   |
|  Image_QEMU                |    kernel image for QEMU platform  |
+----------------------------+------------------------------------+
|  hip04-d01.dtb             |    dtb file for D01 platform       |</span>
|  hip05-d02.dtb             |    dtb file for D02 platform       |
<span class="code">+----------------------------+</span>------------------------------------+              
<span class="header">|  mini-rootfs.cpio.gz       |    initramfs stored in NORFLASH    |   
+----------------------------+------------------------------------+</span></code></pre>
<h1 class="inline-comment"><strong>Main Components</strong></h1>
<h2><span id="UEFI">UEFI</span>:</h2>
Responsible for loading and booting Image and dtb file,and you could download binary file from
<div class="inline-comment">
<pre>wget -c https://github.com/open-estuary/estuary/releases/download/bin-v1.2/UEFI_D01.fd
wget -c https://github.com/open-estuary/estuary/releases/download/bin-v1.2/UEFI_D02.fd</pre>
<h2><span id="UEFI">GRUB</span>:</h2>
grub configure file and grub image file for D02,and you could download binary file from:

</div>
<pre class="disqus"><code>wget -c <span class="symbol">https:</span>/<span class="regexp">/github.com/open-estuary</span><span class="regexp">/estuary/releases</span><span class="regexp">/download/bin</span>-v1.<span class="number">2</span>/grub.cfg
wget -c <span class="symbol">https:</span>/<span class="regexp">/github.com/open-estuary</span><span class="regexp">/estuary/releases</span><span class="regexp">/download/bin</span>-v1.<span class="number">2</span>/grubarm32.efi
wget -c <span class="symbol">https:</span>/<span class="regexp">/github.com/open-estuary</span><span class="regexp">/estuary/releases</span><span class="regexp">/download/bin</span>-v1.<span class="number">2</span>/grubaa64.efi </code></pre>
<h2>Kernel:</h2>
The operation system that D02 runs on,and you could binary files from following website:
<pre class="disqus"><code>wget -c <span class="symbol">https:</span>/<span class="regexp">/github.com/open-estuary</span><span class="regexp">/estuary/releases</span><span class="regexp">/download/bin</span>-v1.<span class="number">2</span>/<span class="constant">Image</span>
wget -c <span class="symbol">https:</span>/<span class="regexp">/github.com/open-estuary</span><span class="regexp">/estuary/releases</span><span class="regexp">/download/bin</span>-v1.<span class="number">2</span>/hip05-d02.dtb</code></pre>
<h2>Linux Distribution Files:</h2>
Because the distribution’s Images are too large, all of them are storaged into another place. The validated distributions for this project’s boards can be downloaded from following website, the <span style="color: #ff0000;"><strong>default user name and passowrd </strong></span>of distributions are: <span style="color: #ff0000;"><strong>root, root</strong></span>.
<pre class="disqus"><code><span class="attribute">Ubuntu</span>: <span class="string">    wget -c http://7xjz0v.com1.z0.glb.clouddn.com/dist/Ubuntu_ARM64.tar.gz</span>
<span class="attribute">OpenSUSE</span>: <span class="string">  wget -c http://7xjz0v.com1.z0.glb.clouddn.com/dist/OpenSuse_ARM64.tar.gz</span>
<span class="attribute">Fedora</span>: <span class="string">    wget -c http://7xjz0v.com1.z0.glb.clouddn.com/dist/Fedora_ARM64.tar.gz</span>
<span class="attribute">Redhat</span>: <span class="string">    TBD</span>
<span class="attribute">Debian</span>:     <span class="string">wget -c http://7xjz0v.com1.z0.glb.clouddn.com/dist/Debian_ARM64.tar.gz
</span><span class="attribute">OpenEmbedded</span>: <span class="string"> TBD</span></code></pre>
All these validated distributions can be uncompressed to any target position directly with following example commands.
<pre class="disqus"><code>mkdir -p ~/rootfs
sudo tar -xzf xxxxx_ARM64.tar.gz -C ~/rootfs/</code></pre>
All original distributions without validation for this project’s boards can be downloaded from follows:
<pre class="disqus"><code><span class="attribute">Ubuntu</span>: <span class="string">    wget -c https://cloud-images.ubuntu.com/vivid/current/vivid-server-cloudimg-arm64.tar.gz</span>
<span class="attribute">OpenSUSE</span>: <span class="string">  wget -c http://download.opensuse.org/ports/aarch64/distribution/13.2/appliances/openSUSE-13.2-ARM-JeOS.aarch64-rootfs.aarch64-Current.tbz</span>
<span class="attribute">Fedora</span>: <span class="string">    wget -c http://dmarlin.fedorapeople.org/fedora-arm/aarch64/F21-20140407-foundation-v8.tar.xz</span>
<span class="attribute">Redhat</span>: <span class="string">    TBD</span>
<span class="attribute">Debian</span>: <span class="string">    wget -c http://people.debian.org/~wookey/bootstrap/rootfs/debian-unstable-arm64.tar.gz</span>
<span class="attribute">OpenEmbedded</span>: <span class="string">wget -c http://releases.linaro.org/14.06/openembedded/aarch64/vexpress64-openembedded_minimal-armv8-gcc-4.8_20140623-668.img.gz</span></code></pre>
<h2>Toolchain:</h2>
Used to compile and debug some above files, and now you could download it from following website:
<pre class="disqus"><code>wget -<span class="built_in">c</span> http:<span class="comment">//releases.linaro.org/14.09/components/toolchain/binaries/gcc-linaro-aarch64-linux-gnu-4.9-2014.09_linux.tar.bz2</span></code></pre>
Quicker download link are:
<pre class="disqus"><code>ARM32: wget -c http://7xjz0v.com1.z0.glb.clouddn.com/tools/gcc-linaro-arm-linux-gnueabihf-4.9-2014.09_linux.tar.xz
ARM64: wget -c http://7xjz0v.com1.z0.glb.clouddn.com/tools/gcc-linaro-aarch64-linux-gnu-4.9-2014.09_linux.tar.xz</code></pre>
<div class="inline-comment"><span style="color: #ff0000;"><strong>Note: By default, all distributions and tool chains are compressed, you should decompress them firstly before using them.</strong></span></div>
<div class="inline-comment">

<hr />

<strong>More material about how to use these binaries, please refer to <a href="http://open-estuary.com/estuary-user-manual/">Estuary User Manual</a>.</strong>

</div>
