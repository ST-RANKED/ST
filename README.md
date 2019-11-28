# author : @Exa21
# -*- coding: utf-8 -*-

import os
import sys
import fileinput
os.system("clear")

N = '\033[0m'
D = '\033[90m'
W = '\033[1;37m'
B = '\033[1;34m'
R = '\033[1;31m'
G = '\033[1;32m'
Y = '\033[1;33m'
C = '\033[1;36m'

ask = G + '[' + W + '?' + G + '] '
sukses = G + '[' + W + '√' + G + '] '
eror = R + '[' + W + '!' + R + ']'
wait = Y + '[' + W + "Wait" + Y + ']' + W

banner = """
{}━━━━━━━━━━━━━━━━━━━━━
{}Make by{} : {}@Exa21
{}Channel{} : {}@INSANEhacks
{}Channel{} : {}@SCGaminGCH
{}━━━━━━━━━━━━━━━━━━━━━
""".format(G,Y,W,B,Y,W,B,Y,W,B,G)
banner2 = """
   {}[{}1{}]{} [DEC]Darking      
   {}[{}2{}]{} [DEC]Simple
   
   
{}━━━━━━━━━━━━━━━━━━━━━
""".format(G,W,G,W,G,W,G,W,G)

print banner
print banner2

def darkingenc():
   try:
        sc = raw_input(ask + W + "Script " + G + "> " + W)
        f = open(sc,'r')
        filedata = f.read()
        f.close()
        
        newdata = filedata.replace("eval $@","echo $@")
        renameback = filedata.replace("echo $@","eval $@")

        f = open(sc,'w')
        f.write(newdata)
        f.close()
       
        print (wait + "Proccecing")
        
        os.system("touch Exa_Tools.sh")
        os.system("bash " + sc)
        os.system("clear")
        print "Waiting Save to File"
        os.system("bash " + sc + " > Exa_Tools.sh")
        os.rename("Exa_Tools.sh","[DEC_BY_EXA]" + sc)
        
        f = open(sc,'w')
        f.write(renameback)
        f.close()
        
        print (sukses + "Done Decrypted Check with File Manager")

   except KeyboardInterrupt:
       print (eror + " Stopped!")
   except IOError:
       print (eror + " File Not Found!")
       
def simpleenc():
   try:
       sc = raw_input(ask + W + "Script " + G + "> " + W)
       f = open(sc,'r')
       filedata = f.read()
       f.close()

       newdata = filedata.replace("eval","echo")
       renameback = filedata.replace("echo","eval")
       
       f = open(sc,'w')
       f.write(newdata)
       f.close()

       os.system("touch Exa_Proccecing.sh")
       os.system("bash " + sc)
       os.system("clear")
       print "Wait Save to File"
       os.system("bash " + sc + " > Exa_Proccecing.sh")
       
       f = open(sc,'w')
       f.write(renameback)
       f.close()
       
       os.rename("Exa_Proccecing.sh","[DEC_BY_EXA]" + sc)
       print (sukses + "Done Decrypt Check in File Manager")

   except KeyboardInterrupt:
       print (eror + " Stopped!")
   except IOError:
       print (eror + " File Not Found!")

exazacky = raw_input(W + "Choose" + G + " > ")
if exazacky == "1" or exazacky == "01":
   darkingenc()
elif exazacky == "2" or exazacky == "02":
   simpleenc()
else:
        print (eror + " Wrong input")
