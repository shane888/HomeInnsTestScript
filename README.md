# HomeInnsTestScript
Behave+Appium test script for HomeInns Android and iOS app

# Environment setup
## Appium 
Please refer to appium.io for appium setup
 https://github.com/appium/python-client

Android sdk 2.3+ is needed
Xcode is needed

appium 中实用的代码都在client里面
common 属于Appium/python-client中的一部分
（1）element
    查找并定位界面的控件，然后定义一些查找控件方法或者控件属性的方法
（2）webdriver
    对控件进行定义，并实现这些已经在element中定义好的方法
（3）common_test_step文件中，主要是调用appium中的接口来实现功能方法，还有日志打印功能
    调用了单点触控（TouchAction），多点触控（MultiAction）等接口


## Behave
Please refer to http://pythonhosted.org/behave/ for behave setup
behave是BBD（行为驱动开发）的框架，既可以用来测试网页的功能，也可以用来单元测试
1.feature：属于behave的一部分，文件包括了5行
    feature行：介绍这个feature用来干什么
    Scenario行：介绍这个Scenario用来干什么
    Given行：一般数据的初始化
    When行：执行操作
    Then行：验证结果
2.environment:定义了一些当测试脚本在run的过程中之前和之后完成的任务
    before_step(context, step), after_step(context, step)
    在这里面的脚本会在每一个步骤之前，之后执行
    before_scenario(context, scenario), after_scenario(context, scenario)
    在这里面的脚本会在每一个场景之前，之后执行
    before_feature(context, feature), after_feature(context, feature)
    在这里面的脚本会在每一个feature之前，之后执行
    before_tag(context, tag), after_feature(context, tag)
    在脚本里面可以设置tag(这个之后会介绍)，这里面的脚本会在含有tag的模块里面之前，之后执行
    before_all(context), after_all(context)   
    这里面的脚本会在整个脚本开始之前，之后执行 例如登录或者是退出
