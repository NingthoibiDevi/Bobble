# Bobble
#part A <br/>
#Answer 1: B.19/59 <br/>
#Answer 2: B.False Positive <br/>
#Ans 3: B <br/>
#Ans 4: D. θ0=0,θ1=0.5 <br/>
#Ans 5: C. Statement 1 and Statement 4 are correct <br/>
#Ans 6: D. Statement 2 and Statement 3 are correct <br/>
#Ans 7: A.Statement 1 and statement 3 are correct  <br/>
#Ans 8: D.Random Forest <br/>
#Ans 9: D. All the above <br/>
#Ans 10: C. Both A and B <br/>
#Ans 11: B.PCA -> normalize PCA output -> training <br/>
#Ans 12: D.All of the above <br/>
#Ans 13: B.Assumes that all the features in a dataset are independent <br/>
#Ans 14:B.Using too large a value of lambda can cause your hypothesis to overfit the data. <br/>
#Ans 15:C.Both A and B <br/>
#Ans 16.B. 2 and 3 <br/>
#Ans 17:A.Choose k to be the smallest value so that at least 99% of the varinace is retained <br/>
#Ans 18:C.a=0.3 is an effective choice of learning rate <br/>
#Ans 19:D.And <br/>
#Ans 20:C. 8/10 <br/>
#Ans 21:B. Image translation <br/>
#Ans 22:B.Median Filter <br/>
#Ans 23:B.LAB <br/>
#Ans 24:B.The process of modifying pixel intensity value of an image <br/>
#Ans 25:A.Zero <br/>

#PartB <br/>
#Ans 1: decrease <br/>
#Ans 2: non linear, regression,decrease <br/>
#Ans 3: classification <br/>
#Ans 4: testing, training <br/>
#Ans 5: 0 to +1 <br/>

#PartC <br/>
#Question 1: <br/>
import nltk <br/>
from nltk.corpus import stopwords <br/>
from nltk.tokenize import word_tokenize <br/>
from nltk.stem import PorterStemmer  <br/>
from nltk.tokenize import word_tokenize <br/>
nltk.download('stopwords') <br/>
nltk.download('punkt') <br/>


a="Steve was born in Tokyo, Japan in 1950. He moved to London with his parents when hewas 5 years old. Steve started school there and his father began work at the hospital. His mother was a house wife and he had four brothers.He lived in England for 2 years then moved to Amman, Jordan where he lived there for 10 years. Steve then moved to Cyprus to study at the Mediterranean University.Unfortunately, he did not succeed and returned to Jordan. His parents were very unhappy so he decided to try in America.He applied to many colleges and universities in the States and finally got some acceptance offers from them. He chose Wichita State University in Kansas. His major was Bio-medical Engineering. He stayed there for bout six months and then he moved again to a very small town called Greensboro to study in a small college. " <br/>
b=a.lower() <br/>
print(b) <br/>
 
c = "" <br/>
p = '''!()-[]{};:'"\,<>./?@#$%^&*_~''' <br/>
for i in a: <br/>
   if i not in p: <br/>
       c=c+i <br/>
print(c)<br/>

def remove(a): <br/> 
    return a.replace(" ", "") <br/>
print(remove(a)) <br/>
sw = set(stopwords.words('english')) <br/> 
  
word_tokens = word_tokenize(a) <br/>
  
filtered_sentence = [w for w in word_tokens if not w in sw] <br/>
  
filtered_sentence = [] <br/>
  
for w in word_tokens: <br/>
    if w not in sw: <br/>
        filtered_sentence.append(w) <br/>
  
print(word_tokens) <br/>
print(filtered_sentence) <br/>
ps=PorterStemmer() <br/>
f= a.split() <br/>
for j in f: <br/>
    print(w, " : ", ps.stem(w)) <br/>

#Question 3 <br/>

def setZeroes(matrix): <br/>
        is_col = False <br/>
        R = len(matrix) <br/>
        C = len(matrix[0]) <br/>
        for i in range(R): <br/>
            if matrix[i][0] == 0: <br/>
                is_col = True <br/>
            for j in range(1, C): <br/>
                if matrix[i][j]  == 0: <br/>
                    matrix[0][j] = 0 <br/>
                    matrix[i][0] = 0 <br/>
        for i in range(1, R): <br/>
            for j in range(1, C): <br/>
                if not matrix[i][0] or not matrix[0][j]: <br/>
                    matrix[i][j] = 0 <br/>
        if matrix[0][0] == 0: <br/>
            for j in range(C): <br/>
                matrix[0][j] = 0 <br/>
        if is_col: <br/>
            for i in range(R): <br/>
                matrix[i][0] = 0 <br/>
        print(matrix) <br/>
matrix = [[1,1,1,1],[1,0,1,1],[1,1,0,0],[0,0,0,1]] <br/>
setZeroes(matrix) <br/>
