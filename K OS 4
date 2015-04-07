import time
import getpass
import subprocess
import json
import os
import sys
def database_load():
        db = open("database1", 'r')
        data = json.loads(db.read())
        db.close()
        #print data['users']['kainen']['password']
        return data
        
def database_save(db):
        db_file = open("database1", 'w')
        data = json.dumps(db, separators=(',', ':'))
        db_file.write(data)
        db_file.close()
		
def add_user(db, username, password, adminask):
        if username in db['users'].keys():
                print("cannot comply, user exists")
                return
                
        db['users'][username] = {"password": password, "admin": adminask}
        database_save(db)

def clearscreen():
   os.system(['clear','cls'][os.name == 'nt'])

def loginscript(db, uname, passwd):
	clearscreen()
	print("welcome to kainen os 3")
	print("please enter username and password")
	uname = input("username: ")
	passwd = getpass.getpass("password: ")
	if uname in db['users'].keys():
				if passwd == db['users'][uname]['password']:
					clearscreen()
					menu(db, uname, passwd)
				else:
					#print 'DEBUG: password wrong'
					print("username or password incorrect")
					time.sleep(1)
					clearscreen()
					loginscript(db, 1, 2)
	else:
		#print 'DEBUG: Not in users'
		print("username or password incorect")
		time.sleep(1)
		clearscreen()
		loginscript(db, 1, 2)

def menu(db, uname, passwd):
	clearscreen()
	print("welcome " +uname)
	print("")
	print("1) admin stuff")
	print("2) games")
	print("3) steam")
	uinput1 = input()
	if uinput1 == "1":
		print("admin menu here")
		time.sleep(1)
		menu(db, uname, passwd)
	elif uinput1 == "2":
		print("games menu here")
		time.sleep(1)
		menu(db, uname, passwd)
	elif uinput1 == "3":
		print("steam games menu here")
		time.sleep(1)
		menu(db, uname, passwd)
def add_user(db, username, password, adminask):
        if username in db['users'].keys():
                print("cannot comply, user exists")
                return
                
        db['users'][username] = {"password": password, "admin": adminask}
        database_save(db)

def lockscreen(db, uname, passwd):
        clear_screen()  
        print("this computer is locked to " + uname)
        print("please enter password or type su to switch user")
        lockedpasswd = getpass.getpass("password: ")
        if lockedpasswd == db['users'][uname]['password']:
                menu(db, uname, passwd)
        elif lockedpasswd.lower() == "su":
                loginscript(db, uname, passwd)
        else:
                print("the password was wrong")
                time.sleep(1)
                lockscreen(db, uname, passwd)


def group_change(db, uname, passwd):
        uname_input = raw_input("enter the user name: ")
        if uname_input in db['users'].keys():
                adminchange = raw_input("a for admin or s for standard user: ")
                if adminchange.lower() == "a":
                        db['users'][uname_input]['admin'] = True
                        database_save(db)
                        menu(db, uname, passwd)
                
                elif adminchange.lower() == "s":
                        db['users'][uname_input]['admin'] = False
                        database_save(db)
                        menu(db, uname, passwd)
                
                else:
                        print("that was not a valid answer")
                        time.sleep(1)
                        menu(db, uname, passwd)
                        
        else:
                print("this user does not exist")
                time.sleep(1)
                menu(db, uname, passwd)

def password_reset(db, uname, passwd):
        unametoreset = raw_input("enter username to reset: ")
        if unametoreset in db['users'].keys():
                passwordtoreset = getpass.getpass("new password: ")
                passwordtoreset2 = getpass.getpass("enter password again: ")
                if passwordtoreset == passwordtoreset2:
                        db['users'][unametoreset]['password'] = passwordtoreset
                        database_save(db)
                        menu(db, uname, passwd)
                else:
                        print("passwords did not match")
                        time.sleep(1)
                        menu(db, uname, passwd)
        else:
                print("user does not exist")
                time.sleep(1)
                menu(db, uname, passwd)


def admin_menu(db, uname, passwd):
        print("1) add user")
        print("2) password reset")
        print("3) group change")
        uinput2 = input()
        if uinput2 == "1":
                add_user(db, uname, passwd)
        elif uinput == "2":
                password_reset(db, uname, passwd)
        elif uinput == "3":
                group_change(db, uname, passwd)
        else:
                print("not valid")
                time.sleep(1)
                admin_menu(db, uname, passwd)

def games_menu(db, uname, passwd):
        pass
        menu(db, uname, passwd)
def steam_menu(db, uname, passwd):
        pass
        menu(db, uname, passwd)
print("welcome to kainen os 4")
print("loading")
time.sleep(1)
clearscreen()
print("welcome to kainen os 4")
print("loading .")
time.sleep(1)
clearscreen()
print("welcome to kainen os 4")
print("loading ..")
time.sleep(1)
clearscreen()
print("welcome to kainen os 4")
print("loading ...")
time.sleep(1)
clearscreen()
print("welcome to kainen os 4")
print("loading")
time.sleep(1)
clearscreen()
print("welcome to kainen os 4")
print("loading .")
time.sleep(1)
clearscreen()
print("welcome to kainen os 4")
print("loading ..")
time.sleep(1)
clearscreen()
print("welcome to kainen os 4")
print("loading ...")
time.sleep(1)
clearscreen()

db = database_load()
loginscript(db, 1, 2)
