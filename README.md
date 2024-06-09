[[<p align="center">
  <a href="./README.md">
	English
	</a>
	|
	<a href="./README_fa.md">
	فارسی
	</a>
</p>

# ESSL چیست؟
ESSL (Easy SSL) یک اسکریپت کاربرپسند است که به منظور ساده‌سازی فرآیند دریافت گواهی‌نامه‌های SSL از طریق روش‌های مختلف طراحی شده است. این اسکریپت مراحل پیچیده و دستورات غیرضروری را حذف کرده و کاربران را قادر می‌سازد تنها با کپی و پیست یک خط فرمان، تمامی کارها را به صورت خودکار انجام دهند.

### ویژگی‌ها:
- گواهی‌نامه SSL برای یک دامنه (sub.domain.com)
- گواهی‌نامه SSL برای دامنه وایلدکارد (*.domain.com)
- گواهی‌نامه SSL برای چندین دامنه (sub1.domain1.com sub2.domain2.com)
- تمدید گواهی‌نامه SSL (بروزرسانی)
- لغو گواهی‌نامه SSL (حذف)
- وصله خودکار/سفارشی (پشتیبانی از تمام دایرکتوری‌های پنل‌ها)

### پشتیبانی:
- Acme
- Certbot
- API کلودفلر

> [!مهم]
> اسکریپت به صورت خودکار هم acme و هم certbot را برای تولید گواهی‌نامه آزمایش می‌کند.

## نحوه استفاده؟

تنها کافیست کپی/پیست کنید و لذت ببرید: 

```bash
sudo bash -c "$(curl -sL https://github.com/erfjab/ESSL/raw/main/essl.sh)"
<details>
<summary>یک دامنه</summary>

1. acme & certbot
	در حالت یک دامنه پس از تنظیم DNS تنها به موارد زیر نیاز دارید:
	- `دامنه` (به عنوان مثال: sub.doamin.com)
	- `ایمیل`
	
	پس از دریافت SSL، سه مسیر به شما نشان داده می‌شود: مسیر اول برای مسیر دلخواه، مسیر دوم برای مسیر پنل مرزی و مسیر سوم برای مسیر سایر پنل‌ها. شما به راحتی و به سرعت یک گواهی‌نامه دریافت می‌کنید.
2. API کلودفلر
	> API کلودفلر تنها گواهی‌نامه‌های وایلدکارد تولید می‌کند.

	با API کلودفلر نیازی به تنظیم DNS ندارید. شما به موارد زیر نیاز دارید:
	- `دامنه` (به عنوان مثال: domain.com)
	- `ایمیل حساب کلودفلر`
	- `کلید API جهانی کلودفلر`
	
 	چگونه کلید API جهانی کلودفلر را پیدا کنیم: [لینک](https://coda.io/@vishesh-jain/api-documentation/cloudflare-global-api-key-15)
	
 	پس از دریافت SSL، سه مسیر به شما نشان داده می‌شود: مسیر اول برای مسیر دلخواه، مسیر دوم برای مسیر پنل مرزی و مسیر سوم برای مسیر سایر پنل‌ها. شما به راحتی و به سرعت یک گواهی‌نامه دریافت می‌کنید.

</details>

<details>
<summary>دامنه وایلدکارد</summary>

1. acme & certbot
	در حالت دامنه وایلدکارد پس از تنظیم DNS تنها به موارد زیر نیاز دارید:
	- `دامنه` (به عنوان مثال: domain.com)
	- `ایمیل`

	اکنون یک نام و مقدار متنی به شما داده می‌شود که باید آن‌ها را در فرمت DNS متنی تنظیم کنید، پس از چند لحظه، تنظیمات را تایید کنید.

	پس از دریافت SSL، سه مسیر به شما نشان داده می‌شود: مسیر اول برای مسیر دلخواه، مسیر دوم برای مسیر پنل مرزی و مسیر سوم برای مسیر سایر پنل‌ها. شما به راحتی و به سرعت یک گواهی‌نامه دریافت می‌کنید.
2. API کلودفلر
	> API کلودفلر تنها گواهی‌نامه‌های وایلدکارد تولید می‌کند.
 
	با API کلودفلر نیازی به تنظیم DNS ندارید. شما به موارد زیر نیاز دارید:
	- `دامنه` (به عنوان مثال: domain.com)
	- `ایمیل حساب کلودفلر`
	- `کلید API جهانی کلودفلر`
	
 	چگونه کلید API جهانی کلودفلر را پیدا کنیم: [لینک](https://coda.io/@vishesh-jain/api-documentation/cloudflare-global-api-key-15)
	پس از دریافت SSL، سه مسیر به شما نشان داده می‌شود: مسیر اول برای مسیر دلخواه، مسیر دوم برای مسیر پنل مرزی و مسیر سوم برای مسیر سایر پنل‌ها. شما به راحتی و به سرعت یک گواهی‌نامه دریافت می‌کنید.

</details>

<details>
<summary>چندین دامنه</summary>
	
در حالت چندین دامنه پس از تنظیم DNS تنها به موارد زیر نیاز دارید:
- `دامنه‌ها` (در یک خط با فاصله به عنوان مثال: sub1.domain1.com sub2.domain2.com...)
- `ایمیل`

پس از دریافت SSL، سه مسیر به شما نشان داده می‌شود: مسیر اول برای مسیر دلخواه، مسیر دوم برای مسیر پنل مرزی و مسیر سوم برای مسیر سایر پنل‌ها. شما به راحتی و به سرعت یک گواهی‌نامه دریافت می‌کنید.
</details>

<details>
<summary>تمدید</summary>
	
در حالت تمدید تنها به موارد زیر نیاز دارید:
- `دامنه` (به عنوان مثال: *.domain.com (وایلدکارد) sub.domain.com (یک دامنه))

اگر نیاز به تمدید باشد، تمدید خواهد شد، در غیر این صورت اعلام می‌کند که هنوز نیازی به تمدید نیست.
</details>

<details>
<summary>لغو</summary>
	
در حالت لغو تنها به موارد زیر نیاز دارید:
- `دامنه` (به عنوان مثال: *.domain.com (وایلدکارد) sub.domain.com (یک دامنه))

اگر دامنه شما در لیست دامنه‌ها باشد، لغو خواهد شد.
</details>

## حمایت از پروژه

**ما به حمایت مالی نیاز نداریم، تنها ستاره (⭐) کافیست، متشکریم.**

[![Stargazers over time](https://starchart.cc/erfjab/essl.svg?variant=adaptive)](https://starchart.cc/erfjab/essl)
](https://github.com/erfjab/ESSL/assets/143827987/2e9873a6-1ea8-4777-a4f9-a18cd58a0a29


<p align="center">
  <a href="./README.md">
	English
	</a>
	|
	<a href="./README_fa.md">
	فارسی
	</a>
</p>

# اسکرپیت ESSL چیه؟
ای اس اس ال (ESSL یا Easy SSL) یک اسکریپت کاربرپسند است که برای ساده‌تر کردن فرآیند دریافت گواهی SSL از طریق روش‌های مختلف طراحی شده است. این اسکریپت فرآیند را ساده‌تر می‌کند و کاربران را از دستورات گیج‌کننده و غیرضروری نجات می‌دهد. فقط کپی/پیست کنید و لذت ببرید.

### قابلیت‌ها :
- گواهی تک دامنه (sub.domain.com)
- گواهی همه‌ی ساب‌ها (*.domain.com)
- گواهی مولتی-دامنه (sub1.doamin1.com sub2.domain2.com)
- تمدید گواهی (آپدیت)
- منقضی گواهی (تمدید)
- مسیردهی اتوماتیک/شخصی‌سازی (پیشتیبانی همه‌ی پنل‌ها)

### پشتیبانی:
- Acme
- Certbot
- Cloudflare api

> [!IMPORTANT]
> اسکریپت به صورت اتوماتیک هم acme و هم certbot را برای دریافت گواهی تست میکند.


## نحوه‌ی استفاده؟

فقط کپی/پیست کنید و لذت ببرید: 

```bash
sudo bash -c "$(curl -sL https://github.com/erfjab/ESSL/raw/main/essl.sh)"
```
<details>

<summary>تک دامنه</summary>

1. acme & certbot

	در تک دامنه بعد از تنظیم دی‌ان‌اس ها نیاز به دو چیز داریم:
	- `دامنه` (e.g: sub.doamin.com)
	- `ایمیل`
	
	بعد از دریافت گواهی به شما سه تا گزینه برای مسیردهی گواهی نمایش میدهد که اولی برای مسیردهی دلخواه دومی برای مسیردهی پنل مرزبان و سومی مسیردهی مناسب سایر پنل‌ها می‌باشد که اتوماتیک انجام میشود.
2. cloudflare api
	> توجه کنید که api های کلودفلر فقط گواهی wildcard دریافت میکنند. 

	با api های کلودفلر شما نیازی به تنظیم dns ندارید، پس:
	- `دامنه` (e.g: domain.com)
	- `ایمیل اکانت کلودفلر`
	- `کلید گلوبال api کلودفلر`
	
 	نحوه‌ی یافت کلید گلوبال api در کلودفلر : [Link](https://coda.io/@vishesh-jain/api-documentation/cloudflare-global-api-key-15)
	
	بعد از دریافت گواهی به شما سه تا گزینه برای مسیردهی گواهی نمایش میدهد که اولی برای مسیردهی دلخواه دومی برای مسیردهی پنل مرزبان و سومی مسیردهی مناسب سایر پنل‌ها می‌باشد که اتوماتیک انجام میشود.

</details>


<details>

<summary>گواهی همه‌ی ساب‌ها</summary>
1. acme & certbot

در گواهی همه‌ی ساب‌ها بعد از تنظیم دی‌ان‌اس ها نیاز به دو چیز داریم:
- `دامنه` (e.g: doamin.com)
- `ایمیل`

حالا به شما یک اسم و یک text value برای ساخت dns text نمایش میدهد که بعد از ساهت چند ثانیه صبر کنید و enter کلیک کنید تا اسکریپت به کارش ادامه دهد.
بعد از دریافت گواهی به شما سه تا گزینه برای مسیردهی گواهی نمایش میدهد که اولی برای مسیردهی دلخواه دومی برای مسیردهی پنل مرزبان و سومی مسیردهی مناسب سایر پنل‌ها می‌باشد که اتوماتیک انجام میشود.

2. cloudflare api

	با api های کلودفلر شما نیازی به تنظیم dns ندارید، پس:
	- `دامنه` (e.g: domain.com)
	- `ایمیل اکانت کلودفلر`
	- `کلید گلوبال api کلودفلر`
	
 	نحوه‌ی یافت کلید گلوبال api در کلودفلر : [Link](https://coda.io/@vishesh-jain/api-documentation/cloudflare-global-api-key-15)
	
	بعد از دریافت گواهی به شما سه تا گزینه برای مسیردهی گواهی نمایش میدهد که اولی برای مسیردهی دلخواه دومی برای مسیردهی پنل مرزبان و سومی مسیردهی مناسب سایر پنل‌ها می‌باشد که اتوماتیک انجام میشود.

</details>


<details>

<summary>مولتی-دامین</summary>
	
در گواهی مولتی-دامین بعد از تنظیم دی‌ان‌اس ها نیاز به دو چیز داریم:
- `دامنه ها` (in a line with a space e.g: sub1.domain1.com sub2.domain2.com...)
- `ایمیل`

بعد از دریافت گواهی به شما سه تا گزینه برای مسیردهی گواهی نمایش میدهد که اولی برای مسیردهی دلخواه دومی برای مسیردهی پنل مرزبان و سومی مسیردهی مناسب سایر پنل‌ها می‌باشد که اتوماتیک انجام میشود.
</details>

<details>

<summary>تمدید</summary>
	
در هنگام تمدید فقط به یک چیز نیاز داریم:
- `دامنه` (e.g: *.domain.com (wildcard) sub.domain.com (single))

اگر نیاز به تمدید داشته باشد، تمدید خواهد شد. در غیراینصورت به شما در مورد اینکه نیاز به تمدید ندارد پیامی نمایش خواهد داد شد.
</details>


<details>

<summary>منقضی</summary>
	
در هنگام منقضی فقط به یک چیز نیاز داریم:
- `نام دامنه` (e.g: *.domain.com (wildcard) sub.domain.com (single))
  
اگر دامنه‌ی شما در لیست دامنه ها موجود باشد، دامنه منقضی خواهد شد.
</details>

## حمایت پروژه 

**ما نیاز به حمایت مالی نداریم, فقط استار دادن (⭐) کافیه‌، ممنونیم.**

[![Stargazers over time](https://starchart.cc/erfjab/essl.svg?variant=adaptive)](https://starchart.cc/erfjab/essl)


)
](https://github.com/erfjab/ESSL/assets/143827987/2e9873a6-1ea8-4777-a4f9-a18cd58a0a29

<p align="center">
  <a href="./README.md">
	English
	</a>
	|
	<a href="./README_fa.md">
	فارسی
	</a>
</p>

# What is ESSL?
ESSL (Easy SSL) is a user-friendly script designed to streamline the process of obtaining SSL certificates through various methods. It simplifies the procedure, sparing users from confusing and unnecessary commands. just copy and paste one line so that everything is done automatically.

### Future's:
- Single domain ssl (sub.domain.com)
- Wildcard domain ssl (*.domain.com)
- Multi-domain ssl (sub1.doamin1.com sub2.domain2.com)
- Renewal ssl (update)
- Revoke ssl (delete)
- Automatic/Custom patch (support all panel's directory)

### Support:
- Acme
- Certbot
- Cloudflare api

> [!IMPORTANT]
> The script automatically tests both acme and certbot to generate the certificate.

## How to Use?

just copy/paste and enjoy : 

```bash
sudo bash -c "$(curl -sL https://github.com/erfjab/ESSL/raw/main/essl.sh)"
```
<details>

<summary>Single Domain</summary>

1. acme & certbot
	In single domain after set DNS you only need :
	- `domain` (e.g: sub.doamin.com)
	- `email`
	
	After receiving ssl, it will show you three path, the first one is for the desired path, the second one is for the border panel path and the third one is for the path of other panels. You received a certificate so easily and easily.
2. cloudflare api
	> Cloudflare api only generates wildcard certificates.

	With cloudflare api you don't need to set dns. well:
	- `domain` (e.g: domain.com)
	- `cloudflare account email`
	- `cloudflare global api key`
	
 	how to find cloudflare global api key : [Link](https://coda.io/@vishesh-jain/api-documentation/cloudflare-global-api-key-15)
	
 	After receiving ssl, it will show you three path, the first one is for the desired path, the second one is for the border panel path and the third one is for the path of other panels. You received a certificate so easily and easily.

</details>


<details>

<summary>Wildcard Domain</summary>

1. acme & certbot

	In wildcard domain after set DNS you only need :
	- `domain` (e.g: domain.com)
	- `email`

	Now it gives you a name and text value, which asks you to set them in text dns format, after a few moments, click set enter.

	After receiving ssl, it will show you three path, the first one is for the desired path, the second one is for the border panel path and the third one is for the path of other panels. You received a certificate so easily and easily.
2. cloudflare api

	> Cloudflare api only generates wildcard certificates.
 
	With cloudflare api you don't need to set dns. well:
	- `domain` (e.g: domain.com)
	- `cloudflare account email`
	- `cloudflare global api key`
	
 	how to find cloudflare global api key : [Link](https://coda.io/@vishesh-jain/api-documentation/cloudflare-global-api-key-15)
	After receiving ssl, it will show you three path, the first one is for the desired path, the second one is for the border panel path and the third one is for the path of other panels. You received a certificate so easily and easily.

</details>


<details>

<summary>Multi-Domain</summary>
	
In Multi domain after set DNS you only need :
- `domain's` (in a line with a space e.g: sub1.domain1.com sub2.domain2.com...)
- `email`

After receiving ssl, it will show you three path, the first one is for the desired path, the second one is for the border panel path and the third one is for the path of other panels. You received a certificate so easily and easily.
</details>

<details>

<summary>Renewal</summary>
	
In renewal you only need :
- `domain` (e.g: *.domain.com (wildcard) sub.domain.com (single))

If it needs to be extended, it will be extended, otherwise it will say that it is not needed yet.
</details>


<details>

<summary>Revoke</summary>
	
In Revoke fi you only need :
- `domain` (e.g: *.domain.com (wildcard) sub.domain.com (single))

If your domain is in the domain list, it will revoked.
</details>

## Support project 

**We don't need financial support, only Star (⭐) is enough, thank you.**

[![Stargazers over time](https://starchart.cc/erfjab/essl.svg?variant=adaptive)](https://starchart.cc/erfjab/essl)


)
