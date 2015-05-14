# diplom
import tkinter


def change_color(event):
    r = hex(red.get())[2:4]
    g = hex(green.get())[2:4]
    b = hex(blue.get())[2:4]
    if len(r) == 1:
        r = '0' + r
    if len(g) == 1:
        g = '0' + g
    if len(b) == 1:
        b = '0' + b
    color = '#' + r + g + b
    fr1.configure(bg=color)
    out_hex['text'] = color


root = tkinter.Tk()

fr1 = tkinter.Label(root, width=20, height=10, bg='white')
fr1.pack()
out_hex = tkinter.Label(root, width='44')
out_hex.pack()


red = tkinter.Scale(root,orient="horizontal",length=180,from_=0,to_=255,tickinterval=50,resolution=1)
red.pack()
green = tkinter.Scale(root,orient="horizontal",length=180,from_=0,to_=255,tickinterval=50,resolution=1)
green.pack()
blue = tkinter.Scale(root,orient="horizontal",length=180,from_=0,to_=255,tickinterval=50,resolution=1)
blue.pack()
but = tkinter.Button(root,text="Получить цвет и его код")
but.bind("<Button-1>",change_color)
but.pack()

root.mainloop()
