# APK FolderMount
破解 FolderMount.apk 方法

===================
应用名称：FolderMount.apk

应用包名：com.devasque.fmount

备注：此应用需通过 应用内购 升级Pro版

破解方法：

① 首先，反编译 FolderMount.apk，然后反编译 classes.dex。

② 找到 com/devasque/fmount/FolderpairActivity.smali 文件并打开，定位到如下代码：

.method static constructor <clinit>()V
    .registers 2

    .prologue
    const/4 v0, 0x0     //将 0x0 修改为 0x1

    .line 69
    sput-boolean v0, Lcom/devasque/fmount/FolderpairActivity;->b:Z

按照上述说明修改即可，修改后保存。

③ 找到 com/devasque/fmount/custom/d.smali 文件并打开，定位到如下代码：

.line 90
    sget-boolean v0, Lcom/devasque/fmount/FolderpairActivity;->c:Z

    if-eqz v0, :cond_13     (//将 :cond_13 修改为 :cond_5e) 具体你想修改为什么就是什么，随意。这里只是示例。

    .line 91     //从此处开始选择 (//将 .line 91 修改为 :cond_5e)
    iget-object v0, p0, Lcom/devasque/fmount/custom/d;->f:Landroid/content/Context;

    const v1, 0x7f060029

    invoke-static {v0, v1, v4}, Landroid/widget/Toast;->makeText(Landroid/content/Context;II)Landroid/widget/Toast;

    move-result-object v0

    invoke-virtual {v0}, Landroid/widget/Toast;->show()V

    .line 113
    :goto_12     (//将 :goto_12 修改为 :goto_6a，将依次前移的其他代码中跳转到 goto_12 的都修改为 goto_6a)
    return-void     //选择到此处结束→复制，然后向下滚动屏幕找到 

.end method 

在其之前粘贴上述复制代码，粘贴完成后将原位置的上述代码删除，其后的其他代码依次前移。

【重要备注】 
上述代码中 (//........) 为复制粘贴代码后再按照括号中说明修改。
按照上述说明修改即可，修改后保存

④ 找到 com/devasque/fmount/a/p.smali 文件并打开，定位到如下代码：

.line 578
    :cond_12
    sget-boolean v0, Lcom/devasque/fmount/FolderpairActivity;->c:Z

    if-nez v0, :cond_27     //将 if-nez v0 修改为 if-eqz v0

    .line 579
    iget-object v1, p0, Lcom/devasque/fmount/a/p;->a:Lcom/devasque/fmount/a/i;

按照上述说明修改即可，修改后保存。

最后就是编译，然后就可以安装 FolderMount Pro.apk 啦。

好了，FolderMount.apk 破解到此完成！

========================

【特别声明】

→ 不保证上述破解方法永久有效！
如果此应用开发者重新修改代码，那上述破解方法就失效！这你必须要清楚明白！

→ 开发者敲字母编写程序代码也不容易，如果你条件(不管是经济还是网络条件)允许，还是请支付美元购买原版！以支持开发者的开发工作。

→ 我破解是因为我没有上述那个条件。穷逼的破解者一个。
如果你愿意，请捐赠以支持我的破解工作。
