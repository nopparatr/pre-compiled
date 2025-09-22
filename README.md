
## CCMiner auto run on Termux

**`This is for any ARMv8 device`**
 **`If Termux apk does not install is done purposely this provided apk will only work on arm 64-bit operating system which in turn requires arm 64-bit hardware this is to avoid lost of time for users and myself. (Mining on 32-bit devices is not profitable)`**

[English](#installation) | [Thai](#การติดตั้ง)

 ## Installation:
1. Download & install latest arm64-v8a Termux [Download](https://github.com/termux/termux-app/releases/download/v0.118.0/termux-app_v0.118.0+github-debug_arm64-v8a.apk):
```
https://github.com/termux/termux-app/releases/download/v0.118.0/termux-app_v0.118.0+github-debug_arm64-v8a.apk
```
2. Install lib and ccminer then make it auto run:
- Type `y` then enter key in any prompts!

```
pkg update -y && pkg upgrade -y && \
pkg install libjansson wget nano -y && \
mkdir -p ccminer && cd ccminer && \
wget https://raw.githubusercontent.com/nopparatr/pre-compiled/main/ccminer && \
wget https://raw.githubusercontent.com/nopparatr/pre-compiled/main/config.json && \
wget https://raw.githubusercontent.com/nopparatr/pre-compiled/main/start.sh && \
chmod +x ccminer start.sh && \
echo 'bash /data/data/com.termux/files/home/ccminer/start.sh' >> /data/data/com.termux/files/usr/etc/bash.bashrc && \
bash /data/data/com.termux/files/home/ccminer/start.sh
```

## Usage:

1. Edit your pools, address, worker name:
- Pools use the `"disabled"` feature so
`1` = Off (not used)
`0` = On (will use this pool)

- Address & worker name is near the bottom of the config.json in format `address here.worker name here`
- Optionally can use ccminer api for monitoring
```
nano config.json
```
**config.json (Preview):**
```json
{
	"pools":
		[{
			"name": "SG-VIPORPOOL",
			"url":"stratum+tcp://sg.vipor.net:5040",
			"timeout": 180,
			"disabled": 0
		}],
	"user": "RUgMMJ3jfWX6VycDRM72155s1euZQDduq7.admin",
	"algo": "verus",
	"pass": "x",
	"threads": 8,
	"cpu-priority": 1,
	"retry-pause": 10,
	"api-allow": "192.168.0.0/16",
	"api-bind": "0.0.0.0:4068"
}
```
2. Start ccminer with:
```
~/ccminer/start.sh
```
3. Close ccminer with:
```
CTRL + c
```
# การติดตั้ง:

1. ดาวน์โหลดและติดตั้ง Termux arm64-v8a เวอร์ชันล่าสุด [ดาวน์โหลด](https://github.com/termux/termux-app/releases/download/v0.118.0/termux-app_v0.118.0+github-debug_arm64-v8a.apk):

```
https://github.com/termux/termux-app/releases/download/v0.118.0/termux-app_v0.118.0+github-debug_arm64-v8a.apk
```
2. ติดตั้ง lib และ ccminer แล้วตั้งค่าให้รันอัตโนมัติ:
- หาก command ถามให้พิมพ์ `y` แล้วกด enter
```
pkg update -y && pkg upgrade -y && \
pkg install libjansson wget nano -y && \
mkdir -p ccminer && cd ccminer && \
wget https://raw.githubusercontent.com/nopparatr/pre-compiled/main/ccminer && \
wget https://raw.githubusercontent.com/nopparatr/pre-compiled/main/config.json && \
wget https://raw.githubusercontent.com/nopparatr/pre-compiled/main/start.sh && \
chmod +x ccminer start.sh && \
echo 'bash /data/data/com.termux/files/home/ccminer/start.sh' >> /data/data/com.termux/files/usr/etc/bash.bashrc && \
bash /data/data/com.termux/files/home/ccminer/start.sh
```
# การใช้งาน:
1. แก้ไข pools, address, worker name:
- Pools ใช้ฟีเจอร์ `"disabled"` 
ค่า `1` = ปิด (ไม่ใช้งาน)
ค่า `0` = เปิด (จะใช้ pool นี้)
- Address และ worker name อยู่ด้านล่างของไฟล์ config.json ในรูปแบบ
`เลขกระเป๋า.ชื่อ`
```
nano config.json
```
**config.json (ตัวอย่าง):**

```json
{
	"pools":
		[{
			"name": "SG-VIPORPOOL",
			"url":"stratum+tcp://sg.vipor.net:5040",
			"timeout": 180,
			"disabled": 0
		}],
	"user": "RUgMMJ3jfWX6VycDRM72155s1euZQDduq7.admin",
	"algo": "verus",
	"pass": "x",
	"threads": 8,
	"cpu-priority": 1,
	"retry-pause": 10,
	"api-allow": "192.168.0.0/16",
	"api-bind": "0.0.0.0:4068"
}
```
2. เริ่มต้น ccminer ด้วย:
```
~/ccminer/start.sh
```
3. ปิด ccminer ด้วย:
```
CTRL + c
```
