import tkinter
from tkinter import *
from tkinter import messagebox

#functions_to_make_my_buttons_work

val = ""
A = 0
operator=""


def btn_1_clicked():
    global val
    val=val+"7"
    data.set(val)

def btn_2_clicked():
    global val
    val=val+"8"
    data.set(val)

def btn_3_clicked():
    global val
    val=val+"9"
    data.set(val)

def btn_5_clicked():
    global val
    val=val+"4"
    data.set(val)

def btn_6_clicked():
    global val
    val=val+"5"
    data.set(val)

def btn_7_clicked():
    global val
    val=val+"6"
    data.set(val)

def btn_9_clicked():
    global val
    val=val+"1"
    data.set(val)

def btn_10_clicked():
    global val
    val=val+"2"
    data.set(val)

def btn_11_clicked():
    global val
    val=val+"3"
    data.set(val)


def btn_14_clicked():
    global val
    val=val+"0"
    data.set(val)

#"+"-"*"/"="C" Btns

def plus_clicked ():
    global A
    global operator
    global val
    A = int(val)
    operator="+"
    val= val+"+"
    data.set(val)

def minus_clicked ():
    global A
    global operator
    global val
    A = int(val)
    operator="-"
    val= val+"-"
    data.set(val)

def gun_clicked ():
    global A
    global operator
    global val
    A = int(val)
    operator="x"
    val= val+"x"
    data.set(val)


def bhag_clicked ():
    global A
    global operator
    global val
    A = int(val)
    operator="/"
    val= val+"/"
    data.set(val)

def C_clicked():
    global A
    global operator
    global val
    val= ""
    A= 0
    operator=""
    data.set(val)


def equal_clicked():
    global A
    global val
    global operator
    val2= val
    if operator== "+":
        store=int((val2.split("+")[1]))
        calculet= A + store
        data.set(calculet)
        val= str(calculet)
    elif operator== "-":
        store=int((val2.split("-")[1]))
        calculet= A - store
        data.set(calculet)
        val= str(calculet)
    elif operator== "x":
        store=int((val2.split("x")[1]))
        calculet= A * store
        data.set(calculet)
        val= str(calculet)
    elif operator== "/":
        store=int((val2.split("/")[1]))
        if store==0 :
            messagebox.showerror("Error","Can't divide by Zero")
            A = 0
            val=""
            data.set(val)
        else:
            calculet = int(A / store)
            data.set(calculet)
            val = str(calculet)



#about_the_window

root = tkinter.Tk()
root.geometry("350x500+300+300")
root.resizable(0, 0)
root.title("Ibus CAL")
data= StringVar()


#display_of_my_calculator
lbl= Label(
    root, text="Your input", font=("Arial Rounded MT", 35),
    anchor=SE,
    textvariable= data,
)
lbl.pack(expand=True, fill="both",)

# 1st Row & Buttons

btnrow01 = Frame(root, bg="#D9D7D7")
btnrow01.pack(expand=True, fill="both")

btn01 = Button(
    btnrow01,
    text="7",
    font=("calibri", 25), bg="#D9D7D7",
    relief = GROOVE,
    border=0,
    command= btn_1_clicked,
)
btn01.pack(side=LEFT, expand=True, fill="both")

btn02 = Button(
    btnrow01,
    text="8",
    font=("Arial Rounded MT", 25), bg="#D9D7D7",
    relief = GROOVE,
    border=0,
    command=btn_2_clicked,
)
btn02.pack(side=LEFT, expand=True, fill="both")

btn03 = Button(
    btnrow01,
    text="9",
    font=("Arial Rounded MT", 25), bg="#D9D7D7",
relief = GROOVE,
    border=0,
    command=btn_3_clicked,
)
btn03.pack(side=LEFT, expand=True, fill="both")

#"+"btn
btn04 = Button(
    btnrow01,
    text="+",
    font=("Arial Rounded MT", 25), bg="#D9D7D7",relief = GROOVE,
    border=0,
    fg="#F2522E",
    command=plus_clicked,
)
btn04.pack(side=LEFT, expand=True, fill="both")

