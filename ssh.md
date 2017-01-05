###ssh提交
1.git生成公钥和私钥： ssh-keygen -t rsa

> 文件生成的公钥和私钥会在当前用户的.ssh目录下

![](/assets/要.png)

> 打开github（git服务器）->setting->ssh-keygen...->在里面新建公钥，push的时候地址为ssh的提交地址，这样这个项目的push时就不用用户名和密码，同事提交也不需要，只要有他们的公钥