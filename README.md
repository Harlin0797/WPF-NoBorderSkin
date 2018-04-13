# WPF-NoBorderSkin
WPF无边框皮肤，可打包成dll引用


源码出自[DMSkin-for-WPF 2.0.0.1](https://github.com/944095635/DMSkin-for-WPF)

## 使用说明
```
1.引用DMSkin.WPF.DLL  
2.Window继承修改为:MainWindow : DMSkinWindow  
3.添加引用:xmlns:DMSkin="clr-namespace:DMSkin.WPF;assembly=DMSkin.WPF"  
4.XAML继承修改为: DMSkin:DMSkinWindow x:Class="DMSkin.WPF.Test.MainWindow"  
```

## 窗体属性
<pre>
<code>      
Foreground="White"                    //前景色 
Background="White"                    //背景色 
DMShowMin="True"                      //显示系统按钮-最小化
DMShowMax="True"                      //显示系统按钮-最大化
DMShowClose="True"                    //显示系统按钮-关闭
DMWindowShadowSize="10"               //窗体边框阴影大小
DMWindowShadowColor="#FFC8C8C8"       //窗体边框阴影颜色
DMWindowShadowDragVisibility="False"  //窗体拖动时是否显示阴影层
DMWindowShadowVisibility="False"      //窗体是否有阴影层[关闭阴影层]
DMWindowShadowBackColor="#FF323CAD"   //阴影背景色,选择跟主窗体相近的颜色 拉伸跟拖动 用户体验更好|#FF323CAD 为蓝色
DMSystemButtonSize="50"               //系统按钮大小
DMSystemButtonForeground="#FF666666"  //系统按钮[文字]颜色
DMSystemButtonHoverColor="#33000000"  //系统按钮的鼠标悬浮[背景]色
DMSystemButtonHoverForeground="White" //系统按钮的鼠标悬浮[文字]颜色
DMSystemButtonCloseHoverColor="Red"   //系统【关闭】按钮的鼠标悬浮[背景]色-默认为红色
DMSystemButtonShadowEffect="0"        //系统按钮的阴影大小
ResizeMode="CanResize"                //边框拉伸方案CanResiz和CanResizeWithGrip
Height="700" Width="1000"             //窗体大小
MinHeight="268" MinWidth="360"        //窗体最大以及最小属性
WindowStartupLocation="CenterScreen"  //窗体初始位置
<br/>
<del>DMMetroBorderColor="#FFC8C8C8"  //窗体边框颜色-仅Metro有效   --2.0中移除</del>
<del>DMMetroBorderSize="1"           //边框大小-仅Metro有效   --2.0中移除</del>
<del>DMWindow="Shadow"               //Shadow-阴影模式  Metro-线条扁平化模式   --2.0中移除</del>
</code>
</pre>

## 资源引用
```
<Application.Resources>
    <ResourceDictionary>
        <ResourceDictionary.MergedDictionaries>
            <ResourceDictionary Source="pack://application:,,,/DMSkin.WPF;Component/Themes/DMSkin.xaml" />
            <ResourceDictionary Source="pack://application:,,,/DMSkin.WPF;Component/Themes/DMColor.xaml" />
            <ResourceDictionary Source="pack://application:,,,/DMSkin.WPF;Component/Themes/DMScrollViewer.xaml" />
            <ResourceDictionary Source="pack://application:,,,/DMSkin.Wpf;component/Themes/DMButton.xaml" />
            <ResourceDictionary Source="pack://application:,,,/DMSkin.Wpf;component/Themes/DMTabControl.xaml" />
            <ResourceDictionary Source="pack://application:,,,/DMSkin.Wpf;component/Themes/DMRadioButton.xaml" />
            <ResourceDictionary Source="pack://application:,,,/DMSkin.Wpf;component/Themes/DMTreeView.xaml" />
            <ResourceDictionary Source="pack://application:,,,/DMSkin.Wpf;component/Themes/DMDataGrid.xaml" />
            <ResourceDictionary Source="pack://application:,,,/DMSkin.Wpf;component/Themes/DMListBox.xaml" />
            <ResourceDictionary Source="pack://application:,,,/DMSkin.Wpf;component/Themes/DMSlider.xaml" />
            <ResourceDictionary Source="pack://application:,,,/DMSkin.Wpf;component/Themes/DMCheckBox.xaml" />
            <ResourceDictionary Source="pack://application:,,,/DMSkin.Wpf;component/Themes/DMContextMenu.xaml" />
        </ResourceDictionary.MergedDictionaries>
    </ResourceDictionary>
</Application.Resources>
```

## 通用模板
<pre>
<code>
&lt;Grid&gt;
        &lt;Grid Background="White"&gt;
            &lt;Border Grid.Column="0" BorderThickness="0,0,0,2" BorderBrush="{StaticResource LineColor}" VerticalAlignment="Top"&gt;
                &lt;Grid&gt;
                    &lt;TextBlock Foreground="{StaticResource MainColor}" Text="DMSkin"  FontSize="20"
                           HorizontalAlignment="Left" VerticalAlignment="Center" Margin="10,0,0,0"/&gt;
                    &lt;Button  Name="ButtonSkin"
                                ToolTip="主题"
                                Focusable="False"
                                Style="{DynamicResource CaptionButtonStyle}"
                                Padding="0" HorizontalContentAlignment="Center" HorizontalAlignment="Right" Margin="0,0,150,0" Width="50" Height="50" 
                                &gt;
                        &lt;Label Foreground="#FF555555" 
                                       Content="X" FontSize="22" 
                                       HorizontalContentAlignment="Center" FontWeight="Bold"  &gt;&lt;/Label&gt;
                    &lt;/Button&gt;
                &lt;/Grid&gt;
            &lt;/Border&gt;
        &lt;/Grid&gt;
        &lt;ResizeGrip  HorizontalContentAlignment="Stretch" VerticalContentAlignment="Stretch" VerticalAlignment="Bottom" HorizontalAlignment="Right"&gt;&lt;/ResizeGrip&gt;
&lt;/Grid&gt;
</code>
</pre>

## 圆角窗体
<pre>
<code>
&lt;Border Background="White" CornerRadius="5"  BorderThickness="1"&gt;
        &lt;Border.Effect&gt;
            &lt;DropShadowEffect BlurRadius="12" ShadowDepth="0" Color="#88000000"/&gt;
        &lt;/Border.Effect&gt;
        &lt;Grid Margin="0,0,0,0"&gt;
            &lt;Grid Background="Transparent"&gt;
                &lt;Grid.RowDefinitions&gt;
                    &lt;RowDefinition Height="30"&gt;&lt;/RowDefinition&gt;
                    &lt;RowDefinition Height="*"&gt;&lt;/RowDefinition&gt;
                    &lt;RowDefinition Height="30"&gt;&lt;/RowDefinition&gt;
                &lt;/Grid.RowDefinitions&gt;
                &lt;Grid Grid.Row="0" Name="DMTitle"&gt;
                &lt;/Grid&gt;
            &lt;/Grid&gt;
            &lt;ResizeGrip VerticalContentAlignment="Bottom" HorizontalContentAlignment="Right" HorizontalAlignment="Right" VerticalAlignment="Bottom"&gt;&lt;/ResizeGrip&gt;
        &lt;/Grid&gt;
&lt;/Border&gt;
</code>
</pre>