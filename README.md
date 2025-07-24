**WEB AUTOMATION TESTING USING SELENIUM PYTHON**

**Features:**
1. Case normal -> Login Success
2. Case negative -> Login Invalid

**Set Up:**
1. Uses Chrome WebDriver for browser automation
2. Using python interpreter
3. Using selenium library
4. Using PyCharm as IDE Editor
5. Testing web: https://the-internet.herokuapp.com/login
   - Username: tomsmith
   - Password: SuperSecretPassword!

**How to Run:**
1. Positive login test -> python login_positive.py
2. Negative login test -> python login_negative.py

**Scipt:**
1. Positive case (valid login)
from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.common.keys import Keys
import time

driver = webdriver.Chrome()
driver.get("https://the-internet.herokuapp.com/login")

driver.find_element(By.ID, "username").send_keys("tomsmith")
driver.find_element(By.ID, "password").send_keys("SuperSecretPassword!")
driver.find_element(By.CLASS_NAME, "radius").click()
time.sleep(2)

2. Negative case (invalid login)
from selenium import webdriver
from selenium.webdriver.common.by import By
import time

driver = webdriver.Chrome()
driver.get("https://the-internet.herokuapp.com/login")

driver.find_element(By.ID, "username").send_keys("wronguser")
driver.find_element(By.ID, "password").send_keys("wrongpassword")
driver.find_element(By.CLASS_NAME, "radius").click()
time.sleep(2)

error_message = driver.find_element(By.ID, "flash").text
print("Error message:", error_message)

**Folder Project**
= PycharmProjects -> PythonProject -> .venv -> Scripts -> login_success.py & login_invalid.py

