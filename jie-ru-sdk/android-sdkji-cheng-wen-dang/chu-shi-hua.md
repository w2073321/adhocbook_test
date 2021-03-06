### SDK初始化 {#init}

1.在工程文件“项目名称.java”文件中创建Appllication 类

```
public class DemoApplication extends Application {
private static final String TAG = "DemoApplication" ;
private static DemoApplication instance;
private RefWatcher refWatcher;
```

2.需要在AndroidManifest.xml 里指定类名：

![](http://doc.appadhoc.com/_images/code/android2.png "SDK初始化")

如果已经创建过Application类，跳过新建步骤，直接在onCreate加入上述代码即可。

3.在调用SDK之前记得引入文件 

```
import com.adhoc.adhocsdk.AdhocTracker;
import com.adhoc.config.AdhocConfig;
```

 4.并在OnCreate\(\)中加入下面代码：

```
AdhocConfig adhocConfig = 
new
 AdhocConfig.Builder()

          //设置App上下文(必要参数)
          .context(this)
          //设置Appkey(必要参数)
          .appKey(key)
          //设置clientId,将替换为clientId
          .clientId("xxxx")
          //添加定向试验条件（自定义用户标签）
          .addCustom("sex", "male")
          //调用后,优化指标只有在wifi网络下才会上报数据(可能会造成官网数据延时显示)
          .reportWifi()
          .build();
          
AdhocTracker.init(adhocConfig);
```

| 参数名称 | 参数值 | 说明 |
| :--- | :--- | :--- |
| appkey | ADHOC\_a54d08f9-fb86-455d-9b3e-0343033dfa67 | 创建应用后得到的授权标识 |
| clientId | test | 识别当前版本的方法 |
| addCustom | sex,male | 自定义受众条件\(请保持与平台上填写条件一致\) |
| reportWifi |  | 优化指标只有在wifi网络下才会上报数据 |

其中，“appKey” 是在登录 AppAdhoc 后,创建“应用”之后获得的授权标识。

注意：试验“应用”此时应该提前创建完毕。可在AppAdhoc控制台应用列表找到，如下图红线部分：

![](http://doc.appadhoc.com/_images/app/appkey.png "your\_app\_key")

请勿在SDK基础上进行自行封装，以免影响到试验逻辑，造成试验无法正常运行。如果确有自行封装的需求，请与客户经理联系，获取注意事项。



