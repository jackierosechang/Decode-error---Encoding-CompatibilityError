# Decode-error---Encoding-CompatibilityError
A CompatibilityError like "incompatible character encodings: GBK and UTF-8 " may occur when you use sublime to decode a sass/scss file.Now let`s  find out the reason
<pre>
Encoding::CompatibilityError
使用sublime在编译scss文件时出现如下错误信息：

 Encoding::CompatibilityError: incompatible character encodings: GBK and UTF-8
  Use --trace for backtrace.
[Finished in 0.9s with exit code 1]

一、	按照提示，打开sass-build的配置文件（用open resource）

二、	添加”--trace”用以显示错误跟踪信息

三、再次运行编译跟踪的错误信息如下：

 E:/Program Files/Koala/ruby/lib/ruby/gems/2.0.0/gems/sass-3.4.21/lib/sass/util.rb:1184:in `absolute_path': incompatible character encodings: GBK and UTF-8 (Encoding::CompatibilityError)
 
四、由于是absolute_path出现错误，故把相同文件复制到D盘，再次编译,则正常。

 write D:/index.css
      write D:/index.css.map
[Finished in 1.0s]

五，综上错误原因是绝对路径中有中文和英文造成utf-8与gbk不匹配。原来index.scss位于"C:\Documents and Settings\Administrator\桌面\index.scss"有中文所以显示错误
 </pre>
