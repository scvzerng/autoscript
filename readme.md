## 使用须知

> 由于是花了十几分钟写的并且不是很熟悉按键精灵的语法规则所以使用要求请严格遵守以下规则

- 包裹必须打开
- 包裹呈现必须为48个未开光的元婴

#### 执行开光48次后脚本就会停止请按F10热键在此开光开光要求为上述要求
> 开关原理介绍:

- 定位到第一个未开光元婴并初始化未标
- 根据初始化坐标自动计算鼠标偏移位置 x:initx+35+3
- x轴移动6次后重置x初始坐标按x偏移方式偏移y轴
- y轴偏移6次结束开光

> code

        Delay 5000
        If intX > 0 And intY > 0 Then
        End If
        FindPic 0, 0, 1920, 1024, "Attachment:\ÔªÓ¤.bmp", 0.9, intX, intY
        initX =0 
        initY =0 
        If intX > 0 and intY > 0 Then 
            initX = intX 
            initY = intY
        End If
        If initX <= 0 and initY <= 0 Then 
            MessageBox "Ã»ÓÐÕÒµ½ÔªÓ¤"
            EndScript
        End If
        initY = initY + 10
        initX = initX + 10
        sourceX = initX
        initCycle = 6
        initMoveStep = 35
        border = 3
        count = 48
        While count <> 0
            MoveTo initX,initY
            RightClick 1
            Delay 300
            FindPic 0, 0, 1920, 1024, "Attachment:\¿ªÊ¼.bmp", 0.9, startX, startY
            If startX = 0 Then 
                MessageBox "ÎÞ·¨ÕÒµ½¿ªÊ¼¼ü"
                EndScript
            End If
            MoveTo startX,startY
            LeftClick 1
            Delay 3100
            initX = initX + initMoveStep+border
            initCycle = initCycle - 1
            If initCycle=0 Then  
                initCycle = 6
                initX = sourceX
                initY=initY+initMoveStep+border
            End If
       
            count=count-1
        Wend


####  遇到鼠标乱飘请按f12结束脚本并是包裹打到上述开光要求

####  至于为什么是48次那是因为48正好是包裹一页不需要滚屏偷个小懒包裹大的可以多兑换点多运行几次脚本开光

##   购买和出售请自行处理

> 怕有毒的仙友自行下载按键精灵打开`自动开光.Q`源文件运行