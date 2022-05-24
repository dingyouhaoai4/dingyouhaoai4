- 👋 Hi, I’m @dingyouhaoai4
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
dingyouhaoai4/dingyouhaoai4 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->


import requests
from lxml import etree

url = 'https://voice.baidu.com/act/newpneumonia/newpneumonia/?from=osari_aladin_banner#tab4'
headers = {
    'User-Agent':'Mozilla/5.0 (Windows NT 10.0; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/70.0.3538.25 Safari/537.36 Core/1.70.3861.400 QQBrowser/10.7.4313.400'
}
page_text = requests.get(url=url,headers=headers).text
with open('./voice.html','w',encoding = 'utf-8') as fp:
    fp.write(page_text)

tree = etree.HTML(page_text)
append_text = tree.xpath('//div[@class="VirusSummarySix_1-1-350_2ZJJBJ"]/p[2]/text()')
with open(append_text,'w',encoding = 'utf-8') as fp1:
    fp1.write(page_text)
    print('over')
