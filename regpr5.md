import random
from pystyle import *
from atexit import register
from time import sleep
import os,json,re,sys
import threading,base64
import os,time,re,json,random
from datetime import datetime
from time import sleep,strftime
import requests
os.system('title TOOL REG PAGE PRO5')
dem = 0
listCookie = []

def clear():
    os.system("cls" if os.name == "nt" else "clear")
    
class reg_pro5():
	def __init__(self,cookies, name) -> None:
		self.cookies = cookies
		self._id = self.cookies.split('c_user=')[1].split(';')[0]
		self.name = name
		headers = {
		'authority': 'www.facebook.com',
	    'accept': 'text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9',
	    'accept-language': 'vi',
	    'cookie': self.cookies,
	    'sec-ch-prefers-color-scheme': 'light',
	    'sec-ch-ua': '"Chromium";v="106", "Google Chrome";v="106", "Not;A=Brand";v="99"',
	    'sec-ch-ua-mobile': '?0',
	    'sec-ch-ua-platform': '"Windows"',
	    'sec-fetch-dest': 'document',
	    'sec-fetch-mode': 'navigate',
	    'sec-fetch-site': 'none',
	    'sec-fetch-user': '?1',
	    'upgrade-insecure-requests': '1',
	    'user-agent': 'Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/106.0.0.0 Safari/537.36',
	    'viewport-width': '1366',
		}
		url = requests.get('https://www.facebook.com/me', headers=headers).url
		profile = requests.get(url, headers=headers).text
		try:
			self.fb_dtsg = profile.split('{"name":"fb_dtsg","value":"')[1].split('"},')[0]
		except:
			self.fb_dtsg = profile.split(',"f":"')[1].split('","l":null}')[0]
	def Reg(self):
		headers = {
		'authority': 'www.facebook.com',
		'accept': '*/*',
		'accept-language': 'vi-VN,vi;q=0.9,fr-FR;q=0.8,fr;q=0.7,en-US;q=0.6,en;q=0.5',
		'cookie': self.cookies,
		'origin': 'https://www.facebook.com',
		'referer': 'https://www.facebook.com/pages/creation?ref_type=launch_point',
		'sec-ch-prefers-color-scheme': 'dark',
		'sec-ch-ua-mobile': '?0',
		'sec-ch-ua-platform': '"Windows"',
		'sec-fetch-dest': 'empty',
		'sec-fetch-mode': 'cors',
		'sec-fetch-site': 'same-origin',
		'user-agent': 'Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/107.0.0.0 Safari/537.36',
		'viewport-width': '979',
		'x-fb-friendly-name': 'AdditionalProfilePlusCreationMutation',
		'x-fb-lsd': 'ZM7FAk6cuRcUp3imwqvHTY',
		}
		data = {
		'av': self._id,
		'__user': self._id,
		'__a': '1',
		'__dyn': '7AzHxq1mxu1syUbFuC0BVU98nwgU29zEdEc8co5S3O2S7o11Ue8hw6vwb-q7oc81xoswIwuo886C11xmfz81sbzoaEnxO0Bo7O2l2Utwwwi831wiEjwZwlo5qfK6E7e58jwGzE8FU5e7oqBwJK2W5olwuEjUlDw-wUws9ovUaU3qxWm2Sq2-azo2NwkQ0z8c84K2e3u362-2B0oobo',
		'__csr': 'gP4ZAN2d-hbbRmLObkZO8LvRcXWVvth9d9GGXKSiLCqqr9qEzGTozAXiCgyBhbHrRG8VkQm8GFAfy94bJ7xeufz8jK8yGVVEgx-7oiwxypqCwgF88rzKV8y2O4ocUak4UpDxu3x1K4opAUrwGx63J0Lw-wa90eG18wkE7y14w4hw6Bw2-o069W00CSE0PW06aU02Z3wjU6i0btw3TE1wE5u',
		'__req': 't',
		'__hs': '19296.HYP:comet_pkg.2.1.0.2.1',
		'dpr': '1',
		'__ccg': 'EXCELLENT',
		'__rev': '1006496476',
		'__s': '1gapab:y4xv3f:2hb4os',
		'__hsi': '7160573037096492689',
		'__comet_req': '15',
		'fb_dtsg': self.fb_dtsg,
		'jazoest': '25404',
		'lsd': 'ZM7FAk6cuRcUp3imwqvHTY',
		'__aaid': '800444344545377',
		'__spin_r': '1006496476',
		'__spin_b': 'trunk',
		'__spin_t': '1667200829',
		'fb_api_caller_class': 'RelayModern',
		'fb_api_req_friendly_name': 'AdditionalProfilePlusCreationMutation',
		'variables': '{"input":{"bio":"","categories":["181475575221097"],"creation_source":"comet","name":"'+self.name+'","page_referrer":"launch_point","actor_id":"'+self._id+'","client_mutation_id":"1"}}',
		'server_timestamps': 'true',
		'doc_id': '5903223909690825',
		}
		rp = requests.post('https://www.facebook.com/api/graphql/', headers=headers, data=data)
		return rp
Write.Print('[LƯU Ý] Muốn Dừng Thì Nhấn Enter\n',Colors.green_to_yellow,interval=0.0001)
for i in range(10000000):
    cookies = str(Write.Input("Nhập Cookie Thứ "+str(i+1)+": ",Colors.green_to_white,interval=0.0001))
    if cookies != '':
        listCookie.append(cookies)
    else:
    	break
dl = int(Write.Input('Nhập Delay: ',Colors.green_to_white,interval=0.0001))
def idelay(o):
    while(o>1):
        o=o-1
        Write.Print(f'[FRIVE][.....][{o}]',Colors.green_to_yellow,interval=0.0001,end='\r');sleep(1/6)
        Write.Print(f'[FRIVE][X....][{o}]',Colors.green_to_yellow,interval=0.0001,end='\r');sleep(1/6)
        Write.Print(f'[FRIVE][XX...][{o}]',Colors.green_to_yellow,interval=0.0001,end='\r');sleep(1/6)
        Write.Print(f'[FRIVE][XXX..][{o}]',Colors.green_to_yellow,interval=0.0001,end='\r');sleep(1/6)
        Write.Print(f'[FRIVE][XXXX.][{o}]',Colors.green_to_yellow,interval=0.0001,end='\r');sleep(1/6)
        Write.Print(f'[FRIVE][XXXXX][{o}]',Colors.green_to_yellow,interval=0.0001,end='\r');sleep(1/6)

for i in range (1):
	for ck in listCookie:
		cookies = (ck)
		cookie = cookies
		i = 0
		while True:
			gender = random.choice(["male", "female"])
			name = requests.get("https://story-shack-cdn-v2.glitch.me/generators/vietnamese-name-generator/").json()["data"][gender]
			__start = time.time()
			reg = reg_pro5(cookies, name).Reg()
			if "id" in reg.text:
				id = reg.json()["data"]["additional_profile_plus_create"]["additional_profile"]["id"]
				tg=datetime.now().strftime('%H:%M')
				dem = dem + 1
				Write.Print(f'[{dem}] | {tg} | {id} | {name} |\n',Colors.green_to_red,interval=0.0001)
			else:
				tg=datetime.now().strftime('%H:%M')
				dem = dem + 1
				Write.Print(f'[X] | {tg} | ACC BỊ BLOCK | ERROR \n',Colors.green_to_red,interval=0.0001)
			idelay(dl)
			i+=1
			if i == 10:
			    Write.Print(f"────────────────────────────────────────────────────────────\n",Colors.green_to_yellow,interval=0.0001)
			    break
