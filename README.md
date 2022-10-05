#Python 3.X
from selenium import webdriver
from PIL import Image
from Screenshot import Screenshot
from selenium.webdriver.firefox.options import Options
from selenium.webdriver.firefox.service import Service
from selenium.webdriver.support.ui import WebDriverWait
from selenium.webdriver.support import expected_conditions as EC
from selenium.webdriver.common.by import By
from selenium.common.exceptions import TimeoutException
from selenium.webdriver.common.keys import Keys
import time
from selenium.webdriver.firefox.options import Options
from selenium.webdriver.common.action_chains import ActionChains
from selenium.webdriver.support.ui import Select





#Setup driver to use and the URL to go to
driver = webdriver.Firefox()
wait= WebDriverWait(driver, 5)
driver.maximize_window()
driver.get('https://www.sovtech.co.za/contact-us/')


  
time.sleep(4)


#Switch to frame
driver.switch_to.frame(1)


#name field
name = driver.find_element(By.CSS_SELECTOR, '#your_name-c2e387f9-4bd8-496f-ab2a-81fbbc31712a')
name.send_keys('Menzi')
time.sleep(2)
name.send_keys(Keys.TAB)


#email
time.sleep(3)
work_email = driver.find_element(By.CSS_SELECTOR,'#email-c2e387f9-4bd8-496f-ab2a-81fbbc31712a')
work_email.send_keys('something@gmail.com')
time.sleep(2)
work_email.send_keys(Keys.TAB)







#cell number
time.sleep(3)
cell_number = driver.find_element(By.CSS_SELECTOR,'#mobilephone-c2e387f9-4bd8-496f-ab2a-81fbbc31712a')
cell_number.send_keys('+27660785207')
time.sleep(2)
cell_number.send_keys(Keys.TAB)








#Company size drop down 
time.sleep(3)

company_size_drop = driver.find_element(By.CSS_SELECTOR, '#numemployees-c2e387f9-4bd8-496f-ab2a-81fbbc31712a')
company_size_drop.click()

company_size_drop_menu_list = Select(driver.find_element(By.CSS_SELECTOR, '#numemployees-c2e387f9-4bd8-496f-ab2a-81fbbc31712a'))

# select by visible text
company_size_drop_menu_list.select_by_visible_text('100-500')


 
 
 
 
#What service u looking for?
time.sleep(3)
what_serv = driver.find_element(By.CSS_SELECTOR, '#what_kind_of_problem_is_your_business_currently_facing_-c2e387f9-4bd8-496f-ab2a-81fbbc31712a')
what_serv.click()
looking_for_list = Select(driver.find_element(By.CSS_SELECTOR, '#what_kind_of_problem_is_your_business_currently_facing_-c2e387f9-4bd8-496f-ab2a-81fbbc31712a'))

# select by visible text
looking_for_list.select_by_visible_text('Design and prototype a new idea')


#how can we help
time.sleep(3)
how_help = driver.find_element(By.CSS_SELECTOR,'#message-c2e387f9-4bd8-496f-ab2a-81fbbc31712a')
how_help.send_keys('I need assistance')
time.sleep(2)
how_help.send_keys(Keys.TAB)


#I agree to receive communications
time.sleep(3)
agree_box = driver.find_element(By.CSS_SELECTOR, '#LEGAL_CONSENT\.subscription_type_10841063-c2e387f9-4bd8-496f-ab2a-81fbbc31712a')
agree_box.click()



#Submit button
time.sleep(3)
button = driver.find_element(By.CSS_SELECTOR, '.hs-button')
button.click()


#close browser
time.sleep(3)
driver.close()
