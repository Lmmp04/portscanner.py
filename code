#!/bin/python3

#This port scanner was made by Leo Platti and uploaded to github. It scans all 65535 ports on a target network. Because of the large number of ports it scans it may take awhile, so please be patient.

import sys
import socket
import time
from datetime import datetime

answer = input("Would you like to scan a target by ip address, or by url? (ip/url) : ").lower().strip()

if answer == "ip":
    targets_ip = input("Enter Your Targets IP Address : ").strip()
    time1 = datetime.now()
    print ("-"*75)
    print ("Beginning port scan at {}".format(time1))
    print ("Scanning for open ports, please be patient")
    print ("")
    try:
        for port in range(1,65535):
            new_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
            new_socket.settimeout(.5)
            outcome = new_socket.connect_ex((targets_ip,port))
            if outcome == 0:
                print ("Port {}: Open".format(port))
                new_socket.close()
               
            else:
                print ("Port {}: Closed".format(port))
                new_socket.close()
   
        time2 = datetime.now()
        time_total = time2 - time1
        print ("Scan completed in {}".format(time_total))
   
    except KeyboardInterrupt:
        print ("Scan Succesfully Cancelled")
   
    except:
        pass

if answer == "url":
    url_target = input("Please enter the URL of Your Target : ").strip()
    time1 = datetime.now()
    print ("-"*75)
    print ("Beginning port scan at {}".format(time1))
    print ("Scanning for open ports, please be patient")
    print ("")
    url_ip = socket.gethostbyname(url_target)
    try:
        for port in range(1,65535):
            new_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)       
            new_socket.settimeout(.5)
            outcome = new_socket.connect_ex((url_ip,port))
            if outcome == 0:
                print ("Port {}: is open".format(port))
                new_socket.close()
               
            else:
                print ("Port {}: is closed".format(port))
                new_socket.close()
               
        time2 = datetime.now()
        time_total = time2 - time1
        print ("Scan completed in {}".format(time_total))
   
    except KeyboardInterrupt:
        print ("Scan Successfully Cancelled")
       
    except socket.error:
        print ("Couldn't connect the socket")
       
    except:
        pass
