## .gitignore 规则不生效 
有时候在项目开发过程中，突然心血来潮想把某些目录或文件加入忽略规则，按照上述方法定义后发现并未生效！
原因是： **.gitignore 只能忽略那些原来没有被track的文件，如果某些文件已经被纳入了版本管理中，则修改.gitignore是无效的**。([source link](https://www.cnblogs.com/songjilong/p/12627355.html))