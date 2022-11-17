# Store_Input-APP

This application is developed by using PYTHON and pyinsaller module to make an .exe file.

First install:
1.Tkinter: pip install Tkinter
2.Pyinstaller: pip install pyinstaller

CODE OF THIS APPLICATION:

from tkinter import *
root = Tk()

root.title("Store Inputs")

file_name = Label(root, text="Enter The file name:")
file_name.grid(row=0, column=0)

entry = Entry(root)
entry.grid(row=0, column=1)

def name():
    name = Label(root, text="Enter your name:")
    name.grid(row=3, column=0)
    input_1 = Entry(root)
    input_1.grid(row=3, column=1)

    e_mail = Label(root, text="Enter your E-mail:")
    e_mail.grid(row=4, column=0)
    input_2 = Entry(root)
    input_2.grid(row=4, column=1)

    p_no = Label(root, text="Enter your phone number:")
    p_no.grid(row=5, column=0)
    input_3 = Entry(root)
    input_3.grid(row=5, column=1)

    def submit():
        with open(f'{entry.get()}.txt', 'a') as f:
            f.write(f'Name: {input_1.get()} \nE_mail: {input_2.get()}\nNumber: {input_3.get()}\n')

        input_1.delete(0, END)
        input_2.delete(0, END)
        input_3.delete(0, END)
        
    submit_b = Button(root, text="Submit", command=submit)
    submit_b.grid(row=7 , column=1)

name_b = Button(root, text='Name', command=name)
name_b.grid(row=1, column=1)
root.mainloop()
