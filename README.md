# Student_registration_Xpath
# Name: Harini S
# Reg no : 212223240048
# Code
```
from selenium import webdriver
from selenium.webdriver.common.by import By
from selenium.webdriver.support.ui import WebDriverWait
from selenium.webdriver.support import expected_conditions as EC


# --------------------------------------------------
# 1. Open Browser
# --------------------------------------------------

driver = webdriver.Chrome()

driver.maximize_window()

driver.get("https://www.selenium.dev/selenium/web/web-form.html")


# --------------------------------------------------
# 2. Create Explicit Wait
# --------------------------------------------------

wait = WebDriverWait(driver, 10)


# ==================================================
# 3. ABSOLUTE XPATH
# ==================================================

# Example:
# /html/body/main/div/form/div/div/input

try:
    element = driver.find_element(
        By.XPATH,
        "/html/body/main/div/form/div/div/input"
    )

    print("Absolute XPath:")
    print(element.get_attribute("name"))

except Exception as e:
    print("Absolute XPath failed:", e)


# ==================================================
# 4. RELATIVE XPATH
# ==================================================

text_box = driver.find_element(
    By.XPATH,
    "//input[@name='my-text']"
)

text_box.clear()
text_box.send_keys("Jeevan")

print("Relative XPath executed")


# ==================================================
# 5. XPATH WITH ATTRIBUTE
# ==================================================

text_box = driver.find_element(
    By.XPATH,
    "//input[@name='my-text']"
)

text_box.clear()
text_box.send_keys("Selenium Python")

print("Attribute XPath executed")


# ==================================================
# 6. XPATH WITH TEXT
# ==================================================

# Find the Submit button using its text

submit_button = driver.find_element(
    By.XPATH,
    "//button[text()='Submit']"
)

print("Text XPath:")
print(submit_button.text)


# ==================================================
# 7. contains()
# ==================================================

# Find input whose name contains 'my'

element = driver.find_element(
    By.XPATH,
    "//input[contains(@name,'my')]"
)

element.clear()
element.send_keys("Contains Example")

print("contains() executed")


# ==================================================
# 8. contains() WITH TEXT
# ==================================================

button = driver.find_element(
    By.XPATH,
    "//button[contains(text(),'Submit')]"
)

print("contains() with text executed")


# ==================================================
# 9. starts-with()
# ==================================================

element = driver.find_element(
    By.XPATH,
    "//input[starts-with(@name,'my')]"
)

print("starts-with() executed")


# ==================================================
# 10. text()
# ==================================================

button = driver.find_element(
    By.XPATH,
    "//button[text()='Submit']"
)

print("text() XPath executed")


# ==================================================
# 11. PARENT AXIS
# ==================================================

# Find the parent element of the input

parent = driver.find_element(
    By.XPATH,
    "//input[@name='my-text']/parent::*"
)

print("Parent tag:")
print(parent.tag_name)


# ==================================================
# 12. CHILD AXIS
# ==================================================

# Find child input elements inside the form

children = driver.find_elements(
    By.XPATH,
    "//form/child::*"
)

print("Number of direct children:")
print(len(children))


# ==================================================
# 13. ANCESTOR AXIS
# ==================================================

ancestor = driver.find_element(
    By.XPATH,
    "//input[@name='my-text']/ancestor::form"
)

print("Ancestor tag:")
print(ancestor.tag_name)


# ==================================================
# 14. DESCENDANT AXIS
# ==================================================

descendants = driver.find_elements(
    By.XPATH,
    "//form/descendant::input"
)

print("Number of input descendants:")
print(len(descendants))


# ==================================================
# 15. FOLLOWING AXIS
# ==================================================

following_elements = driver.find_elements(
    By.XPATH,
    "//input[@name='my-text']/following::*"
)

print("Following elements:")
print(len(following_elements))


# ==================================================
# 16. PRECEDING AXIS
# ==================================================

preceding_elements = driver.find_elements(
    By.XPATH,
    "//button[text()='Submit']/preceding::*"
)

print("Preceding elements:")
print(len(preceding_elements))


# ==================================================
# 17. FOLLOWING-SIBLING AXIS
# ==================================================

following_siblings = driver.find_elements(
    By.XPATH,
    "//input[@name='my-text']/following-sibling::*"
)

print("Following siblings:")
print(len(following_siblings))


# ==================================================
# 18. PRECEDING-SIBLING AXIS
# ==================================================

preceding_siblings = driver.find_elements(
    By.XPATH,
    "//button[text()='Submit']/preceding-sibling::*"
)

print("Preceding siblings:")
print(len(preceding_siblings))


# ==================================================
# 19. WAIT + XPATH
# ==================================================

submit_button = wait.until(
    EC.element_to_be_clickable(
        (By.XPATH, "//button[text()='Submit']")
    )
)

print("Submit button is clickable")


# ==================================================
# 20. SUBMIT
# ==================================================

submit_button.click()

print("Form submitted successfully")


# --------------------------------------------------
# Keep browser open
# --------------------------------------------------

input("Press Enter to close browser...")

driver.quit()
```
# Output
<img width="1902" height="997" alt="image" src="https://github.com/user-attachments/assets/a86745d4-e8cb-46b1-a646-0db7610c1800" />
