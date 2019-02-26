import time
import requests

#Add URLs to check to this array
urls = [
	"https://www.example.com",
	"https://www.wikipedia.org",
	]

#Set number of seconds between checking URLs
sleep_time = 30
run = True

while run == True:
	#Reset error list on each run
	error_list = []
	#Loop through URLs and store any non 200 responses in error_list array
	for item in urls:
		r = requests.get(item)
		if r.status_code == 200:
			pass
		else:
			error_list.append([item,r.status_code])
	#Check if error list if empty
	if error_list == []:
		print("OK! All URLs returned a 200 status")
		print("Retrying in {} seconds".format(sleep_time))
	#Print http errors to console
	else:
		print("WARNING! Not all URLs returned 200 status")
		#print(error_list)
		for warning in error_list:
			print("{} returned a {} status".format(warning[0],warning[1]))
		print("Retrying in {} seconds".format(sleep_time))
	time.sleep(sleep_time)
