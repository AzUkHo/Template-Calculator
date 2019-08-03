# Template-Calculator
from tkinter import *
import math
import parser
import tkinter.messagebox

window = Tk()
window.title ("Calculatrice scientifique")
window.configure(background="powder blue")
window.geometry("480x566+0+0")
window.resizable (width=False, height=False)

calc = Frame (window)
calc.grid()

txtDisplay = Entry(calc, font=('arial',20,'bold'), bg="#825163", bd=30, width=28, justify=RIGHT)
txtDisplay.grid(row=0 ,column=0, columnspan=4, pady=1)
txtDisplay.insert(0,"0")

numberpad = "789456123"
i = 0
btn = []
for j in range(2,5):
    for k in range(3):
        btn.append(Button(calc, width=6, height=2,  font=('arial',20,'bold'), bg="#825163", bd=4, text =numberpad[i]))
        btn[i].grid(row =j, column =k, pady =1)

        i += 1
#================================================================================================#
btnClear = Button(calc, text=chr(67), width =6, height=2,font=('arial',20,'bold'),bd=4,
                  bg='#B82358').grid(row=1 ,column=0, pady=1)
btnAllClear = Button(calc, text=chr(67) + chr(69), width =6, height=2, font=('arial',20,'bold'),bd=4,
                  bg='#B82358').grid(row=1,column=1, pady=1)

btnRc = Button(calc, text="V", width =6, height=2,font=('arial',20,'bold'),bd=4,
                  bg='#B82358').grid(row=1 ,column=2, pady=1)
btnAdd = Button(calc, text="+" + "", width =6, height=2, font=('arial',20,'bold'),bd=4,
                  bg='#B82358').grid(row=1,column=3, pady=1)

btnSt = Button(calc, text="-", width =6, height=2, font=('arial',20,'bold'),bd=4,
                  bg='#B82358').grid(row=2,column=3, pady=1)

btnMp = Button(calc, text="x", width =6, height=2, font=('arial',20,'bold'),bd=4,
                  bg='#B82358').grid(row=3,column=3, pady=1)

btnDv = Button(calc, text=chr(247), width =6, height=2, font=('arial',20,'bold'),bd=4,
                  bg='#B82358').grid(row=4,column=3, pady=1)


btnZr = Button(calc, text="0" + "", width =6, height=2, font=('arial',20,'bold'),bd=4,
                  bg='#B82358').grid(row=5,column=0, pady=1)



btnPtn = Button(calc, text=".", width =6, height=2, font=('arial',20,'bold'),bd=4,
                  bg='#B82358').grid(row=5,column=1, pady=1)

btnMpl = Button(calc, text=chr(177), width =6, height=2, font=('arial',20,'bold'),bd=4,
                  bg='#B82358').grid(row=5,column=2, pady=1)

btnDv = Button(calc, text="=", width =6, height=2, font=('arial',20,'bold'),bd=4,
                  bg='#B82358').grid(row=5,column=3, pady=1)

#===============================================Scientifique calculatrice============================================ #
btnPi = Button(calc, text="Pi", width =6, height=2, font=('arial',20,'bold'),bd=4,
                  bg='#DB789B').grid(row=2,column=4, pady=1)

btn = Button(calc, text="cos", width =6, height=2, font=('arial',20,'bold'),bd=4,
                  bg='#DB789B').grid(row=2,column=5, pady=1)

btnTan = Button(calc, text="tan", width =6, height=2, font=('arial',20,'bold'),bd=4,
                  bg='#DB789B').grid(row=2,column=6, pady=1)

btnSin = Button(calc, text="sin", width =6, height=2, font=('arial',20,'bold'),bd=4,
                  bg='#DB789B').grid(row=2,column=7, pady=1)

# =================================================================================================================== #
btnPi = Button(calc, text="2pi", width =6, height=2, font=('arial',20,'bold'),bd=4,
                  bg='#DB789B').grid(row=1,column=4, pady=1)

btnCosh = Button(calc, text="cosh", width =6, height=2, font=('arial',20,'bold'),bd=4,
                  bg='#DB789B').grid(row=1,column=5, pady=1)

