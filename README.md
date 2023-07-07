# Reflected XSS 1
Geeklog v2.2.2 is vulnerable to Reflected Cross-Site Scripting (XSS) in public_html/admin/configuration.php

Vendor:https://github.com/Geeklog-Core/geeklog

## PoC
1. Log in to the Geeklog's admin account and Navigate to Configuration->Mail.
![Config_mail](https://github.com/CrownZTX/reflectedxss1/blob/main/images/geeklog_config_mail.png)

2. Enter the payload to the input area of Mail Settings[backend] and click on SAVE CHANGES. The payload is
~~~
"><script>alert('xss');</script>
~~~
![bankend_inject](https://github.com/CrownZTX/reflectedxss1/blob/main/images/geeklog_bankend_inject.png)
3. We can observe the payload getting triggered.
![bankend_reflect](https://github.com/CrownZTX/reflectedxss1/blob/main/images/geeklog_bankend_reflect.png)

4.Similarly, we can enter the payload to the input area of Mail Settings[host], Mail Settings[port] and Mail Settings[auth].
![hpa_inject](https://github.com/CrownZTX/reflectedxss1/blob/main/images/geeklog_bankend_reflect.png)

5. We can observe all payloads getting triggered.
![hpa_reflect](https://github.com/CrownZTX/reflectedxss1/blob/main/images/geeklog_bankend_reflect.png)
