# zonestar_P802N_private_custom
a private fork for ZoneStar P802N firmware based Repetier-Firmware v0.92.9

問題
* AutoLevelingの測定時に、1カ所目、4カ所目、7カ所目のY位置が手前過ぎてベッドをはみ出してるっぽい問題
* 9箇所測定し終わった後に、X軸右手に移動をはじめてフレームに激突する問題

これらをモンキーパッチで解決する。
* AutoLevelingの測定時は、Y位置を10mm奥にずらして測定するようにした
* 9箇所測定し終わった後の移動(Printer::finishProbing())を呼ばないようにした。(ただし副作用不明)

とりあえずこれで、手元のP802Nでは、正常にAutoLevelingが動いている。