# 2nd Row & Buttons

btnrow02 = Frame(root, bg="#D9D7D7")
btnrow02.pack(expand=True, fill="both")

btn05 = Button(
    btnrow02,
    text="4",
    font=("Arial Rounded MT", 25), bg="#D9D7D7",relief = GROOVE,
    border=0,
    command=btn_5_clicked,
)
btn05.pack(side=LEFT, expand=True, fill="both")


btn06 = Button(
    btnrow02,
    text="5",
    font=("Arial Rounded MT", 25), bg="#D9D7D7",
relief = GROOVE,
    border=0,
    command=btn_6_clicked,
)
btn06.pack(side=LEFT, expand=True, fill="both")

btn07 = Button(
    btnrow02,
    text="6",
    font=("Arial Rounded MT", 25), bg="#D9D7D7",
relief = GROOVE,
    border=0,
    command=btn_7_clicked,
)
btn07.pack(side=LEFT, expand=True, fill="both")

#"-"btn
btn08 = Button(
    btnrow02,
    text="-",
    font=("calibri", 25), bg="#D9D7D7",
relief = GROOVE,
    border=0,
    fg="#F2522E",
    command=minus_clicked
)
btn08.pack(side=LEFT, expand=True, fill="both")


# 3rd Row & Buttons

btnrow03 = Frame(root)
btnrow03.pack(expand=True, fill="both")

btn09 = Button(
    btnrow03,
    text="1",
    font=("Arial Rounded MT", 25), bg="#D9D7D7",
    relief = GROOVE,
    border=0,
    command=btn_9_clicked,
)
btn09.pack(side=LEFT, expand=True, fill="both")


btn10 = Button(
    btnrow03,
    text="2",
    font=("Arial Rounded MT", 25), bg="#D9D7D7",
    relief = GROOVE,
    border=0,
    command=btn_10_clicked,
)
btn10.pack(side=LEFT, expand=True, fill="both")


btn11 = Button (
    btnrow03,
    text="3",
    font=("Arial Rounded MT", 25), bg="#D9D7D7",
    relief = GROOVE,
    border=0,
    command=btn_11_clicked,
)
btn11.pack(side=LEFT, expand=True, fill="both")

#"*"btn
btn12 = Button(
    btnrow03,
    text="x",
    font=("Arial Rounded MT", 25), bg="#D9D7D7",
    relief = GROOVE,
    border=0,
    fg="#F2522E",
    command= gun_clicked,
)
btn12.pack(side=LEFT, expand=True, fill="both" )





# 4th Row & Buttons
btnrow04 = Frame(root, bg="#494859")
btnrow04.pack(expand=True, fill="both")

#"C" btn
btn13 = Button(
    btnrow04,
    text="C",
    font=("Arial Rounded MT", 25), bg="#D9D7D7",
    relief = GROOVE,
    border=0,
    fg="#F2522E",
    command=C_clicked,
)
btn13.pack(side=LEFT, expand=True, fill="both" )

btn14 = Button(
    btnrow04,
    text="0",
    font=("Arial Rounded MT", 25), bg="#D9D7D7",
    relief = GROOVE,
    border=0,
    command=btn_14_clicked,
)
btn14.pack(side=LEFT, expand=True, fill="both" )

#"="btn
btn15 = Button(
    btnrow04,
    text="=",
    font=("Arial Rounded MT", 25), bg="#D9D7D7",
    relief = GROOVE,
    border=0,
    fg="#F2522E",
    command= equal_clicked,
)
btn15.pack(side=LEFT, expand=True, fill="both" )

#"/"btn
btn16= Button(
    btnrow04,
    text="/",
    font=("Arial Rounded MT", 25), bg="#D9D7D7",
    relief = GROOVE,
    border=0,
    fg="#F2522E",
    command= bhag_clicked
)
btn16.pack(side=LEFT, expand=True, fill="both" )





root.mainloop()

