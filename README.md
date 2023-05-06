# Engineering Design VI
Welcome to the GitHub repository for Engineering Design VI class! This repository is designed to be a central hub for all the code, documentation, and other resources related to the course labs.Whether you're a student, instructor, or just interested in the course content, you'll find everything you need here.
* ## [Lab 01: GHDL and GTKWave](/lab_01/lab_01.md)
    * Assignment
        * Go to the [GitHub repository](https://github.com/kevinwlu/dsd) of Digital System Design (DSD) 
            * Study VHDL and GHDL
        * Go to the [GHDL](https://github.com/kevinwlu/dsd/tree/master/ghdl) folder
            * Install GHDL and GTKWave
            * Run the Half Adder example
            * Run another example such as D Flip-Flop or 4-to-1 Multiplexer
            * Document the results on your GitHub repository
        * Exploration: [Icarus Verilog](https://en.wikipedia.org/wiki/Icarus_Verilog)

* ## [Lab 02: Basic Linux Terminal Commands](/lab_02/lab_02.md)
    * Assignment
        * Go to the IoT [repository](https://github.com/kevinwlu/iot)
        * Study Lessons 1 and 2
        * Open a terminal
            ```sh
            $ hostname
            $ env
            $ ps
            $ pwd
            $ git clone https://github.com/kevinwlu/iot.git
            $ cd iot
            $ ls
            $ cd
            $ df
            $ mkdir demo
            $ cd demo
            $ nano file
            $ cat file
            $ cp file file1
            $ mv file file2
            $ rm file2
            $ clear
            $ man uname
            $ uname -a
            $ ifconfig
            $ ping localhost
            $ netstat
            ```

* ## [Lab 03: Python Basics](/lab_03/lab_03.md)
    * Assignment
        * Study the GitHub repository Lesson 3 labs
        * Install required Python packages such as jdcal, astral, and geopy
        ```sh
        $ cd ~/iot
        $ cd *3
        $ python3 julian.py
        $ python3 date_example.py
        $ python3 datetime_example.py
        $ python3 time_example.py
        $ python3 sun.py 'New York'
        $ python3 moon.py
        $ python3 coordinates.py 'SC Williams Library'
        $ python3 address.py '40.74480675, -74.02532862031404'
        $ python3 cpu.py
        $ python3 battery.py
        $ python3 documentstats.py document.txt

        ```

* ## [Lab 04: Django and Flask](/lab_04/lab_04.md)
    * Assignment
        * Study the GitHub repository Lesson 4 labs
        * Install Django and Django REST framework
        * Use the default database, i.e., SQLite
        * Start Django project "stevens," run server, and view app 
        * Start Django REST project "mycpu," run server, and view app
        * Install Flask if no module named 'flask'
        * Run Flask server via hello_world.py and view app

* ## [Lab 05: Django and Flask](/lab_05/lab_05.md)
    * Assignment
        * Study the GitHub [repository](https://github.com/kevinwlu/iot) Lesson 5 labs
        * Install Paho-MQTT
        * Change directory to the iot repository
        * Update the repository with git pull
        * Change directory to Lesson 5
        * Run python3 subcpu.py on one Terminal
        * Run python3 pubcpu.py on another

* ## [Lab 06: Node.js and Pystache](/lab_06/lab_06.md)
    * Assignment
        * Study the GitHub [repository](https://github.com/kevinwlu/iot) Lesson 6
        * Install Node.js and run hello-world.js, hello.js, and http.js
        * Refresh the webpage to see server activities
        * Install Pystache and run say_hello.py that uses the template in say_hello.mustache

* ## [Lab 07: ThinkSpeak and Google Sheets](/lab_07/lab_07.md)
    * Assignment
        * Study the GitHub [repository](https://github.com/kevinwlu/iot) Lesson 7
        * Sign up and log in MathWorks ThingSpeak
        * Run thingspeak_cpu_loop.py or thinkspeak_feed.py in a demo folder
        * Install gspread and oauth2client
        * Log in the Google Cloud Platform Identity and Access Management, create a project cpudata, enable both Drive API and Sheets API, create and download service account JSON key file
        * Start a new Google sheet cpudata, share it with the client email in the JSON file, delete Rows 2 to 1000, and edit the header cells
        * Run cpu_spreadsheet.py with the JSON key file in a demo folder


* ## [Lab 08: Data Analysis](/lab_08/lab_08.md)
    * Assignemt 
        * Study the GitHub [repository](https://github.com/kevinwlu/iot) Lesson 8
        * Install Python packages
        * Save the Lab 7 Google sheet in CSV format to ~/demo
        * Copy ~/iot/lesson8/plt_final.py and plt_cv2.py to ~/demo
        * Edit plt_final.py and plt_cv2.py to read the CSV file with customized plot titles
        * Run plt_final.py and plt_cv2.py

* ## [Lab 09: PlantUML](/lab_09/lab_09.md)
    * Assignemt
        * Study the GitHub [repository](https://github.com/kevinwlu/iot) Lesson 9
        * Install pyang and PlantUML
        * copy ~/iot/lesson9/intrusiondetection.yang to ~/demo
        * Run pyang to generate intrusiondetection.yin and intrusiondetection.uml
        * Run PlantUML to generate intrusiondetection.png

* ## [Lab 10: Blockchain](/lab_10/lab_10.md)
    * Assignemt
        * Study the GitHub [repository](https://github.com/kevinwlu/iot) Lesson 10
        * Run hash_value.py twice and compare results
        * Run snakecoin.py
        * Run snakecoin-server-full-code.py on Terminal 1 and mine a new block on Terminal 2
        * Clone Python blockchain app and uncomment the last line of node_server.py
        * Run node_server.py on Terminal 1 and run_app.py on Terminal 2


