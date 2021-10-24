以Ini主導的UI
==
Dialog與UserControl共同定義

以Section定義Dialog,UserControl,FormData,Event

# Dialog以及UserControl

* Example
  * 定義一個Dialog叫DIALOG_ID
  [Dialog=DIALOG_ID]
  
  * 定義一個UserControl叫做CONTROL_ID
  [UserControl=CONTROL_ID] 

* Dialog以及UserControl共同定義
  
  * Controls.Count
  
    決定這個Dialog/UserControl要載入幾個ChildControl，-1是預設值，代表全部載入
  * Size=100,100    
  
    control/dialog的預設大小
  * BackgroundColor=0,0,0,0
  
    control/dialog的背景色
  * BackgroundImage=檔名
  
    背景圖
    
  * Bound Data
  
    綁定資料欄位，預設填入到Value
    
# FormData
  * Example
    * [FormData=FORM_ID]
    
    定義一個FormData叫做FORM_ID，預設存檔到FormData.FORM_ID.dat
    * [FormData=FORM_ID,FileName=FILE_NAME]
    
    定義一個FormData叫做FORM_ID，且存檔到FILE_NAME
  * Builtin Events 
    * Save
    
    存檔
    * Load
    讀檔
    
    使用方式是 FORM_ID.Save,FORM_ID.Load
 
 # Events
   * Example
     * Closed
     * Click
   * Event的名稱後面可以接以下內容
     * 目標的預設EventID (例如FormData的Save, Load，Dialog的Close)
     * Dialog名稱 (跳出Dialog，用DoModal啟動)
     * ScriptName (檔名)
   * 定義event
     * [Event=EVENT_ID]
       Before=FORM_ID.Save
       Work=scripts\somescript.bat
       After=FORM_ID.Load
       
     定義名為EVENT_ID的Event，Before代表執行之前要執行什麼event，Work代表主要任務，After代表執行完畢後跑什麼任務
   
   
```~ini
[Dialog=Example]
Size=500,500
Location=-1,-1
Controls.Count=4
BackgroundImage=imgs\bg1.jpg

Control1.Type=Label
Control1.BackgroundColor=0,0,0,0
Control1.Size=100,20
Control1.Value=Input Data1
Control1.Location=100,100

Control2.Type=TextBox
Control2.BackgroundColor=0,0,0,0
Control2.BackgroundImage=imgs\bg.jpg
Control2.Size=200,20
Control2.Value=Test
Control2.Location=200,100
Control2.BoundData=Form1.Text1

Control3.Type=Label
Control3.BackgroundColor=0,0,0,0
Control3.Size=100,40
Control3.Value=Input Data2
Control3.Location=100,100

Control4.Type=TextBox
Control4.BackgroundColor=0,0,0,0
Control4.BackgroundImage=imgs\bg.jpg
Control4.Size=200,40
Control4.Value=Test
Control4.Location=200,100
Control4.BoundData=Form1.Text2

Control5.Type=Button
Control5.BackgroundColor=255,192,192,192
Control5.ForegroundColor=255,0,0,0
Control5.Text=Save
Control5.Size=70,20
Control5.Location=425,475
Contorl5.Events.Click=Form1.Save

[FormData=Form1,Save=output\Form1.txt]
Text1=
Text2=


[Event=EVT1]
Before=Form1.Save
Work=scripts\dosomething.bat
After=
```
