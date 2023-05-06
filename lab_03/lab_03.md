# Lab 3 
* ## Install required Python packages such as jdcal, astral, and geopy
    * I do not like to install unnecessary packages on my computer, that is why I typically set up a virtual environment.
    ```sh
    senku@Senku:/mnt/c/codes/design 6/iot/lesson3$ python3 -m venv lab3
    senku@Senku:/mnt/c/codes/design 6/iot/lesson3$ source lab3/bin/activate
    (lab3) senku@Senku:/mnt/c/codes/design 6/iot/lesson3$ 
    (lab3) senku@Senku:/mnt/c/codes/design 6/iot/lesson3$ pip install jdcal
    (lab3) senku@Senku:/mnt/c/codes/design 6/iot/lesson3$ pip install astral
    (lab3) senku@Senku:/mnt/c/codes/design 6/iot/lesson3$ pip install geopy
    (lab3) senku@Senku:/mnt/c/codes/design 6/iot/lesson3$ pip install pytz
    (lab3) senku@Senku:/mnt/c/codes/design 6/iot/lesson3$ pip install psutil
    ```
* ## python3 julian.py
    ```sh
    Calendar Date: 2023-05-06
    Julian Date: 2460070.5
    Modified Julian Date: 60070.0
    ```
* ## python3 date_example.py
    ```sh
    Date: 2023-05-06
    Date: 05-06-23
    Day of Week: Saturday
    Month: May
    Year: 2023
    108 days after the first day of classes
    -2 days before the last day of classes
    ```
* ## python3 datetime_example.py
    ```sh
    2023-05-06 01:28:23.091797
    2023-05-06 01:28:23.092320
    2023-05-06 05:28:23.094207
    1683350903.0946455
    Sat May  6 01:28:23 2023
    2023-05-06 01:28:23.095531
    2023-05-06 05:28:23.095911
    ```
* ## python3 time_example.py
    ```sh
    Sat May  6 01:28:48 2023
    Sat May  6 01:28:58 2023
    Sat May  6 01:29:08 2023
    ```
* ## python3 sun.py 'New York'
    ```sh
    Information for New York/USA

    Timezone: US/Eastern
    Latitude: 40.72; Longitude: -74.00

    Dawn:    2023-05-06 05:18:16.183857-04:00
    Sunrise: 2023-05-06 05:48:59.949550-04:00
    Noon:    2023-05-06 12:52:41-04:00
    Sunset:  2023-05-06 19:56:54.495627-04:00
    Dusk:    2023-05-06 20:27:44.881020-04:00
    ```
* ## python3 moon.py
    ```sh
    2023-05-06 Moon Phase: 14
    2023-05-07 Moon Phase: 15
    2023-05-08 Moon Phase: 16
    2023-05-09 Moon Phase: 17
    2023-05-10 Moon Phase: 18
    2023-05-11 Moon Phase: 19
    2023-05-12 Moon Phase: 20
    2023-05-13 Moon Phase: 21
    2023-05-14 Moon Phase: 22
    2023-05-15 Moon Phase: 23
    2023-05-16 Moon Phase: 24
    2023-05-17 Moon Phase: 25
    2023-05-18 Moon Phase: 26
    2023-05-19 Moon Phase: 27
    2023-05-20 Moon Phase: 0
    2023-05-21 Moon Phase: 1
    2023-05-22 Moon Phase: 2
    2023-05-23 Moon Phase: 3
    2023-05-24 Moon Phase: 4
    2023-05-25 Moon Phase: 5
    2023-05-26 Moon Phase: 6
    2023-05-27 Moon Phase: 6
    2023-05-28 Moon Phase: 7
    2023-05-29 Moon Phase: 8
    2023-05-30 Moon Phase: 9
    2023-05-31 Moon Phase: 10
    2023-06-01 Moon Phase: 11
    2023-06-02 Moon Phase: 12
    2023-06-03 Moon Phase: 13
    2023-06-04 Moon Phase: 14
    ```
* ## python3 coordinates.py 'SC Williams Library'
    ```sh
    Library Parking, Williams Lake, Cariboo Regional District, British Columbia, Canada
    (52.130143399999994, -122.14187089155848)
    ```
* ## python3 address.py '40.74480675, -74.02532862031404'
    ```sh
    Samuel C. Williams Library, Field House Road, Hoboken, Hudson County, New Jersey, 07030, United States
    (40.74480675, -74.02532861159351)
    ```
* ## python3 cpu.py
    ```sh
    The number of physical cores =  4
    The number of logical CPUs =  8
    The utilization per second as a percentage for each CPU
    [0.0, 1.0, 1.0, 0.0, 1.0, 1.0, 1.0, 0.0]
    [5.0, 0.0, 0.0, 0.0, 0.0, 2.0, 4.0, 1.0]
    [0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0]
    [3.0, 0.0, 2.0, 0.0, 5.0, 5.1, 6.0, 3.0]
    [9.8, 3.0, 5.1, 0.0, 8.0, 0.0, 3.0, 0.0]
    [2.0, 0.0, 0.0, 4.0, 2.9, 2.0, 3.0, 2.0]
    [2.0, 1.0, 3.0, 0.0, 0.0, 0.0, 0.0, 2.0]
    [3.0, 2.0, 0.0, 0.0, 0.0, 1.0, 2.0, 0.0]
    [0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0]
    [2.1, 0.0, 2.0, 0.0, 2.0, 0.0, 0.0, 0.0]
    ```
* ## python3 battery.py
    ```sh
    sbattery(percent=100, secsleft=<BatteryTime.POWER_TIME_UNLIMITED: -2>, power_plugged=True)
    ```
* ## python3 documentstats.py document.txt
    ```sh
    Word Count: 1343
    Top Ten Words: [('our', 26), ('their', 20), ('has', 20), ('he', 19), ('them', 15), ('these', 13), ('have', 11), ('we', 11), ('us', 11), ('people', 10)]
    ```