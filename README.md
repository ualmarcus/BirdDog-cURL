# BirdDog-cURL
cURL commands to control a BirdDog Studio or Mini NDI Encoder / Decoder

Birddog Firmware v 2.0.7 Public Beta -  Command list
------

Shortened: 

Switch NDI Decode Sources when in Decode mode:
------
```
curl -s http://birddog-b334e.local/login -c cookiefile.txt -d "auth_password=birddog" && curl -b cookiefile.txt -s 'http://birddog-b334e.local/operation-configuration' -H 'Connection: keep-alive' -H 'Cache-Control: max-age=0' -H 'Content-Type: multipart/form-data; boundary=----WebKitFormBoundaryLrzvccuVYBrErN9Q' --data-binary $'------WebKitFormBoundaryLrzvccuVYBrErN9Q\r\nContent-Disposition: form-data; name="source_name"\r\n\r\n"MSTHREESTICKM5 (Intel(R) HD Graphics 515 1)"\r\n------WebKitFormBoundaryLrzvccuVYBrErN9Q\r\nContent-Disposition: form-data; name="change_source_button"\r\n\r\nchange_source\r\n------WebKitFormBoundaryLrzvccuVYBrErN9Q--\r\n' --compressed
```
```
curl -s http://birddog-b334e.local/login -c cookiefile.txt -d "auth_password=birddog" && curl -b cookiefile.txt -s 'http://birddog-b334e.local/operation-configuration' -H 'Connection: keep-alive' -H 'Cache-Control: max-age=0' -H 'Content-Type: multipart/form-data; boundary=----WebKitFormBoundaryLrzvccuVYBrErN9Q' --data-binary $'------WebKitFormBoundaryLrzvccuVYBrErN9Q\r\nContent-Disposition: form-data; name="source_name"\r\n\r\n"UALRETINA.LOCAL (NDI Signal Generator)"\r\n------WebKitFormBoundaryLrzvccuVYBrErN9Q\r\nContent-Disposition: form-data; name="change_source_button"\r\n\r\nchange_source\r\n------WebKitFormBoundaryLrzvccuVYBrErN9Q--\r\n' --compressed
```
```
curl -s http://birddog-b334e.local/login -c cookiefile.txt -d "auth_password=birddog" && curl -b cookiefile.txt -s 'http://birddog-b334e.local/operation-configuration' -H 'Connection: keep-alive' -H 'Cache-Control: max-age=0' -H 'Content-Type: multipart/form-data; boundary=----WebKitFormBoundaryLrzvccuVYBrErN9Q' --data-binary $'------WebKitFormBoundaryLrzvccuVYBrErN9Q\r\nContent-Disposition: form-data; name="source_name"\r\n\r\n"BIRDDOG-B265B (HDMI)"\r\n------WebKitFormBoundaryLrzvccuVYBrErN9Q\r\nContent-Disposition: form-data; name="change_source_button"\r\n\r\nchange_source\r\n------WebKitFormBoundaryLrzvccuVYBrErN9Q--\r\n' --compressed
```

Switch Decode Mode to ON:
-----
```
curl -s http://birddog-b334e.local/login -c cookiefile.txt -d "auth_password=birddog" && curl -b cookiefile.txt -s 'http://birddog-b334e.local/operation-configuration' -H 'Connection: keep-alive' -H 'Cache-Control: max-age=0' -H 'Content-Type: multipart/form-data; boundary=----WebKitFormBoundaryA24wNG3dbt8rOKz7' --data-binary $'------WebKitFormBoundaryA24wNG3dbt8rOKz7\r\nContent-Disposition: form-data; name="mode"\r\n\r\nDecode\r\n------WebKitFormBoundaryA24wNG3dbt8rOKz7\r\nContent-Disposition: form-data; name="operation_mode_button"\r\n\r\noperation_mode\r\n------WebKitFormBoundaryA24wNG3dbt8rOKz7--\r\n' --compressed
```

Switch Encode Mode to ON:
-----
```
curl -s http://birddog-b334e.local/login -c cookiefile.txt -d "auth_password=birddog" && curl -b cookiefile.txt -s 'http://birddog-b334e.local/operation-configuration' -H 'Connection: keep-alive' -H 'Cache-Control: max-age=0' -H 'Content-Type: multipart/form-data; boundary=----WebKitFormBoundaryA24wNG3dbt8rOKz7' --data-binary $'------WebKitFormBoundaryA24wNG3dbt8rOKz7\r\nContent-Disposition: form-data; name="mode"\r\n\r\nEncode\r\n------WebKitFormBoundaryA24wNG3dbt8rOKz7\r\nContent-Disposition: form-data; name="operation_mode_button"\r\n\r\noperation_mode\r\n------WebKitFormBoundaryA24wNG3dbt8rOKz7--\r\n' --compressed
```

Set Encode Video setting to AUTO / HDMI:
-----
```
curl -s http://birddog-b334e.local/login -c cookiefile.txt -d "auth_password=birddog" && curl -b cookiefile.txt -s 'http://birddog-b334e.local/video' -H 'Connection: keep-alive' -H 'Cache-Control: max-age=0' --data 'video-app-params=-H+AUTO+-a+-n+HDMI&video-form-path=video-param-grp-Manual-HDMI-Auto' --compressed
```


Combined Commands
-----------

