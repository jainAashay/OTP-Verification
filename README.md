from tkinter import *
from tkinter import messagebox
import smtplib
import random
otp = random.randint(1000, 9999)
otp = str(otp)
root = Tk()
root.title("Send OTP Via Email")
root.geometry("565x450")
email_label = Label(root, text="Enter receiver's Email: ",font="ariel 15 bold", relief=FLAT)
email_label.grid(row=0, column=0, padx=15, pady=60)
email_entry = Entry(root, font="ariel 15 bold", width=25,relief=GROOVE, bd=2)
email_entry.grid(row=0, column=1, padx=12, pady=60)
email_entry.focus()
def check():
if(e.get()==otp):
messagebox.showinfo("Send OTP via Email", "Verification
Successfull")
else:
messagebox.showinfo("Send OTP via Email", "Verification
Unsuccessfull")
def send():
try:
s = smtplib.SMTP("smtp.gmail.com", 587) # 587 is a port number

s.starttls()
ssender = aashay1000@gmail.com
spass = "frwe dkwc sbgr jpgz"
s.login(ssender, spass)
s.sendmail(ssender, email_entry.get(), otp)

messagebox.showinfo("Send OTP via Email", f"OTP sent to {email_entry.get()}")
s.quit()
except:
messagebox.showinfo("Send OTP via Email","Please enter the valid email address OR check an internet connection")
send_button = Button(root, text="Send Email", font="ariel 15
bold", bg="black", fg="green2", bd=3, command=send)
send_button.place(x=210, y=150)
Label(root,text="Enter OTP :",font="ariel 15).place(x=20,y=200)
var=IntVar()
e=Entry(root,textvariable=var,font="ariel 15 bold", width=25,relief=GROOVE, bd=2)
e.place(x=250,y=250)
Button(root,text="Verify",font="ariel 15 bold", bg="black",
fg="green2", bd=3,command=check).place(x=230,y=350)
root.mainloop()
