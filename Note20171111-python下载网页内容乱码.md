# python 下载网页内容出现乱码

平时使用`urllib2`下载一个页面的内容，然后使用`beautifulsoup`解析后出现乱码，不管是换成`utf8`或者`gbk`编码来解码都不行。

这个问题可能是网页被压缩的原因。

用浏览器调试工具查看下`url`应答包`header`中是否有`Content-Encoding`为`gzip`。

python可以使用`gzip`库来解压:

``` python
import gzip, StringIO
url = 'http://www.example.com'
response = urllib2.urlopen(url)
html = response.read()
if response.info().get('Content-Encoding') == 'gzip':
    buf = StringIO.StringIO(html)
    fd = gzip.GzipFile(fileobj=buf)
    html = fd.read()
print html
```