Switch Decode Mode to ON and switch to a named NDI Source:
-----
```
curl -s http://birddog-b334e.local/login -c cookiefile.txt -d "auth_password=birddog" && curl -b cookiefile.txt -s 'http://birddog-b334e.local/operation-configuration' -H 'Connection: keep-alive' -H 'Cache-Control: max-age=0' -H 'Content-Type: multipart/form-data; boundary=----WebKitFormBoundaryLrzvccuVYBrErN9Q' --data-binary $'------WebKitFormBoundaryLrzvccuVYBrErN9Q\r\nContent-Disposition: form-data; name="source_name"\r\n\r\n"UALRETINA.LOCAL (NDI Signal Generator)"\r\n------WebKitFormBoundaryLrzvccuVYBrErN9Q\r\nContent-Disposition: form-data; name="change_source_button"\r\n\r\nchange_source\r\n------WebKitFormBoundaryLrzvccuVYBrErN9Q--\r\n' --compressed && curl -b cookiefile.txt -s 'http://birddog-b334e.local/operation-configuration' -H 'Connection: keep-alive' -H 'Cache-Control: max-age=0' -H 'Content-Type: multipart/form-data; boundary=----WebKitFormBoundaryA24wNG3dbt8rOKz7' --data-binary $'------WebKitFormBoundaryA24wNG3dbt8rOKz7\r\nContent-Disposition: form-data; name="mode"\r\n\r\nDecode\r\n------WebKitFormBoundaryA24wNG3dbt8rOKz7\r\nContent-Disposition: form-data; name="operation_mode_button"\r\n\r\noperation_mode\r\n------WebKitFormBoundaryA24wNG3dbt8rOKz7--\r\n' --compressed
```
```
curl -s http://10.80.89.35/login -c cookiefile.txt -d "auth_password=birddog" && curl -b cookiefile.txt -s 'http://10.80.89.35/operation-configuration' -H 'Connection: keep-alive' -H 'Cache-Control: max-age=0' -H 'Content-Type: multipart/form-data; boundary=----WebKitFormBoundaryLrzvccuVYBrErN9Q' --data-binary $'------WebKitFormBoundaryLrzvccuVYBrErN9Q\r\nContent-Disposition: form-data; name="source_name”\r\n\r\n”MACBOOK-PRO-2.ARTS.LOCAL (NDI Signal Generator)"\r\n------WebKitFormBoundaryLrzvccuVYBrErN9Q\r\nContent-Disposition: form-data; name="change_source_button"\r\n\r\nchange_source\r\n------WebKitFormBoundaryLrzvccuVYBrErN9Q--\r\n' --compressed && curl -b cookiefile.txt -s 'http://10.80.89.35/operation-configuration' -H 'Connection: keep-alive' -H 'Cache-Control: max-age=0' -H 'Content-Type: multipart/form-data; boundary=----WebKitFormBoundaryA24wNG3dbt8rOKz7' --data-binary $'------WebKitFormBoundaryA24wNG3dbt8rOKz7\r\nContent-Disposition: form-data; name="mode"\r\n\r\nDecode\r\n------WebKitFormBoundaryA24wNG3dbt8rOKz7\r\nContent-Disposition: form-data; name="operation_mode_button"\r\n\r\noperation_mode\r\n------WebKitFormBoundaryA24wNG3dbt8rOKz7--\r\n' --compressed
```
```
curl -s http://birddog-b334e.local/login -c cookiefile.txt -d "auth_password=birddog" && curl -b cookiefile.txt -s 'http://birddog-b334e.local/operation-configuration' -H 'Connection: keep-alive' -H 'Cache-Control: max-age=0' -H 'Content-Type: multipart/form-data; boundary=----WebKitFormBoundaryLrzvccuVYBrErN9Q' --data-binary $'------WebKitFormBoundaryLrzvccuVYBrErN9Q\r\nContent-Disposition: form-data; name="source_name"\r\n\r\n"BIRDDOG-B265B (HDMI)"\r\n------WebKitFormBoundaryLrzvccuVYBrErN9Q\r\nContent-Disposition: form-data; name="change_source_button"\r\n\r\nchange_source\r\n------WebKitFormBoundaryLrzvccuVYBrErN9Q--\r\n' --compressed && curl -b cookiefile.txt -s 'http://birddog-b334e.local/operation-configuration' -H 'Connection: keep-alive' -H 'Cache-Control: max-age=0' -H 'Content-Type: multipart/form-data; boundary=----WebKitFormBoundaryA24wNG3dbt8rOKz7' --data-binary $'------WebKitFormBoundaryA24wNG3dbt8rOKz7\r\nContent-Disposition: form-data; name="mode"\r\n\r\nDecode\r\n------WebKitFormBoundaryA24wNG3dbt8rOKz7\r\nContent-Disposition: form-data; name="operation_mode_button"\r\n\r\noperation_mode\r\n------WebKitFormBoundaryA24wNG3dbt8rOKz7--\r\n' --compressed
```


Switch Encode Mode to ON and set Video to AUTO / HDMI:
----- 
```
curl -s http://birddog-b334e.local/login -c cookiefile.txt -d "auth_password=birddog" && curl -b cookiefile.txt -s 'http://birddog-b334e.local/video' -H 'Connection: keep-alive' -H 'Cache-Control: max-age=0' --data 'video-app-params=-H+AUTO+-a+-n+HDMI&video-form-path=video-param-grp-Manual-HDMI-Auto' --compressed && curl -b cookiefile.txt -s 'http://birddog-b334e.local/operation-configuration' -H 'Connection: keep-alive' -H 'Cache-Control: max-age=0' -H 'Content-Type: multipart/form-data; boundary=----WebKitFormBoundaryA24wNG3dbt8rOKz7' --data-binary $'------WebKitFormBoundaryA24wNG3dbt8rOKz7\r\nContent-Disposition: form-data; name="mode"\r\n\r\nEncode\r\n------WebKitFormBoundaryA24wNG3dbt8rOKz7\r\nContent-Disposition: form-data; name="operation_mode_button"\r\n\r\noperation_mode\r\n------WebKitFormBoundaryA24wNG3dbt8rOKz7--\r\n' --compressed
```