btnTan = Button(calc, text="tanh", width =6, height=2, font=('arial',20,'bold'),bd=4,
                  bg='#DB789B').grid(row=1,column=6, pady=1)

btnSin = Button(calc, text="sinh", width =6, height=2, font=('arial',20,'bold'),bd=4,
                  bg='#DB789B').grid(row=1,column=7, pady=1)
# =================================================================================================================== #
btnLog = Button(calc, text="Log", width =6, height=2, font=('arial',20,'bold'),bd=4,
                  bg='#DB789B').grid(row=3,column=4, pady=1)

btnExp = Button(calc, text="Exp", width =6, height=2, font=('arial',20,'bold'),bd=4,
                  bg='#DB789B').grid(row=3,column=5, pady=1)

btnMod = Button(calc, text="Mod", width =6, height=2, font=('arial',20,'bold'),bd=4,
                  bg='#DB789B').grid(row=3,column=6, pady=1)

btnE = Button(calc, text="e", width =6, height=2, font=('arial',20,'bold'),bd=4,
                  bg='#DB789B').grid(row=3,column=7, pady=1)
#=====================================================================================================================#

btnLog2 = Button(calc, text="Log2", width =6, height=2, font=('arial',20,'bold'),bd=4,
                  bg='#DB789B').grid(row=4,column=4, pady=1)

btnDeg = Button(calc, text="Deg", width =6, height=2, font=('arial',20,'bold'),bd=4,
                  bg='#DB789B').grid(row=4,column=5, pady=1)

btnACosh = Button(calc, text="Acosh", width =6, height=2, font=('arial',20,'bold'),bd=4,
                  bg='#DB789B').grid(row=4,column=6, pady=1)

btnaSinh = Button(calc, text="aSinh", width =6, height=2, font=('arial',20,'bold'),bd=4,
                  bg='#DB789B').grid(row=4,column=7, pady=1)
#=====================================================================================================================#
btnLog10 = Button(calc, text="Log10", width =6, height=2, font=('arial',20,'bold'),bd=4,
                  bg='#DB789B').grid(row=5,column=4, pady=1)

btnlog1P = Button(calc, text="Log1p", width =6, height=2, font=('arial',20,'bold'),bd=4,
                  bg='#DB789B').grid(row=5,column=5, pady=1)

btnEx = Button(calc, text="expm1", width =6, height=2, font=('arial',20,'bold'),bd=4,
                  bg='#DB789B').grid(row=5,column=6, pady=1)

btngamma = Button(calc, text="1gamma", width =6, height=2, font=('arial',20,'bold'),bd=4,
                  bg='#DB789B').grid(row=5,column=7, pady=1)

IblnDisplay =Label(calc, text="Calculatrice scientifique",font=('arial',20,'bold'), justify=CENTER)
IblnDisplay.grid(row=0,column=4,columnspan=4)




#=======================================Menu and fuction========================================= #

def iExit():
    iExit = tkinter.messagebox.askyesno("Calculatrice scientifique", "Voulez vous vraiment quittez cette apllication ?")
    if iExit > 0:
        window.destroy()
        return

def Scientifique():
    window.geometry("944x568+0+0")
    window.resizable(width=False, height=False)

def Stantard():
    window.geometry("480x566+0+0")
    window.resizable(width=False, height=False)



menubar = Menu(calc)

filemenu = Menu(menubar, tearoff =0)
menubar.add_cascade(label = "fichier", menu=filemenu)
filemenu.add_command(label = "Stantard", command = Stantard)
filemenu.add_command(label = "Scientifique", command = Scientifique)
filemenu.add_separator()
filemenu.add_command(label = "Quittez", command = iExit)

editmenu = Menu(menubar, tearoff =0)
menubar.add_cascade(label = "Ouvrir", menu=editmenu)
editmenu.add_command(label = "Coupez")
editmenu.add_command(label = "Copier")
editmenu.add_separator()
editmenu.add_command(label = "Coller")

helpmenu = Menu(menubar, tearoff =0)
menubar.add_cascade(label = "Aide", menu=helpmenu)
helpmenu.add_command(label = "Besoins d'aide")








window.configure(menu=menubar)
window.mainloop()

