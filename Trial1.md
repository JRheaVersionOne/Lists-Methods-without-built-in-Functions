Lists-Methods-without-built-in-Functions
========================================

This code is not fully done but extra help and comments are welcome
#PYTHON 2.7
# Python 2.7: methods with list without built-in functions in python
#Justin Rhea
#11/14/2014


def swap(lists):

    for i in range(0, len(lists) - 1):
        if lists[i] > lists[i+1]:
            lists[i+1], lists[i] = lists[i], lists[i+1]
    return lists

#------------------------------------------------------------------

def sort(lists):

    if len(lists) != 0:
        less = lists[0]
        for i in range(0, len(lists)-1):
                if lists[i] > lists[i+1]:
                    swap(lists)
                elif less > lists[i]:
                    swap(lists)
    return lists
#---------------------------------------------------------------------

def find(lists, i):

    if i in range(0, len(lists)):
        return lists[i]
    else:
        return "error"
#-------------------------------------------------------------------

def is_ascending(lists):

    check = False
    less = lists[0]
    for i in range(0, len(lists)-1):
            if lists[i] < lists[i+1]:
                check = True
            elif less < lists[i]:
                check = True
            else:
                return False
    return check
#------------------------------------------------------------------
def count(lists):

    return len(lists)
#------------------------------------------------------------------
def maximum(lists):

    maxnum = lists[0]
    for i in range(0, len(lists)):
        if maxnum < lists[i]:
            maxnum = lists[i]
    return maxnum
#------------------------------------------------------------------
def mapping(lists, n):

    for i in range(0, len(lists)):
        lists[i] = lists[i] * n
    return lists
#-------------------------------------------------------------------
def filter1(seq, qual):

    newlist = []
    for i in range(0, len(seq)):
        if seq[i] > qual:
            newlist += [seq[i]]
    return newlist
#--------------------------------------------------------------
def equivalence(seq1, seq2):

    check = False
    if len(seq1) == len(seq2) and not(len(seq1) == 0 or len(seq2) == 0):
        for i in range(0, len(seq1)):
            for j in range(0, len(seq2)):
                if (seq1[i] == seq2[j]) and sort(seq1) == sort(seq2):
                    check = True
                else:
                    check = False
        return check
    elif len(seq1) == 0 and len(seq2) == 0:
        return True
    else:
        return False
#-------------------------------------------------------------
def prefix(seq1, seq2):

    check = False
    if len(seq1) >= len(seq2) and not(len(seq2) == 0):
        for i in range(0, (len(seq2))):
            if seq2[i] == seq1[i]:
                check = True
        return check
    elif len(seq2) == 0:
        return True
    else:
        return False
#---------------------------------------------------------------
#There is a flaw in the function
def subsequence(seq1, seq2):

    check = False
    if len(seq1) >= len(seq2) and not(len(seq2) == 0):
        sort(seq1)
        sort(seq2)
        for i in range(0, len(seq1)):
            for j in range(0, len(seq2)):
                if seq1[i] == seq2[j]:
                    check = True
                else:
                    check = False
        return check
    elif len(seq2) == 0:
        return True
    else:
        return False
    #----------------------------------------------
#This is still needs correction and reorganize for no built-in functions

def rotate(lists, n):

    #newlist = []
    #for i in range(0,n):
        #lists.insert(0, i)
        #lists[0] = lists[-1]
        #lists.pop()
        #newlist += [lists[i]]
    #return newlists

#-------------------------------------------------------------
mylist1 = [raw_input("Enter your lists of numbers here( seperate with ',' ): ")]
mylist2 = [raw_input("Enter your lists of numbers here( seperate with ',' ): ")]
#---------------------------------------------------------------
def conversion_str_2_int(lists):

    """ list -> list
    Converts a list of numbers in str format -> list of numbers in int
    """
    newlists = []
    for i in range(0, len(lists)):
        lists[i]= lists[i].split(',')
        newlists += lists[i]
        newlists = [int(i) for i in newlists]
    return newlists
    
mylist1 = conversion_str_2_int(mylist1)
mylist2 = conversion_str_2_int(mylist2)

#My testing results--------------------------------------------
#uncomment to use the methods
#---------------------------------------------------------------
#print is_ascending(mylist1)
#print sort(mylist1)
#print is_ascending(mylist1)
#print find(mylist1, 0)
#print count(mylist1)
#print maximum(mylist1)
#print mapping(mylist1, 3)
#print filter1(mylist1, 8)
#print rotate(mylist1, 2)
#print mylist1
#print mylist2
#print equivalence(mylist1, mylist2)
#print prefix(mylist1, mylist2)
#print subsequence(mylist1, mylist2)
