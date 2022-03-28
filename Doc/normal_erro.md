
1. 内核版本号错误
如果kernel的源码使用git做代码管理，即使在config文件中没有指定CONFIG_LOCALVERSION
⇒ cat .config | grep LOCA   
CONFIG_LOCALVERSION=""
但是在产生的uImage中，其magic数据还是会被添加"+"字符
![未删除git时的内核信息](../images/2022/kernel_error_git.png)
删除git后，生成的内核信息不再包括此错误信息
![删除git目录后的内核信息](../images/2022/kernel_error_delete_git.png)