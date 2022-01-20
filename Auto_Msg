# Required Libraries
from selenium import webdriver
from time import sleep
from webdriver_manager.chrome import ChromeDriverManager
from datetime import datetime
from getpass import getpass

# Login Credentials, Name of the friend you want to message, Message.
usr = input('Enter Email Id : ')
pwd = getpass("Enter password(Don't worry,your password won't be visible) : ")
friend = input('Name of the friend(Enter the User Name of your friend) : ')
msg = input('Enter the message(No emojis) : ')
timer = input('Set the timer(HH:MM) : ').split(':')

while 1:

    # now variable stores present date and time.
    now = datetime.now()
    # We extract only time(HH:MM:SS) from now variable
    h,m,s = now.strftime("%H:%M:%S").split(':')
    
    # When the time is 00:00:00, the message is sent. 
    if int(h) == int(timer[0]) and int(m) >= int(timer[1]):

        # Installs the chrome driver to open Chrome browser.
        driver = webdriver.Chrome(ChromeDriverManager().install())
        
        # Opens the Facebook webpage using the link.
        driver.get('https://www.facebook.com/messages/t/')
        print ("Opened facebook")
        sleep(1)

        # find_element_by_id method searches for the "email" element in the html page and enters the email. 
        username_box = driver.find_element_by_id('email')
        username_box.send_keys(usr)
        print ("Email Id entered")
        sleep(1)

        # find_element_by_id method searches for the "pass" element in the html page and enters the password.
        password_box = driver.find_element_by_id('pass')
        password_box.send_keys(pwd)
        print ("Password entered")
        sleep(1)

        # find_element_by_id method searches for the "loginbutton" element in the html page and clicks the login button.
        login_box = driver.find_element_by_id('loginbutton')
        login_box.click()
        sleep(10)

        # find_element_by_xpath method searches for the "search" element in the html page and enters the friend name that you gave.
        search = driver.find_element_by_xpath('/html/body/div[1]/div/div[1]/div/div[3]/div/div/div[1]/div[1]/div[1]/div/div/div/div[2]/div/div/div/div/div/label/input')
        search.send_keys(friend)
        sleep(3)

        # find_element_by_xpath method searches for your friend name and enters the chat window.
        select_friend = driver.find_element_by_xpath('/html/body/div[1]/div/div[1]/div/div[3]/div/div/div[2]/div/div/div[1]/div[1]/div/div[1]/ul/li[1]/ul/li[2]/div/a/div/div[2]/div/div/span/span/span')
        select_friend.click()
        sleep(3)

        # find_element_by_xpath method searches for the chatting box and enters the message.
        chat = driver.find_element_by_xpath('/html/body/div[1]/div/div[1]/div/div[3]/div/div/div[1]/div[1]/div[2]/div/div/div/div/div/div/div[2]/div/div/div/div[2]/div/form/div/div[3]/div[2]/div[1]/div/div/div[2]/div/div[2]/div/div/div/div')
        chat.send_keys(msg)
        sleep(3)

        # find_element_by_xpath method searches for the "send" element in the html page and clicks the button.
        send = driver.find_element_by_xpath('/html/body/div[1]/div/div[1]/div/div[3]/div/div/div[1]/div[1]/div[2]/div/div/div/div/div/div/div[2]/div/div/div/div[2]/div/form/div/div[3]/span[2]/div')
        send.click()
        sleep(3)

        # Finally the message is sent successfully
        print ('\n==========Done.Message Sent!!!==========\n')
        driver.quit()
        break




