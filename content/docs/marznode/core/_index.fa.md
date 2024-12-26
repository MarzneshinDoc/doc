---
title: هسته
weight: 3
---

{{< callout emoji="🌐" >}}
 در این صفحه نحوه پیکربندی و راه‌اندازی هسته‌های زیر توضیح داده می‌شود.
{{< /callout >}}

همانطور که توضیح داده شده بود، مرزنود از 3 هسته زیر به عنوان هسته‌ی مرکزی استفاده می کند.
بر روی هر کدام از تب ها کلیک کنید تا به توضیحات مربوطه آن بروید.

{{< tabs items="Xray,hysteria2,SingBox" >}}

{{< tab >}}
{{< callout type="info" >}}
  هنگامی که مرزنود را نصب میکنید هسته  بصورت پیش فرض نصب و فعال میشود و نیازی به تنظیمات اضافی برای این هسته نیست.
{{< /callout >}}


در صورت نیاز، برای غیرفعال کردن هسته ایکس‌ری متغیر زیر را مقداردهی کنید 

```bash
  XRAY_ENABLED: "False"
  ```
  {{< /tab >}}

  {{< tab >}}
{{< callout type="info" >}}

با استفاده از آموزش ssl برای نودتون سرت بگیرید و داخل اینباند هیستریا قرار بدید تا ران بشه هسته هیستریاتون

{{< /callout >}}

 {{% steps %}}

### دانلود فایل کانفیگ Hysteria2:
*  با دستور زیر فایل کانفیگ را دریافت و در مسیر مشخص ذخیره کنید
    - ```bash
         curl -L https://github.com/marzneshin/marznode/raw/master/hysteria.yaml > /var/lib/marznode/hysteria.yaml
       ```
### ویرایش فایل تنظیمات Marznode:
* ابتدا به دایرکتوری Marznode بروید و فایل تنظیمات Docker Compose را باز کنید
    - ```bash
       cd marznode && nano compose.yml
      ```
##### ویرایش فایل تنظیمات نود لوکال (Local) پنل:
* برای نود `لوکال`، فایل زیر را ویرایش کنید
    - ```bash
      nano /etc/opt/marzneshin/docker-compose.yml
      ```

### افزودن متغیرهای زیر به فایل داکر:

  ```bash
HYSTERIA_CONFIG_PATH: "/var/lib/>marznode/hysteria.yaml"  
HYSTERIA_ENABLED: "True"  
 ```

### ریستارت Marznode:
* پس از اعمال تغییرات، سرویس Marznode را ریستارت کنید:

    - ```bash
      docker compose down && docker compose up -d
      ```
##### ریستارت نود لوکال پنل Marzneshin:
* برای نود لوکال از دستور زیر استفاده کنید
    
     - ```bash
       marzneshin restart
        ```


در صورت نیاز، برای غیرفعال کردن هسته هیستریا متغیر زیر را مقداردهی کنید 

```bash
  HYSTERIA_ENABLED: "False"
  ```
   {{% /steps %}}

  {{< /tab >}}
  {{< tab >}}
    {{% steps %}}
  ### دانلود فایل کانفیگ sing-box
  * با دستور زیر فایل کانفیگ را دریافت و در مسیر مشخص ذخیره کنید
    - ```bash
        curl -L https://raw.githubusercontent.com/MarzneshinsCommunity/files/refs/heads/main/sing-box.json > /var/lib/marznode/sing-box.json
        ```


  ### ویرایش فایل تنظیمات Marznode:
  * ابتدا به دایرکتوری Marznode بروید و فایل تنظیمات Docker Compose را باز کنید
      - ```bash
        cd marznode && nano compose.yml
          ```
##### ویرایش فایل تنظیمات نود `لوکال`(local) پنل:
*  برای نود (local)`لوکال`، فایل زیر را ویرایش کنید
    - ```bash
       nano /etc/opt/marzneshin/docker-compose.yml
        ```

### افزودن متغیرهای زیر به فایل داکر:
* ```bash
  SING_BOX_ENABLED: "True"
  SING_BOX_CONFIG_PATH: "/var/lib/marznode/sing-box.json"

   ```
### ریستارت Marznode:
* پس از اعمال تغییرات، سرویس Marznode را ریستارت کنید
    - ```bash
       docker compose down && docker compose up -d
        ```
##### ریستارت نود لوکال پنل Marzneshin:
* برای نود لوکال از دستور زیر استفاده کنید:
    - ```bash 
       marzneshin restart
       ```
در صورت نیاز، برای غیرفعال کردن هسته سینگ‌باکس متغیر زیر را مقداردهی کنید 


```bash
 SING_BOX_ENABLED: "False"
 ```



  {{% /steps %}}
  {{< /tab >}}

{{< /tabs >}}

