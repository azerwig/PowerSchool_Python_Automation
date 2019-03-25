"# PowerSchool_Python_Automation" 
from selenium import webdriver

username = "azerwig"
password = "Azerwig_19"

driver = webdriver.Chrome()
driver.get("https://kippstl.powerschool.com/admin/pw.html")
username_field = driver.find_element_by_id("fieldUsername")
password_field = driver.find_element_by_id("fieldPassword")
login_button = driver.find_element_by_id("btnEnter")

username_field.send_keys(username)
password_field.send_keys(password)
login_button.click()

driver.get("https://kippstl.powerschool.com/admin/home.html")
HS_button = driver.find_element_by_xpath("//span[contains(text(),'KIPP St. Louis High School']")
HS_button.click()

driver.get("https://kippstl.powerschool.com/admin/sqlReports5/params.html?frn=0061634&lrn=005851")
login_button = driver.find_element_by_id("btnSubmit")
login_button.click()

driver.get("https://kippstl.powerschool.com/admin/sqlReports5/report5.html?frn=0061634")
html = driver.page_source
