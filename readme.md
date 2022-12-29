# 221228
# 로잘린드 문제 풀이
# [rosalind website](https://rosalind.info/problems/list-view/)
### <br/><br/><br/>

## 1. Counting DNA Nucleotides
### https://rosalind.info/problems/dna/
### A, C, G, T 개수 세는 문제
```
Sample Dataset
AGCTTTTCATTCTGACTGCAACGGGCAATATGTCTCTGTGTGGATTAAAAAAAGAGTGTCTGATAGCAGC
Sample Output
20 12 17 21
```
### 하나 풀어봤는데 다시 시도 시간은 왜 1분을 해놨을까...
### 주의사항 : 맞는데 답이 틀리길래 알고보니 dataset 이 매번 달라졌다.
#### ![image](https://user-images.githubusercontent.com/62974484/209701824-6f91ae94-9898-4217-9aab-dd8f47e74492.png)
#### ![image](https://user-images.githubusercontent.com/62974484/209701585-05002104-a6b6-47ad-83c6-478e1927b80d.png)
### <br/><br/><br/>

## 2. Transcribing DNA into RNA
### https://rosalind.info/problems/rna/
### T 를 U 로 치환하는 문제
```
Sample Dataset
GATGGAACTTGACTACGTAAATT
Sample Output
GAUGGAACUUGACUACGUAAAUU
```
### <br/><br/><br/>

## 3. Complementing a Strand of DNA
### https://rosalind.info/problems/revc/
### reverse complementary sequence 를 만드는 문제
#### A -> T, T -> A, G -> C, C -> G 로 바꾸고 문자열을 거꾸로 읽으면 된다.
```
Sample Dataset
AAAACCCGGT
Sample Output
ACCGGGTTTT
```
### <br/><br/><br/>

## 4. Rabbits and Recurrence Relations
### https://rosalind.info/problems/fib/
### 피보나치 수열을 예로 들고 있는데 사실 별로 관련이 없다. 오히려 피보나치 수열로 생각하면 헷갈리니 문제 자체를 보면 된다.
```
피보나치 수열(바로 뒤 숫자 2개 합)
1 1 2 3 5 8 13
```
### 문제 설명(규칙)
1. 처음에는 암수 토끼 1쌍으로 시작한다.
2. 토끼는 1달이 지나면 번식을 할 수 있다. k 암수 쌍 만큼 자식을 만든다.
   * 토끼가 죽지도 않아서... 문제가 쉽다.
4. 문제 : n 개월 후에 총 마리수는?
#### ![image](https://user-images.githubusercontent.com/62974484/209743309-5bf5b9bc-f070-4ad9-9dfc-4a98fc2b35d2.png)
### X 가 번식 불가능 쌍, O 가 번식 가능 쌍이다. k 가 3일 때 O 수 * 3 이 다음 달에 생성되는 자식 수다.
#### ![image](https://user-images.githubusercontent.com/62974484/209743754-a30a9a9b-a63c-495c-8abe-01683b338aca.png)
```
test
19

given month :  35
given reproduction pair :  2

result
11453246123
```
### <br/><br/><br/>

## 5. Computing GC Content
### https://rosalind.info/problems/gc/
### GC content 계산하는 문제이다. 가장 높은 거 하나만 쓰면 된다.
- GC content : ((G + C) / total) * 100
```
Sample Dataset
>Rosalind_6404
CCTGCGGAAGATCGGCACTAGAATAGCCAGAACCGTTTCTCTGAGGCTTCCGGCCTTCCC
TCCCACTAATAATTCTGAGG
>Rosalind_5959
CCATCGGTAGCGCATCCTTAGTCCAATTAAGTCCCTATCCAGGCGCTCCGCCGAAGGTCT
ATATCCATTTGTCAGCAGACACGC
>Rosalind_0808
CCACCCTCGTGGTATGGCTAGGCATTCAGGAACCGGAGAACGCTTCAGACCAGCCCGGAC
TGGGAACCTGCGGGCAGTAGGTGGAAT

Sample Output
Rosalind_0808
60.919540
```
### 테스트셋 결과
```
Rosalind_9247
51.35135135135135
Rosalind_0597
46.98646986469865
Rosalind_0085
49.69072164948454
Rosalind_2362
50.46189376443419
Rosalind_9567
51.4585764294049
Rosalind_9022
51.83299389002036
Rosalind_9718
49.73147153598281
Rosalind_2359
52.8554070473876
Rosalind_1541
48.567870485678704
Rosalind_4880
48.751357220412594

highest GC content
Rosalind_2359
52.8554070473876
```
### <br/><br/><br/>

## 6. Counting Point Mutations
### https://rosalind.info/problems/hamm/
### 같은 length 를 가진 2개 서열에서 다른 문자 찾기(변이 찾기)
```
Sample Dataset
GAGCCTACTAACGGGAT
CATCGTAATGACGGCCT

Sample Output
7
```
### <br/><br/><br/>

