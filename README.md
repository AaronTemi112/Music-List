# Music-List
import sys

array = [("Jitt", "Diego Money", 551633), ("Hotline Bling", "Drake", 1129696507), ("Acne!", "Jaydes", 754445), ("One Up", "Central Cee", 12568924), ("Not Kool", "Duwap Kaine", 228152), ("Headlines", "Drake", 450109507), ("No Wahala", "1da Banton", 77715368), ("Make It Out", "Lil Durk", 12738651), ("Alligator Walk", "NBA Youngboy", 6897466), ("Phoenix", "KA$HDAMI", 1984677)]

print(array)


CHOICES = ["Add a Song" , "Delete a Song", "Print Songs", "Print Popular Songs", "Stop!"]



def AddSong(name, artist, streams):

    newItemInArray = (name, artist, streams)
    array.append(newItemInArray)
    print(array)

def RemoveSong(name):

    for item in array:
        if item[0] == name:
            array.remove(item)

def printSongs():

    for item in array:
        print(item[0], "x", item[1], "x", item[2])

def printSongsInput(streams):

    for item in array:
        if item[2] > streams:
            print(item[0], "x", item[1], "x", item[2])



decision = 0
while decision != 5:

    print()
    for index, item in enumerate(CHOICES):
        print(index + 1, "-", item)

    print()
    decision = input("Which option would you like... -")
    decision = int(decision)

    if decision <= 0 or decision >len(CHOICES):
        print("\n" + "Error in response" + "/n")

    if decision == 1:
            name = input("Name of the song... -")
            artist = input("Name of the artist... -")
            streams = input("Number of streams... -")
            streams = int(streams)
            AddSong(name, artist, streams)

    elif decision == 2:
            name = input("Name of the song... -")
            RemoveSong(name)
        
    elif decision == 3:
            printSongs()

    elif decision == 4:
            streams = input("Number of streams... -")
            streams = int(streams)
            printSongsInput(streams)

    elif decision == 5:
            sys.exit()
