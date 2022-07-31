# Linux
#runoob
[https://elixir.bootlin.com/linux/latest/source](https://elixir.bootlin.com/linux/latest/source)
[Goorm - Login](https://accounts.goorm.io/login?return_url=aHR0cHM6Ly9pZGUuZ29vcm0uaW8vbXkvZGFzaGJvYXJk&keep_login=false)

# 教程

教程

简介

安装

云服务器

系统启动过程

系统目录结构

忘记密码解决方法

远程登录

文件基本属性

文件与目录管理

用户和用户组管理

磁盘管理

vi/vim

yum 命令

apt 命令
# 其他

- 打开终端
    
    ctrl alt T
    
- 提示符
    
    用户名
    主机名
    当前位置
    ~家目录
    /根目录
    
    $普通用户
    /#管理员
    
- 命令格式
    
    命令 选项 参数
    
- 帮助信息
    
    命令 --help
    
- 自动补全
- 历史命令
- 重定向
    
    命令 > 文件名
    
    将命令输出结果写入文件
    
    >
    
    先清空再写入
    
    >>
    
    追加内容
    
- 管道
    
    命令1 | 命令2
    键命令1的结果给命令2
    
- 文件
    
    文件类型
    bcd-lsp
    
    文件权限
    rwx rwx r-x
    用户主 用户组 其他用户
    
- 清屏
    
    clear
    
- 改变路径
    
    cd
    
    cd -
    
    pwd
    当前绝对路径
    
- 显示文本内容
    
    cat 文件名
    
- 删除
    
    rm -rf
    
    mv

# Linux学习

- 基础操作
    
    用户操作
    切换用户：su - root
    -表示环境变量一起切换
    查看用户
    查看所有用户的列表：cat /etc/passwd
    查看用户组：cat /etc/group
    查看当前活跃的用户列表：w
    关机：shutdown -h now
    重启：reboot
    
    常用操作
    常用快捷键
    tab键：自动补全
    停止当前进程：ctrl + c
    挂起当前进程，后台执行：ctrl + z
    查看历史命令：ctrl + r
    查看执行过的命令：上下方向箭头
    清屏：ctrl + l
    目录操作
    路径更改：cd(change directory)
    目录路径
    /：切换到根目录
    .：当前目录
    ..：回到上一级目录
    -：显示并打开到上一次操作目录
    ~：当前用户的宿主目录(root->/root  user->/home/user)
    文件操作
    文件操作
    ls：list显示所有文件
    ll：相当于ls -l
    -a：all显示所有文件
    -l：long显示详细信息
    -R：recursive递归显示当前目录下所有目录
    -r：reverse逆序排序
    -t：time按修改时间排序(降序)
    -h：易读
    pwd：print working directory显示当前工作目录
    mkdir：make directories创建新目录
    touch：创建空文件或更新已存在文件的时间
    cp：copy复制文件或目录
    语法：cp [-rp] 源文件或目录 目的目录
    复制文件内容：cp -r 目录/* 目的目录
    -r -R：recursive递归处理，复制目录
    -p：保留文件属性
    mv：move移动文件或目录、文件或目录改名
    rm：remove删除文件或删除目录
    语法：rm [-rf] 目录或文件
    删除文件内容：rm -r 目录/*
    -r：recursive删除目录，同时删除该目录下的所有文件
    -f：force强制删除文件或目录，不用提示
    
- 语法
    
    注释
    
    @Override
    
    提示方法是覆盖的
    
    编译器检测是否覆盖
    
    public static XXX getInstance()
    
    获取到单例对象
    
- 面向对象
    
    封装
    类（数据+方法）
    包
    import
    导入类
    import static
    导入类的静态函数
    隐藏
    权限 （数据、函数、类的隐藏）
    无修饰符不等价于 public/private/protected
    权限大小：public>protected>default>private
    应用的对象
    成员变量
    成员函数
    类
    default
    public
    类名与文件名保持一致
    划分的范围
    类自身
    子类
    包
    原则
    高内聚
    尽量不暴露模块内部的变量/方法/类给外部，并且只有模块内部相互引用
    低耦合
    模块之间的调用尽量简单
    继承
    关键字
    extends
    implements
    super
    父构造
    父方法
    final
    类
    方法
    instanceof
    判断以对象的实际类型
    只能继承单个类(extends)
    可继承多个接口(implements)
    无带public/private/protected的继承
    匿名类
    继承与接口或抽象类
    实现接口函数/抽象函数
    无类名
    可以使用普通类代替
    多态
    重载
    重写（覆盖）
    无virtual关键字
    抽象
    接口(interface)
    不须实现方法
    方法的访问权限不能使用 private/protected
    变量隐式定义为static final
    抽象类
    定义
    abstract修饰类
    有抽象函数
    无法实例化抽象类对象
    
- 技巧skill
    
    JavaBean
    具有get/set函数的Java类
    数据结构
    数组
    String[ ] sarray = new String[size]
    动态数组
    ArrayList
    语法
    for(User u: allUsers)
    字符串处理
    转换
    字符串->int
    Integer.ParseInt()
    int->字符串
    String.valueOf
    切分
    str.split()
    比较
    str.equals()
    解析字符
    str.charAt
    属性
    长度
    字符集
    编码
    Ascii
    unicode
    UTF8
    判断中文
    
    > 0x80(近似)
    文件操作
    读
    类
    BufferedReader
    readLine()
    FileReader
    File
    写
    类
    BufferedWriter
    write
    FileWriter
    File
    换行符
    \r\n
    异常处理
    try catch finally
    异常类
    IOException
    finally
    reader/write.close()
    系统资源的回收
    启动Java程序
    IDE
    Run
    Run File
    命令行
    classes目录
    Java com.abc.Main
    jar包
    -jar选项
    配置主类
    MAINFEST.MF
    Java -jar abc.jar
    -cp
    Java -cp abc.jar com.abc.Main
    日志
    Logger.getLogger(xxx.class.getName()).log
    日志的级别
    > 
- 异常
    
    定义
    中断程序执行
    异常类
    IOException
    NullPointerException
    ArithmeticException
    异常发生的位置
    文件+行号
    函数调用的历史信息（异常发生的调用栈）
    异常所在的线程
    关键字
    throws
    声明函数
    调用者必需捕获异常或声明抛出此类异常
    main函数也可以声明抛出异常
    finally
    无论try代码块中有无异常抛出，都必执行
    
- 设计模式
    
    单例模式
    
    构造函数为private
    
    限制在类外创建对象
    
    监听器模式
    
    类
    
    EventSource
    
    Event
    
    Listener

[Shell](笔记本/已归档/runboo/Shell.md)