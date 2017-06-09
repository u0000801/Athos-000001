Opt("TrayOnEventMode",1)
Opt("TrayMenuMode",1)

$AboutItem = TrayCreateItem("About")
TrayItemSetOnEvent(-1,"ReadList")
TrayCreateItem("")
$ExitItem = TrayCreateItem("Exit")
TrayItemSetOnEvent(-1,"ReadList")

Func ReadList()
$SelectedItem = TrayItemGetText(@TRAY_ID)
 If $SelectedItem="Exit" Then
  Exit
 ElseIf $SelectedItem="About" Then
  Call("About")
 EndIf
EndFunc

Func About()
 MsgBox(064,"No Sleep Utility","Prevents your computer from automatically locking or going to screen saver.")
EndFunc

While 1
 Sleep(30000)
 $CurPos = MouseGetPos ( )
 MouseMove ( $CurPos[0] + 1, $CurPos[1] )
 MouseMove ( $CurPos[0] - 1, $CurPos[1] )
WEnd
