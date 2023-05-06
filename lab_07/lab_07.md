# Lab 7
* ## ThingSpeak
    * ### Create new channel cpu_loop with field1 cpu_pc and field2 mem_avail_mb
    ![](/lab_07/new%20channel.PNG)
    * ### thingspeak_cpu_loop.py
    ```py
    senku@Senku:/mnt/c/codes/design 6/iot/lesson7$ cat thingspeak_cpu_loop.py 
    import http.client, urllib.request, urllib.parse, urllib.error
    from time import localtime, strftime
    import psutil
    import time
    def doit():
            cpu_pc = psutil.cpu_percent()
            mem = psutil.virtual_memory()
            mem_avail_mb = mem.available/(1024*1024)
            params = urllib.parse.urlencode({'field1': cpu_pc, 'field2':
                mem_avail_mb,'key':'YOURKEYHERE'})
            headers = {"Content-type":
                "application/x-www-form-urlencoded","Accept": "text/plain"}       
            conn = http.client.HTTPConnection("api.thingspeak.com:80")
            try:
                    conn.request("POST", "/update", params, headers)
                    response = conn.getresponse()
                    print(cpu_pc)
                    print(mem_avail_mb)
                    print(strftime("%a, %d %b %Y %H:%M:%S", localtime()))
                    print(response.status, response.reason)
                    data = response.read()
                    conn.close()
            except:
                    print("connection failed")
    #sleep for 60 seconds (message update interval limit of 15 seconds)
    if __name__ == "__main__":
            while True:
                    doit()
                    time.sleep(60)
    ```
    * ### thingspeak_feed.py
    ```py
    senku@Senku:/mnt/c/codes/design 6/iot/lesson7$ cat thingspeak_feed.py 
    import http.client, urllib.request, urllib.parse, urllib.error
    from time import localtime, strftime
    import psutil
    import time
    """
    2020-11-26: Pridhvi Myneni added lines 13-18, 25, and 43-54
    1. gitignore (https://git-scm.com/docs/gitignore) now prevents students from pushing up credentials.
    2. This program now attempts to cache the API key, but always prompts the user for their preference prior to saving credentials locally.
    3. Pickle data type used to store credentials. Pickle is a binary storage version of JSON. Please note not-human-readable does not mean secure.
    4. Removed key storage in source, which is generally a bad practice, as it leads 
    to version control systems having your key.
    5. Key for storage in a dictionary. This could be expanded in the future if other information needs to be similarly stored.
    """
    from pickle import dump as pickle_dump
    from pickle import load as pickle_load
    from os.path import exists as file_exists
    from os.path import isfile as is_file
    PICKLE_FILE_NAME = "API_KEY.pickle"
    API_KEY_INDEX = "API_KEY"
    def doit():
            cpu_pc = psutil.cpu_percent()
            mem = psutil.virtual_memory()
            mem_avail_mb = mem.available/(1024*1024)
            params = urllib.parse.urlencode({'field1': cpu_pc, 'field2':
    #             mem_avail_mb,'key':'YOURKEYHERE'})
                mem_avail_mb,'key':KEY})
            headers = {"Content-type":
                "application/x-www-form-urlencoded","Accept": "text/plain"}       
            conn = http.client.HTTPConnection("api.thingspeak.com:80")
            try:
                    conn.request("POST", "/update", params, headers)
                    response = conn.getresponse()
                    print(cpu_pc)
                    print(mem_avail_mb)
                    print(strftime("%a, %d %b %Y %H:%M:%S", localtime()))
                    print(response.status, response.reason)
                    data = response.read()
                    conn.close()
            except:
                    print("connection failed")
    #sleep for 60 seconds (message update interval limit of 15 seconds)
    if __name__ == "__main__":
    #caching the Write Key for the ThingSpeak API
            if file_exists(PICKLE_FILE_NAME) and is_file(PICKLE_FILE_NAME):
                    save_file = None
                    with open(PICKLE_FILE_NAME, 'rb') as f:
                            save_file = pickle_load(f)
                    KEY = save_file[API_KEY_INDEX]
            else:
                    key = input("An API key savefile was not found. Enter Write API Key >>> ")
                    should_save = input("Should we save this key for future use? [y/N] >>> ")
                    KEY = key.strip()
                    if len(should_save)>0 and should_save.lower().startswith("y"):   
                            with open(PICKLE_FILE_NAME, 'wb') as f:
                                    pickle_dump({API_KEY_INDEX: KEY}, f)
            while True:
                    doit()
                    time.sleep(60)
    ```
    * # thingspeak_feed.py result
    ```sh
    senku@Senku:/mnt/c/codes/design 6/iot/lesson7$ python3 thingspeak_feed.py
    An API key savefile was not found. Enter Write API Key >>> **********
    Should we save this key for future use? [y/N] >>> y
    5.7
    8895.48046875
    Sat, 06 May 2023 08:28:04
    200 OK
    3.9
    9004.08984375
    Sat, 06 May 2023 08:29:04
    200 OK
    1.0
    9003.42578125
    Sat, 06 May 2023 08:30:05
    200 OK
    0.6
    9019.90625
    Sat, 06 May 2023 08:31:05
    200 OK
    0.7
    9016.25390625
    Sat, 06 May 2023 08:32:05
    200 OK
    0.7
    8984.0703125
    Sat, 06 May 2023 08:33:05
    200 OK
    1.4
    8997.31640625
    Sat, 06 May 2023 08:34:05
    200 OK
    0.6
    9005.9609375
    Sat, 06 May 2023 08:35:05
    200 OK
    0.9
    9021.0859375
    Sat, 06 May 2023 08:36:05
    200 OK
    1.0
    9044.48046875
    Sat, 06 May 2023 08:37:05
    200 OK
    3.9
    9369.41796875
    Sat, 06 May 2023 08:38:05
    200 OK
    0.8
    9370.4375
    Sat, 06 May 2023 08:39:05
    200 OK
    1.1
    9363.8203125
    Sat, 06 May 2023 08:40:06
    200 OK
    0.6
    9350.296875
    Sat, 06 May 2023 08:41:06
    200 OK
    0.8
    9347.3515625
    Sat, 06 May 2023 08:42:06
    200 OK
    0.6
    9342.98828125
    Sat, 06 May 2023 08:43:06
    200 OK
    0.6
    9369.53125
    Sat, 06 May 2023 08:44:06
    200 OK
    0.6
    9326.40234375
    Sat, 06 May 2023 08:45:06
    200 OK
    0.5
    9320.33984375
    Sat, 06 May 2023 08:46:06
    200 OK
    0.7
    9341.7421875
    Sat, 06 May 2023 08:47:06
    200 OK
    0.7
    9333.60546875
    Sat, 06 May 2023 08:48:06
    200 OK
    1.2
    9287.97265625
    Sat, 06 May 2023 08:49:06
    200 OK
    0.5
    9334.15625
    Sat, 06 May 2023 08:50:06
    200 OK
    0.7
    9319.1015625
    Sat, 06 May 2023 08:51:07
    200 OK
    0.6
    9326.3203125
    Sat, 06 May 2023 08:52:07
    200 OK
    0.8
    9378.70703125
    Sat, 06 May 2023 08:53:08
    200 OK
    0.5
    9416.3359375
    Sat, 06 May 2023 08:54:08
    200 OK
    0.7
    9384.82421875
    Sat, 06 May 2023 08:55:08
    200 OK
    ```
    * ### thingspeak graph
    ![](/lab_07/thingspeak.PNG)
* ## Google Sheets
    * ### Sign up and log in the Google Cloud Platform Identity and Access Management (IAM)
    * ### Credential > Create Credentials > Create service account key > Service account > rpidata > JSON key type > Create > download rpidata-xxxxxxxxxxxx.json
    * ### Results 
    ![](/lab_07/cpudata.PNG)
