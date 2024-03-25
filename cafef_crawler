!apt-get update
!apt install chromium-chromedriver
!cp /usr/lib/chromium-browser/chromedriver /usr/bin
import sys
sys.path.insert(0,'/usr/lib/chromium-browser/chromedriver')
!pip install selenium
 
### Chrome_driver####
from selenium import webdriver
from selenium.webdriver.chrome.options import Options
 
chrome_options = Options()
chrome_options.add_argument("--headless")
chrome_options.add_argument("--no-sandbox")
chrome_options.add_argument("--disable-dev-shm-usage")
driver = webdriver.Chrome(options=chrome_options)
 
 
### Run###
from tqdm import tqdm
import requests
import pandas as pd
all_data = []
 
for page in tqdm(range(1, 20)):
    current_url = f'https://s.cafef.vn/Ajax/PageNew/DataHistory/GDKhoiNgoai.ashx?Symbol=FPT&StartDate=&EndDate=&PageIndex={page}&PageSize=20'
    response = requests.get(current_url)
    data = response.json()
    all_data.extend(data["Data"]["Data"])
df_all_pages = pd.DataFrame(all_data)
