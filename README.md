# 2017-data-science-training1
print ("This is Ali's work")
################################################
print ("Part 1 - basic list")
################################################
#A. match_ends
def match_ends(words):
    count = 0
    for word in words:
        if len(words) >= 2 and words[0] == words[-1]:
            count = count + 1
    return count

words = "yuenaliy" #exmaple to verify the answer
match_ends(words)
################################################
#B. front_x
def front_x(words):
    list_x = []
    list_nonx = []
    
    for word in words:
        if word.startswith('x'):
            list_x.append (word)
        else :
            list_nonx.append (word)
    return sorted (list_x) + sorted (list_nonx)

words = ['mix', 'xyz', 'apple', 'xanadu', 'aardvark']
front_x(words)        
################################################
#C. sort_last
def sort_last(tuple):
    return sorted(tuple, key=lambda num: num[-1])

tuple = [(1, 7), (1, 3), (3, 4, 5), (2, 2)] 

sort_last(tuple)
################################################
#D. remove_adjacent
def remove_adjacent(nums):
    list = []
    
    for num in nums:
        if len(list) ==0 or num != list[-1]: 
            list.append (num)       
    return list

nums = ([1, 2, 2, 3])
remove_adjacent (nums)
################################################
#E. linear_merge

def linear_merge(list1, list2):
    list1.extend(list2)
    return sorted(list1)
 
list1 = ([1, 2, 2, 3])
list2 = ([2, 4, 8])
linear_merge(list1, list2)
 
################################################
print ("Part 2 - basic string")
################################################
#A. donuts
def donuts(count):       
    return 'Number of donuts: {}'.format(count if count<10 else 'many')

print donuts(5)
print donuts(23)
################################################
#B. both_ends
def both_ends(s):
    if len(s) <2:
        return ''
    else:
        return s[0]+s[1]+s[-2]+s[-1]

both_ends('a')
#both_ends('spring')
################################################
#C. fix_start
def fix_start(s):
    stra = s[0]
    strb = s[1:]
    strc = strb.replace(s[0], "*")
    return stra+strc

fix_start('babbble')
################################################
#D. MixUp

def mix_up(a, b):
    newa = b[0:2]+a[2:]
    newb = a[0:2]+b[2:]
    
    return '{} {}'.format(newa,newb)

mix_up('mix', 'pod')
#mix_up('dog', 'dinner')
################################################
#D. verbing
def verbing(s):
    if len(s) >=3 and s[-3:] =='ing':
        return '{}ly'.format(s[:-3])
    elif len(s)>=3:
        return '{}ing'.format(s)
    else:
        return s

#verbing('study') #to check for 'ing'
#verbing('working') #to check for 'ly'
verbing('do') #to check for len <3
################################################
#E. not_bad
def not_bad(s):
    
    ch1 = s.find('not')
    ch2 = s.find('bad')
    if ch2 > ch1:
        s = s[0:ch1] + 'good' +s[ch2+3:]
    return s

not_bad('This dinner is not that bad, right?')
################################################
#F. front_back

def front_back(a, b): 
    if len(a)%2 == 0:
        afront = len(a)/2 
    else: afront =(len(a)+1)/2
    
    if len(b)%2 == 0:
        bfront = len(b)/2
    else: bfront = (len(b)+1)/2        
    
    return a[0:afront]+b[0:bfront]+a[afront:]+b[bfront:]
        
a = ('abcde')
b = ('fghi')
front_back(a, b)  
