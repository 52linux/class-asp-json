class asp dealing application/json 
```
<!--#include file="jsonObject.class.asp" -->

Dim post : post=BytesToStr(Request.BinaryRead(Request.TotalBytes))
Set oJSON = New aspJSON
oJSON.loadJSON(post)

Function BytesToStr(bytes)
Dim Stream
Set Stream = Server.CreateObject("Adodb.Stream")
    Stream.Type = 1 'adTypeBinary
    Stream.Open
    Stream.Write bytes
    Stream.Position = 0
    Stream.Type = 2 'adTypeText
    Stream.Charset = "iso-8859-1"
    BytesToStr = Stream.ReadText
    Stream.Close
Set Stream = Nothing
End Function


```
