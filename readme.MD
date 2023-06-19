When running old example, I get 

(venv) PS C:\Users\bhaja\dev\selenium_example> & c:/Users/bhaja/dev/selenium_example/venv/Scripts/python.exe c:/Users/bhaja/dev/selenium_example/crawler.py
c:\Users\bhaja\dev\selenium_example\crawler.py:18: DeprecationWarning: use options instead of chrome_options
  driver = webdriver.Chrome(chrome_options=options)

DevTools listening on ws://127.0.0.1:52910/devtools/browser/4eb3aaf9-5769-4873-9d8e-ec2b47bcdaec
Traceback (most recent call last):
  File "c:\Users\bhaja\dev\selenium_example\crawler.py", line 18, in <module>
    driver = webdriver.Chrome(chrome_options=options)
  File "C:\Users\bhaja\dev\selenium_example\venv\lib\site-packages\selenium\webdriver\chrome\webdriver.py", line 69, in __init__  
    super().__init__(DesiredCapabilities.CHROME['browserName'], "goog",
  File "C:\Users\bhaja\dev\selenium_example\venv\lib\site-packages\selenium\webdriver\chromium\webdriver.py", line 92, in __init__
    super().__init__(
  File "C:\Users\bhaja\dev\selenium_example\venv\lib\site-packages\selenium\webdriver\remote\webdriver.py", line 272, in __init__
    self.start_session(capabilities, browser_profile)
  File "C:\Users\bhaja\dev\selenium_example\venv\lib\site-packages\selenium\webdriver\remote\webdriver.py", line 364, in start_session
    response = self.execute(Command.NEW_SESSION, parameters)
  File "C:\Users\bhaja\dev\selenium_example\venv\lib\site-packages\selenium\webdriver\remote\webdriver.py", line 429, in execute
    self.error_handler.check_response(response)
  File "C:\Users\bhaja\dev\selenium_example\venv\lib\site-packages\selenium\webdriver\remote\errorhandler.py", line 243, in check_response
    raise exception_class(message, screen, stacktrace)
selenium.common.exceptions.SessionNotCreatedException: Message: session not created: This version of ChromeDriver only supports Chrome version 106
Current browser version is 114.0.5735.134 with binary path C:\Program Files\Google\Chrome\Application\chrome.exe


using this new project to fix the issue

To fix this checking https://medium.com/fusionqa/selenium-webdriver-error-sessionnotcreatederror-session-not-created-this-version-of-7b3a8acd7072

To install clrome driver checking https://sites.google.com/chromium.org/driver/?pli=1

since i have Version 114.0.5735.134 (Official Build) (64-bit)

I will download - ChromeDriver 114.0.5735.90 (closet version i see on webpage)
(as per instruction, chrome driver should be in the path)

Added chromedriver.exe to c:\bin


My python version is Python 3.11.3

-----installaing packages
venv) PS C:\Users\bhaja\dev\selenium_example2> pip install -r .\requirements.txt
Collecting bs4
  Using cached bs4-0.0.1.tar.gz (1.1 kB)
  Preparing metadata (setup.py) ... done
Collecting selenium
  Downloading selenium-4.10.0-py3-none-any.whl (6.7 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 6.7/6.7 MB 30.6 MB/s eta 0:00:00
Collecting beautifulsoup4
  Using cached beautifulsoup4-4.12.2-py3-none-any.whl (142 kB)
Collecting urllib3[socks]<3,>=1.26
  Downloading urllib3-2.0.3-py3-none-any.whl (123 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 123.6/123.6 kB ? eta 0:00:00
Collecting trio~=0.17
  Using cached trio-0.22.0-py3-none-any.whl (384 kB)
Collecting trio-websocket~=0.9
  Downloading trio_websocket-0.10.3-py3-none-any.whl (17 kB)
Collecting certifi>=2021.10.8
  Downloading certifi-2023.5.7-py3-none-any.whl (156 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 157.0/157.0 kB ? eta 0:00:00
Collecting attrs>=19.2.0
  Using cached attrs-23.1.0-py3-none-any.whl (61 kB)
Collecting sortedcontainers
  Using cached sortedcontainers-2.4.0-py2.py3-none-any.whl (29 kB)
Collecting async-generator>=1.9
  Using cached async_generator-1.10-py3-none-any.whl (18 kB)
Collecting idna
  Using cached idna-3.4-py3-none-any.whl (61 kB)
Collecting outcome
  Using cached outcome-1.2.0-py2.py3-none-any.whl (9.7 kB)
Collecting sniffio
  Using cached sniffio-1.3.0-py3-none-any.whl (10 kB)
Collecting cffi>=1.14
  Using cached cffi-1.15.1-cp311-cp311-win_amd64.whl (179 kB)
Collecting exceptiongroup
  Downloading exceptiongroup-1.1.1-py3-none-any.whl (14 kB)
Collecting wsproto>=0.14
  Using cached wsproto-1.2.0-py3-none-any.whl (24 kB)
Collecting pysocks!=1.5.7,<2.0,>=1.5.6
  Using cached PySocks-1.7.1-py3-none-any.whl (16 kB)
  Using cached soupsieve-2.4.1-py3-none-any.whl (36 kB)
Collecting pycparser
  Using cached pycparser-2.21-py2.py3-none-any.whl (118 kB)
Collecting h11<1,>=0.9.0
  Using cached h11-0.14.0-py3-none-any.whl (58 kB)
Installing collected packages: sortedcontainers, urllib3, soupsieve, sniffio, pysocks, pycparser, idna, h11, exceptiongroup, certifi, attrs, async-generator, wsproto, outcome, cffi, beautifulsoup4, trio, bs4, trio-websocket, selenium
  DEPRECATION: bs4 is being installed using the legacy 'setup.py install' method, because it does not have a 'pyproject.toml' and the 'wheel' package is not installed. pip 23.1 will enforce this behaviour change. A possible replacement is to enable the '--use-pep517' option. Discussion can be found at https://github.com/pypa/pip/issues/8559
  Running setup.py install for bs4 ... done
Successfully installed async-generator-1.10 attrs-23.1.0 beautifulsoup4-4.12.2 bs4-0.0.1 certifi-2023.5.7 cffi-1.15.1 exceptiongroup-1.1.1 h11-0.14.0 idna-3.4 outcome-1.2.0 pycparser-2.21 pysocks-1.7.1 selenium-4.10.0 sniffio-1.3.0 sortedcontainers-2.4.0 soupsieve-2.4.1 trio-0.22.0 trio-websocket-0.10.3 urllib3-2.0.3 wsproto-1.2.0

[notice] A new release of pip available: 22.3.1 -> 23.1.2
[notice] To update, run: python.exe -m pip install --upgrade pip
(venv) PS C:\Users\bhaja\dev\selenium_example2> python .\crawler.py
Traceback (most recent call last):
  File "C:\Users\bhaja\dev\selenium_example2\crawler.py", line 7, in <module>
    import requests
ModuleNotFoundError: No module named 'requests'
(venv) PS C:\Users\bhaja\dev\selenium_example2> python .\crawler.py

(venv) PS C:\Users\bhaja\dev\selenium_example2> python.exe -m pip install --upgrade pip
Requirement already satisfied: pip in c:\users\bhaja\dev\selenium_example2\venv\lib\site-packages (22.3.1)
Collecting pip
  Using cached pip-23.1.2-py3-none-any.whl (2.1 MB)
Installing collected packages: pip
  Attempting uninstall: pip
    Found existing installation: pip 22.3.1
    Uninstalling pip-22.3.1:
      Successfully uninstalled pip-22.3.1
Successfully installed pip-23.1.2
(venv) PS C:\Users\bhaja\dev\selenium_example2> pip install -r .\requirements.txt      
Requirement already satisfied: bs4 in c:\users\bhaja\dev\selenium_example2\venv\lib\site-packages (from -r .\requirements.txt (line 1)) (0.0.1)
Requirement already satisfied: selenium in c:\users\bhaja\dev\selenium_example2\venv\lib\site-packages (from -r .\requirements.txt (line 2)) (4.10.0)
Collecting requests (from -r .\requirements.txt (line 3))
  Downloading requests-2.31.0-py3-none-any.whl (62 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 62.6/62.6 kB 3.5 MB/s eta 0:00:00
Requirement already satisfied: beautifulsoup4 in c:\users\bhaja\dev\selenium_example2\venv\lib\site-packages (from bs4->-r .\requirements.txt (line 1)) (4.12.2)Requirement already satisfied: urllib3[socks]<3,>=1.26 in c:\users\bhaja\dev\selenium_example2\venv\lib\site-packages (from selenium->-r .\requirements.txt (line 2)) (2.0.3)
Requirement already satisfied: trio~=0.17 in c:\users\bhaja\dev\selenium_example2\venv\lib\site-packages (from selenium->-r .\requirements.txt (line 2)) (0.22.0)
Requirement already satisfied: trio-websocket~=0.9 in c:\users\bhaja\dev\selenium_example2\venv\lib\site-packages (from selenium->-r .\requirements.txt (line 2)) (0.10.3)
Requirement already satisfied: certifi>=2021.10.8 in c:\users\bhaja\dev\selenium_example2\venv\lib\site-packages (from selenium->-r .\requirements.txt (line 2)) (2023.5.7)
Collecting charset-normalizer<4,>=2 (from requests->-r .\requirements.txt (line 3))
  Downloading charset_normalizer-3.1.0-cp311-cp311-win_amd64.whl (96 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 96.7/96.7 kB ? eta 0:00:00
Requirement already satisfied: idna<4,>=2.5 in c:\users\bhaja\dev\selenium_example2\venv\lib\site-packages (from requests->-r .\requirements.txt (line 3)) (3.4)Requirement already satisfied: attrs>=19.2.0 in c:\users\bhaja\dev\selenium_example2\venv\lib\site-packages (from trio~=0.17->selenium->-r .\requirements.txt (line 2)) (23.1.0)
Requirement already satisfied: sortedcontainers in c:\users\bhaja\dev\selenium_example2\venv\lib\site-packages (from trio~=0.17->selenium->-r .\requirements.txt (line 2)) (2.4.0)
Requirement already satisfied: async-generator>=1.9 in c:\users\bhaja\dev\selenium_example2\venv\lib\site-packages (from trio~=0.17->selenium->-r .\requirements.txt (line 2)) (1.10)
Requirement already satisfied: outcome in c:\users\bhaja\dev\selenium_example2\venv\lib\site-packages (from trio~=0.17->selenium->-r .\requirements.txt (line 2)) (1.2.0)
Requirement already satisfied: sniffio in c:\users\bhaja\dev\selenium_example2\venv\lib\site-packages (from trio~=0.17->selenium->-r .\requirements.txt (line 2)) (1.3.0)
Requirement already satisfied: cffi>=1.14 in c:\users\bhaja\dev\selenium_example2\venv\lib\site-packages (from trio~=0.17->selenium->-r .\requirements.txt (line 2)) (1.15.1)
Requirement already satisfied: exceptiongroup in c:\users\bhaja\dev\selenium_example2\venv\lib\site-packages (from trio-websocket~=0.9->selenium->-r .\requirements.txt (line 2)) (1.1.1)
Requirement already satisfied: wsproto>=0.14 in c:\users\bhaja\dev\selenium_example2\venv\lib\site-packages (from trio-websocket~=0.9->selenium->-r .\requirements.txt (line 2)) (1.2.0)
Requirement already satisfied: pysocks!=1.5.7,<2.0,>=1.5.6 in c:\users\bhaja\dev\selenium_example2\venv\lib\site-packages (from urllib3[socks]<3,>=1.26->selenium->-r .\requirements.txt (line 2)) (1.7.1)
Requirement already satisfied: soupsieve>1.2 in c:\users\bhaja\dev\selenium_example2\venv\lib\site-packages (from beautifulsoup4->bs4->-r .\requirements.txt (line 1)) (2.4.1)
Requirement already satisfied: pycparser in c:\users\bhaja\dev\selenium_example2\venv\lib\site-packages (from cffi>=1.14->trio~=0.17->selenium->-r .\requirements.txt (line 2)) (2.21)
Requirement already satisfied: h11<1,>=0.9.0 in c:\users\bhaja\dev\selenium_example2\venv\lib\site-packages (from wsproto>=0.14->trio-websocket~=0.9->selenium->-r .\requirements.txt (line 2)) (0.14.0)
Installing collected packages: charset-normalizer, requests
Successfully installed charset-normalizer-3.1.0 requests-2.31.0


-----------------

Was still gettiong errors. finally as per https://stackoverflow.com/questions/63421086/modulenotfounderror-no-module-named-webdriver-manager-error-even-after-instal

installed https://github.com/yeongbin-jo/python-chromedriver-autoinstaller and it worked



somehow it was not taking the chromedriver that i had downloaded to c:/bin

## This is what i finally did
* copied chrome chromedriver.exe from c:\bin to project dir C:\Users\bhaja\dev\selenium_example2
* ran this in console
---
    (venv) PS C:\Users\bhaja\dev\selenium_example2> python
    Python 3.11.3 (tags/v3.11.3:f3909b8, Apr  4 2023, 23:49:59) [MSC v.1934 64 bit (AMD64)] on win32
    Type "help", "copyright", "credits" or "license" for more information.
    >>> from selenium import webdriver
    >>> driver = webdriver.Chrome()
    DevTools listening on ws://127.0.0.1:57848/devtools/browser/17d557d8-80af-4ccc-b336-11f9eda5d324
    >>> driver.get("https://www.google.com") 
---
