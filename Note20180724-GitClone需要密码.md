git clone 时突然需要输入密码 

已添加ssh key，但在clone的时候要求输入远端的密码？什么？这我怎么知道？

原来是需要将刚生成的私钥添加到ssh中：ssh-add ~/.ssh/id_rsa_xxx


