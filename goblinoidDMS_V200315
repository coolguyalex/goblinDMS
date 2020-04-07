import os
import random
import textwrap
import time
import sys
import csv


####     store text file locations as variables ####

m_txt = "monsters.txt"
n_txt = "names.txt"
j_txt = "jobs.txt"
hl_txt = "hit_locations.txt"
pe_txt = "plant_effects.txt"
b_csv = "beasts.csv"

pf_txt = "plannedfeatures.txt"



#########################################################

#      Define functions


def welcome_selector():
	skip=""
	print("Goblinoid Dungeon Mastery System \n\n 0. short intro \n1. full intro\n")
	skip = input("> ")
	if skip == "0":
		welcome()
	else:
		grand_welcome()	
	pass

# slow printing function , does not print on new line #
def slow_print(blah):
	for l in blah:
		sys.stdout.write(l)
		sys.stdout.flush()
		time.sleep(.005)

# even slower printing function ...for drama #
def vslow_print(blah):
	for l in blah:
		sys.stdout.write(l)
		sys.stdout.flush()
		time.sleep(0.01)

# line reader. takes the table name and line as an argument #
def read_table(name, line):
	file_var= open("tables\\"+name)
	all_lines_var = file_var.readlines()
	item = all_lines_var[line - 1]
	return item 

# line counting function which looks in the tables directory. must include file extension #
def counter(file):
	file = "tables\\"+file
	count = 0
	with open(file, 'r') as f:
	    for line in f:
	        count += 1
	return	(str(count))

# count and name file use din the welcome screen
def count_and_name(file):
	vslow_print (counter(file))
	slow_print (" "+file[:-3]+"\n")
	time.sleep(0.1)



#  welcome screen with ASCII art  #
def grand_welcome():
    with open("tables\\banner.txt", 'r') as f:
        title = f.read()#.replace('\n', '')
        print(title)
    print("Created by Alexander Sousa 3/10/2020 \n\n")
    slow_print("the current directory is:" + cur_dir)
    print("")
    slow_print("and contains...")
    count_and_name(m_txt), count_and_name(n_txt),count_and_name(j_txt), count_and_name(pe_txt),  count_and_name(hl_txt),  count_and_name(b_csv) 
    print("\nPress 0 at any time to go back \n")
    slow_print("press ENTER to begin \n\n")
    input("> ")
    

#  welcome screen with standard text #
def welcome():
	slow_print("\n Welcome to the \n \n GOBLINOID DUNGEON MASTERING SYSTEM\n ")
	slow_print("\n Created by Alexander Sousa 3/10/2020\n ")
	slow_print("\n the current directory is: " + cur_dir + "and contains...\n\n UNSPECIFIED QUANTITY of entires\n\n")
	slow_print("press ENTER to begin")
	print("")
	input("> ")
	print("")
	pass


#  main menu  #
def main_menu():
	print("please select the relevant category by typing the corresponding number")
	print("1. Monsters")
	print("2. Names and Occupations ")
	print("3. Plants Effects")
	print("4. Hit Locations")
	print("5. beast (biome weighted)")
	print("98. Dungeons (planned functionality)")
	print("99. Planned Features")
	print("0. Quit")
	print("")
	selection = input("> ")
	return	selection


#  define biome weighting funtion  #
#this currenlty only applies to beasts
# it wieghts ouputs based on the relevant probabilties
#column 6: forest, 7:town, 8:water

def biome_weight(num):
	creatures=[]
	prob=[]
	num_b = int(num)+5

	f = open('tables\\beasts.csv')
	csv_f = csv.reader(f)
	for row in csv_f:
		creatures.append(row[0])
		prob.append(row[num_b])
	for i in range(0, len(prob)): 
	    prob[i] = int(prob[i]) 
	var = "1"
	while var !="0" :
		print(random.choices(creatures,	prob, k=1))
		var = input("")










####  Run the actual game ####

##################         TESTING GROUNDS         #####################










##################       END TESTING GROUNDS     #######################

#get current directory 
cur_dir = os.getcwd()

welcome_selector()

selection = main_menu()

cont = 1

while selection != "0":
	if selection == "1":
		cont = 1
		while cont !="0" :
			print(read_table(m_txt, random.randrange(695)))
			cont = input("> ")
		selection = main_menu()
	elif selection == "2":
		print("")
		print(read_table(n_txt, random.randrange(4945)).rstrip()+ " the " + read_table(j_txt, random.randrange(525)).rstrip())
		input("> ")
		selection = main_menu()
	elif selection == "3":
		print("")
		print(read_table(pe_txt, random.randrange(100)))
		print("")
		input("> ")
		selection = main_menu()
	elif selection == "4":
		print("")
		print(read_table(hl_txt, random.randrange(int(counter(hl_txt)))))
		print("")
		input("> ")
		selection = main_menu()
	elif selection == "5":
		print("please chose one of the following biomes: \n 1.forest \n 2. town \n 3. water")
		num = input("> ")
		biome_weight(num)
		selection = main_menu()
	elif selection == "98":
		print("")
		print("planned functionality")
		print("")
		input("> ")
		selection = main_menu()	
	elif selection == "99":
		print(read_table(pf_txt, 1))
		print("")
		input("> ")
		selection = main_menu()	
        
	else:
		print("")
		print("Invalid selection")
		print("")
		input("> ")
		selection = main_menu()
