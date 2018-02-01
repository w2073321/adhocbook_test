## **集成调试**

集成调试是指，在试验开始前通过吆喝平台，强制进入试验版本，通过观察试验版本运行是否正常，指标上报是否正常，判断sdk是否集成成功。集成调试数据不计入试验数据。集成调试功能在“调试”页面。

具体各个模式下集成调试如下。

### **Web/H5试验集成调试**

![](/assets/jc1.png)

l  输入参加试验的页面链接（注：可视化、多链接模式不需要），选择“试验版本\_1\_testdemo1”并点击“点击预览”，就会跳转到正在设置中的试验版本，检查版本是否正确显示，同时检查UV，PV是否加1（注：同一个浏览器在进行集成调试时，每次点击预览，UV，PV均加1）

l  同时，当对该页面集成指标的元素进行操作（如点击CTA按钮），相应的指标数据也会发生变化时（如点击指标button\_click加1），说明试验版本已经成功集成。

l  当有多个试验版本时，重复上述操作，确保所有版本都验证正确。

l  若无法进入测试版本（包括原始版本）或无法正常统计试验数据，可能是集成过程中出现了错误，需修正后重新进行检验。错误排查见第3章

### Android集成调试

l  对于Android集成调试，吆喝科技开发了AdhocTester工具。用户可通过AdhocTester扫码强制进入试验环境，验证代码集成是否正确，并提前检测试验版本的效果。相关调试数据将不计入试验结果。（注意，在集成调试之前，请确保试验APP已处于完全退出的状态，即杀死进程）

![](/assets/2.png)

l  进入「调试」页面，可以看到试验版本的二维码。点击下载AdhocTester Android端工具，安装到手机后。

l  安装后，进入AdhocTester。选择「扫描加入试验（Android）」，扫描“试验版本\_1\_test1”页面上的二维码成功后，会自动跳回AdhocTester首页，并显示「已经加入试验」，之后打开您需要试验的app，即可看到试验版本。

![](/assets/3.png)

l  在进入试验版本后，检查UV是否加1（注意：每台独立设备进行集成调试，无论扫码进入多少次试验版本，只算一个UV）

l  进入app的试验版本后，当对集成指标的元素进行操作，相应的指标数据也会发生变化时，说明试验版本已经集成成功。

l  若无法进入试验版本\(包括原始版本\)或无法正常统计试验数据，可能是集成过程中出现了错误，需修正后重新进行检验。错误排查见第3章。

l  当有多个试验版本时，重复上述操作，确保所有版本都验证正确。

l  需要说明的是：扫码后，设备会始终停留在该版本，无论试验是否开始，且不受试验流量调整的影响。如果想退出调试模式请点击“退出试验”。

### iOS集成调试

![](/assets/2.png)

l  对于iOS下的集成调试，SDK在调试模式下可通过扫码强制进入试验环境，验证代码集成是否正确，并提前检测试验版本的效果。相关调试数据将不计入试验结果。（注意，在集成调试之前，请确保试验APP已处于完全退出的状态，即杀死进程）

l  在您进行试验的iOS应用中点击悬浮按钮，扫描“试验版本1\_1\_test1”二维码，之后重新启动您的应用，即可预览该版本，检验版本配置（如果第一次无法进入试验版本，可以再重复一次这个步骤，如果还是不能进入试验版本，请参考错误排查）。关于悬浮按钮的集成请参考[SDK集成文档](http://doc.appadhoc.com/sdk/iosSDK.html#debug)。

l  在进入试验版本后，检查UV是否加1（注意：每台独立设备进行集成调试，无论扫码进入多少次试验版本，只算一个UV）

l  进入app的试验版本后，当对集成指标的元素进行操作，相应的指标数据也会发生变化时，说明试验版本已经集成成功。

l  若无法进入试验版本\(包括原始版本\)或无法正常统计试验数据，可能是集成过程中出现了错误，需修正后重新进行检验。错误排查见第3章。

l  当有多个试验版本时，重复上述操作，确保所有版本都验证正确。

l  需要说明的是：扫码后，设备会始终停留在该版本，无论试验是否开始，且不受试验流量调整的影响。如果想退出调试模式请点击“退出试验”。
