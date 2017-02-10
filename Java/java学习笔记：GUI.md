一：我们使用到的java GUI的API可以分为3种类：  
- 组件类(component class)
- 容器类(container class)
- 辅助类(helper class)

1：组件类：组件类是用户用来创建界面的，Component类的实例可以显示在屏幕上，Component类是包含容器类的所有用户界面的根类，JComponent是轻量级组件类的根类。  
2：容器类：

|容器类    |说明    |
|----------|--------|
|java.awt.Container|对于组件分组，Frame(框架),Panel(面板)都是它的子类|
javax.swing.JFrame|一个不能包含在另一个窗口的窗口，用于存放其他的组件|
|java.swing.JPanel|可做画图的画布|
|java.swing.JApplet|Applet的一个子类|
|java.swing.JDialog|一个弹出式窗口或者消息框|  

3：辅助类：

|辅助类    |说明    |
|----------|--------|
|java.awt.Graphics|绘制字符串，线，和简单图形|  
|java.awt.Color|处理颜色，为JFrame指定背景色|
|java.awt.Font|指定文字的字体，风格|
|java.awt.FontMetrics|获取字体属性|
|java.awt.LayoutManger|布局管理器|  
二：框架，创建一个用户界面需要创建一个框架来呈放用户界面的组件。一般我们用JFrame，有了框架之后我们就可以向框架中加入组件等东西。  
三：布局管理器  
就是管理我们怎样在一个框架上布局东西的，实际上我们先将东西按照一定规则放置在布局管理器上，然后布局管理器再将东西放到框架之上，然后就呈现出来了我们想要的格式。  
1：FlowLayout:默认按照从左往右的顺序排列组件，如果一行放不下，放到下一行。有三种对齐方式可供选择。

|UML      |作用      |
|---------|----------|
|-aligment:int|对齐方式 LEFT=0,CENTER=1,RIGHT=2,LEADING=3|
|-hgap:int|布局管理器的水平间隔|
|-vgap:int|布局管理器的垂直间隔|
|+FlowLayout()|默认的构造方法|
|+FlowLayout(aligment:int)|设置默认对齐方式|
|+FlowLayout(aligment:int,hgap:int,vgap:int)|设置对齐方式，水平间隔和垂直间隔|
2：GridLayout：网格布局管理器，可以指定每行每列放几个元素，但是行的优先级比列高。

|UML      |作用      |
|---------|----------|
|-rows:int|布局管理器中的行数`比列优先`|
|-columns:int|布局管理器的列数|
|-hgap:int|布局管理器的水平间隔|
|-vgap:int|布局管理器的垂直间隔|
|+GridLayout()|默认的构造方法|
|+GridLayout(rows:int,columns:int)|设置指定行数的列数的GridLayout|
|+GridLayout(rows:int,columns:int,hgap:int,vgap:int)|设置行数，列数，水平间隔和垂直间隔| 
3：BorderLayout：将容器分为5个部分：东，南，西，北，中，可以用`BorderLayout.EAST` ,` BorderLayout.SOUTH`,`BorderLayout.WEST`,`BorderLayout.NORTH`,`BorderLayout.CENTER`分别设置组件的位置。

|UML      |作用      |
|---------|----------| 
|-hagp:int|水平间隔|
|-vgap:int|垂直间隔|
|+BorderLayout()|创建一个默认的BorderLayout|
|+BorderLayout(hgap:int,vgap:int)|创建指定水平间隔和垂直间隔的管理器| 
4：cardLayout：顾名思义，就像一张张卡片一样去管理我们的每一个Panel，像一副扑克牌，只最上面的才会被看到。一般我们`CardLayout card = new CardLayout`然后再`JPanel cardPanle = new JPanel(card)`这样`cardPanel`就是一个`CardLayout`的类型的了。

|UML      |作用      |
|---------|----------| 
|-hagp:int|水平间隔|
|-vgap:int|垂直间隔|
|+CardLayout()|创建默认的布局管理器|
|+CardLayout(hagp:int,vgap:int)|指定水平和垂直间隔|
|+card.first(cardPanel)|显示cardPanel的第一张卡片|
|+card.last(cardPanel)|显示cardPanel的最后一张卡片|
|+card.pervious(cardPanel)|显示cardPanel的前一张卡片|
|+card.next(cardPanel)|显示cardPanel的后一张卡片|
|+card.show(cardPanel,String name)|显示cardpanel中名称为name的卡片|
四：使用面板  
我们很难使用一种布局管理器实现我们想要的效果，所以我们通常使用面板将我们能看到的区域划分，然后在每一个部分上添加上我们想使用的组件，然后再将面板添加到框架中，所以基本步骤就是这样`创建面板->往面板上添加组件->将面板添加到框架中`。













