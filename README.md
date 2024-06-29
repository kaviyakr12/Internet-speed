Internet Speed Test GUI
This project is a graphical user interface (GUI) application that measures and reports your internet connection speed, including download and upload speeds. It uses the speedtest-cli library and Tkinter for the GUI.

Features
Measure Download Speed: Determine the download speed of your internet connection.
Measure Upload Speed: Determine the upload speed of your internet connection.
User-Friendly Interface: Simple and intuitive interface to display results.
Prerequisites
Ensure you have Python installed on your system. This project uses the speedtest-cli library and Tkinter, which is included with Python.


pip install speedtest-cli
Usage
Save the Script: Save the provided script as speed_test_gui.py.

Run the Script: Execute the script using Python. Open a terminal or command prompt and run:


python speed_test_gui.py
Use the GUI: Click the "Check Speed" button in the GUI to measure and display the download and upload speeds.

Script Explanation
Importing Libraries
python
Copy code
from tkinter import *
import speedtest
tkinter: A standard Python interface to the Tk GUI toolkit.
speedtest: A library for testing internet bandwidth using speedtest.net.
Defining the Speed Test Function
python

def speedcheck():
    st = speedtest.Speedtest()
    st.get_servers()
    down = str(round(st.download() / (10**6), 3)) + " Mbps"
    up = str(round(st.upload() / (10**6), 3)) + " Mbps"
    lab_down.config(text=f"{down}")
    lab_up.config(text=f"{up}")
Initializes the Speedtest object.
Retrieves and measures the download and upload speeds.
Updates the GUI labels with the results.
Setting Up the GUI
python

sp = Tk()
sp.title("Internet Speed Test")
sp.geometry("500x650")
sp.config(bg="black")
Creates the main window for the application.
Sets the window title, size, and background color.
Adding Labels and Button
python

lab = Label(sp, text="Internet Speed Test", font=("Times New Roman", 30, "bold"), bg="black", fg="white")
lab.place(x=60, y=40, height=50, width=380)

lab = Label(sp, text="Download speed", font=("Times New Roman", 30, "bold"))
lab.place(x=60, y=130, height=50, width=380)

lab_down = Label(sp, text="00", font=("Times New Roman", 30, "bold"))
lab_down.place(x=60, y=200, height=50, width=380)

lab = Label(sp, text="Upload speed", font=("Times New Roman", 30, "bold"))
lab.place(x=60, y=290, height=50, width=380)

lab_up = Label(sp, text="00", font=("Times New Roman", 30, "bold"))
lab_up.place(x=60, y=360, height=50, width=380)

button = Button(sp, text="Check Speed", font=("Times New Roman", 30, "bold"), relief=RAISED, bg="red", command=speedcheck)
button.place(x=60, y=460, height=50, width=380)
Creates and places labels for the title, download speed, and upload speed.
Adds a button to trigger the speed test.
Running the Main Loop
python

sp.mainloop()
Starts the Tkinter main event loop to run the application.
Customization
Change Appearance: Modify the font, colors, and sizes of the labels and button.
