## 服务器如何安装puppeteer（墙外）

+ 安装node

+ 利用npm安装puppeteer(去除chromium安装，手动安装) 
  `npm install puppeteer --ignore-scripts`
  
+ `vim path/to/puppeteer/node_modules/puppeteer/utils/ChromiumDownloader.js` 找到方法downloadFile并打印url 得到下载chromium的地址 然后手动去下载 将下载的文件存放至自定义的web服务器中 更改之前那个url的地址 指向自定义服务器中文件地址 退回并执行安装chromium  `cd path/to/puppeteer/node_modules/puppeteer && ndoe install.js`

+ ps:实验版本node 7.10.1 文件夹中提供的chrome版本是Linux_x64/515411/chrome-linux.zip

+ pps:ChromiumDownloader.js中利用https模块下载，如果自定义web服务器是http的，则需要引入http模块去下载