## 7. Mendel's First Law
### https://rosalind.info/problems/iprb/
### 멘델의 유전법칙을 따라 우성 호모 / 우성 헤테로 / 열성 호모가 각각 k, m, n 개 존재할 때 다음 세대에 우성이 될 확률
#### ![image](https://user-images.githubusercontent.com/62974484/209764074-25001619-f571-45c6-8267-c449d0bb2b44.png)
### 각 조합에서 다음 세대의 유전자형
#### ![image](https://user-images.githubusercontent.com/62974484/209842845-50a6c86f-b4e6-43a2-a0b3-bd60ce79dbe8.png)
#### ![image](https://user-images.githubusercontent.com/62974484/209841080-385bb3b8-d51b-4283-8f8b-1f3546979640.png)
### 우성 표현형이 될 확률
#### ![image](https://user-images.githubusercontent.com/62974484/209841115-7162d42c-d6de-42ea-90bd-35d685655e97.png)
### <br/>
### 계산식 일반화
```
k = 우성 호모
m = 우성 헤테로
n = 열성 호모
total : k + m + n

항상 1개를 선하면 total 은 1 줄어든 상태로 선택해야 한다.
-> 선택할 수 있는 경우의 수 : total * (total - 1)

* 곱하기 순서는 픽한 순서와 같다.
우성 표현형의 확률 : ( (k * (k - 1)) + (k * m) + (k * n) + (m * k) + (n * k)) + 3/4 * (m * (m - 1)) + 1/2 * ((m * n) + (n * m)) ) / (total * (total - 1)
= ( (k * (total + m + n - 1)) + (3/4 * m * (m - 1)) + (m * n) ) / (total * (total - 1))
```
### 계산식이 잘 적용된 것을 확인할 수 있다.
```
Sample Dataset
2 2 2

Sample Output
0.78333
```
#### ![image](https://user-images.githubusercontent.com/62974484/209842658-5e364b88-c155-4946-963f-009a5657015e.png)
### <br/><br/><br/>

## 8. Translating RNA into Protein
### https://rosalind.info/problems/prot/
### RNA 를 protein sequence 로 번역하는 문제
- start codon : AUG
- stop codon : UAA, UAG, UGA
### codon table
#### ![codon_table](https://user-images.githubusercontent.com/62974484/209847326-6ac41e97-0240-45d6-bc6a-5c7ecb2a76a6.png)
```
Sample Dataset
AUGGCCAUGGCGCCCAGAACUGAGAUCAAUAGUACCCGUAUUAACGGGUGA

Sample Output
MAMAPRTEINSTRING
```
### <br/><br/><br/>

## 9. Finding a Motif in DNA
### https://rosalind.info/problems/subs/
### 문자열 안에서 특정 motif (상대적으로 작은 문자열이다)을 찾는 문제
### 여기서는 sSeq\[position\] 을 +1 해줘야 한다.
```
Sample Dataset
GATATATGCATATACTT
ATAT

Sample Output
2 4 10
```
### <br/><br/><br/>

## 10. Consensus and Profile
### https://rosalind.info/problems/cons/
### 같은 포지션에 같은 문자가 몇 개 있는지 세는 문제
### 그리고 각 포지션에서 문자가 제일 많은 것을 선정하여 새로운 seq 을 만든다.
#### 주의사항
- A: 5 1 0 0 5 5 0 0 이거 쓸 때 : 꼭 붙여야 문제 정답 인정 ㅎㅎ
```
Sample Dataset
>Rosalind_1
ATCCAGCT
>Rosalind_2
GGGCAACT
>Rosalind_3
ATGGATCT
>Rosalind_4
AAGCAACC
>Rosalind_5
TTGGAACT
>Rosalind_6
ATGCCATT
>Rosalind_7
ATGGCACT

Sample Output
ATGCAACT
A: 5 1 0 0 5 5 0 0
C: 0 0 1 4 2 0 6 1
G: 1 1 6 3 0 1 0 0
T: 1 5 0 0 0 1 1 6
```
### <br/><br/><br/>

## 11. Mortal Fibonacci Rabbits
### https://rosalind.info/problems/fibd/
### 4. Rabbits and Recurrence Relations 문제에서 토끼가 몇 달 후에 죽는지 추가한 것이다.
- 리스트 인덱스로 태어난 month 를 구분한다.
- die_month + 태어난 month 를 더해 현재 month 와 같으면 죽는 것으로 한다.
- 문제에서는 죽는 달에 먼저 번식을 한 후 죽는다.
```
Sample Dataset
6 3

Sample Output
4
```
#### ![image](https://user-images.githubusercontent.com/62974484/209893532-29e48f52-1c97-4296-8cd7-8a67356b00bb.png)
### <br/><br/><br/>

