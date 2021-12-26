# youtube
自動用google帳號登入youtube

from selenium.webdriver.common.keys import Keys
from selenium import webdriver
import time


# ------ 設定要前往的網址 ------
url = 'https://accounts.google.com/signin/v2/identifier?service=youtube&uilel=3&passive=true&continue=https%3A%2F%2Fwww.youtube.com%2Fsignin%3Faction_handle_signin%3Dtrue%26app%3Ddesktop%26hl%3Dzh-TW%26next%3Dhttps%253A%252F%252Fwww.youtube.com%252F&hl=zh-TW&ec=65620&flowName=GlifWebSignIn&flowEntry=ServiceLogin'  

# ------ 登入的帳號與密碼 ------
username = ''  # ''內打你的GOOGLE帳號
password = ''  # ''內打你的GOOGLE密碼 
# ------ 透過Browser Driver 開啟 Chrome ------
driver = webdriver.Chrome('C:/chromedriver_win32/chromedriver.exe')        

# ------ 前往該網址 ------
driver.get(url)
# ------ 賬號密碼 ------
elem = driver.find_element_by_id("identifierId")
elem.send_keys(username)
elem.send_keys(Keys.ENTER)
time.sleep(4)
elem = driver.find_element_by_name("password")
elem.send_keys(password)    
    

elem.send_keys(Keys.ENTER)
time.sleep(5)
