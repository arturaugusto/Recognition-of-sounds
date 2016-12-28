# Recognition-of-sounds
This python-script performs the task of recognition sounds 
and run specific commands after detecting these sounds.

-------------------

Some technical details
----------------------

This script is based on the creation of sound fingerprint for
etalon .wav file.


(Etalon file is divided into parts.

Then in each part we are looking for frequency
which corresponds to the max amplitude of sound.)

We get a list of frequencies

(It will be store in the file: frequency_list_etalon )

When we run 

	python cts.py standart 


We run endless loop.

Each iteration of this loop does:

- create a short .wav file (0.5 sec),
- make sound fingerprint of this short file,
- make list of frequencies for it,
- save this data in in the general list,
- delete this short file.


(This loop is used for continuous listening microphone
and recording data, when the script is running)

So we get a list of which is constantly supplemented.

Then we compare etalon frequency list and general frequencies list.

When a match occurs lists (80%) - run a command (run firefox)

For details --see code.

-------------------

Usage
------
create etalon .wav file (script will recognize the sounds of this file and do the action (run firefox) ) 

	python cts.py etalon


Run script

	python cts.py standart

When the script is running, it waiting for the etalon sounds
to do the action (run firefox)



Requirements (Worked on my Linux Mint 17.3 Cinnamon 64-bit)
------------
python 2.7

	export LC_ALL=C
	sudo apt-get install python2.7-dev
	sudo apt-get install libblas-dev liblapack-dev libatlas-base-dev gfortran
	sudo apt-get install g++
	sudo apt-get install python-alsaaudio
	sudo apt-get install libfreetype6-dev	

	pip2 install pyalsaaudio
	pip2 install numpy
	sudo pip2 install scipy
	sudo pip2 install matplotlib

---------------------------------------------------
The script is based on ideas and parts of the code from this article:

http://habrahabr.ru/post/252937/

A short video, how this script works:

https://www.youtube.com/watch?v=hi8_oyXEssY&feature=youtu.be
