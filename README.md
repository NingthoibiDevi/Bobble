# Bobble
#part A
#Answer 1: B.19/59
#Answer 2: B.False Positive
#Ans 3: B
#Ans 4: D. θ0=0,θ1=0.5
#Ans 5: C. Statement 1 and Statement 4 are correct
#Ans 6: D. Statement 2 and Statement 3 are correct
#Ans 7: A.Statement 1 and statement 3 are correct
#Ans 8: D.Random Forest
#Ans 9: D. All the above
#Ans 10: C. Both A and B
#Ans 11: B.PCA -> normalize PCA output -> training
#Ans 12: D.All of the above
#Ans 13: B.Assumes that all the features in a dataset are independent
#Ans 14:B.Using too large a value of lambda can cause your hypothesis to overfit the data.
#Ans 15:C.Both A and B
#Ans 16.B. 2 and 3
#Ans 17:A.Choose k to be the smallest value so that at least 99% of the varinace is retained
#Ans 18:C.a=0.3 is an effective choice of learning rate
#Ans 19:D.And
#Ans 20:C. 8/10
#Ans 21:B. Image translation
#Ans 22:B.Median Filter
#Ans 23:B.LAB
#Ans 24:B.The process of modifying pixel intensity value of an image
#Ans 25:A.Zero

#PartB
#Ans 1: decrease
#Ans 2: non linear, regression,decrease
#Ans 3: classification
#Ans 4: testing, training
#Ans 5: 0 to +1

#PartC
#Question 1:
import nltk
from nltk.corpus import stopwords 
from nltk.tokenize import word_tokenize
from nltk.stem import PorterStemmer 
from nltk.tokenize import word_tokenize 
nltk.download('stopwords')
nltk.download('punkt')


a="Steve was born in Tokyo, Japan in 1950. He moved to London with his parents when hewas 5 years old. Steve started school there and his father began work at the hospital. His mother was a house wife and he had four brothers.He lived in England for 2 years then moved to Amman, Jordan where he lived there for 10 years. Steve then moved to Cyprus to study at the Mediterranean University.Unfortunately, he did not succeed and returned to Jordan. His parents were very unhappy so he decided to try in America.He applied to many colleges and universities in the States and finally got some acceptance offers from them. He chose Wichita State University in Kansas. His major was Bio-medical Engineering. He stayed there for bout six months and then he moved again to a very small town called Greensboro to study in a small college. "
b=a.lower()
print(b)

c = ""
p = '''!()-[]{};:'"\,<>./?@#$%^&*_~'''
for i in a:
   if i not in p:
       c=c+i
print(c)

def remove(a): 
    return a.replace(" ", "") 
print(remove(a)) 
sw = set(stopwords.words('english')) 
  
word_tokens = word_tokenize(a) 
  
filtered_sentence = [w for w in word_tokens if not w in sw] 
  
filtered_sentence = [] 
  
for w in word_tokens: 
    if w not in sw:
        filtered_sentence.append(w) 
  
print(word_tokens) 
print(filtered_sentence)
ps=PorterStemmer()
f= a.split()
for j in f: 
    print(w, " : ", ps.stem(w))

#Question 3
def setZeroes(matrix):
        is_col = False
        R = len(matrix)
        C = len(matrix[0])
        for i in range(R):
            if matrix[i][0] == 0:
                is_col = True
            for j in range(1, C):
                if matrix[i][j]  == 0:
                    matrix[0][j] = 0
                    matrix[i][0] = 0

        for i in range(1, R):
            for j in range(1, C):
                if not matrix[i][0] or not matrix[0][j]:
                    matrix[i][j] = 0


        if matrix[0][0] == 0:
            for j in range(C):
                matrix[0][j] = 0
        if is_col:
            for i in range(R):
                matrix[i][0] = 0
        print(matrix)
matrix = [[1,1,1,1],[1,0,1,1],[1,1,0,0],[0,0,0,1]]
setZeroes(matrix)
