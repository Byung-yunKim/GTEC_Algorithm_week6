# GTEC_Algorithm_week6

```
class Node():
    def __init__(self):
        self.data = None
        self.link = None

node1 = Node()
node1.data = "청하"
node1.link = node1

node2 = Node()
node2.data = "미란"
node1.link = node2
node2.link = node1

node3 = Node()
node3.data = "린"
node2.link = node3
node3.link = node1

print(node1.data, end = ' ')
print(node1.link.data, end = ' ')
print(node1.link.link.data, end = ' ')
print(node1.link.link.link.data, end = ' ')
print(node1.link.link.link.link.data, end = ' ')

dataArray = ["수한무", "거북이", "두루미", "삼천갑자", "동방삭"]

node = Node()
node.data = dataArray[0]
head = node
node.link = head

current = node
for data in dataArray[1:]:
    node = Node()
    node.data = data
    
    current.link = node
    node.link = head
    current = node

print(head.data, end = ' ')
print(head.link.data, end = ' ')
print(head.link.link.data, end = ' ')
print(head.link.link.link.data, end = ' ')
print(head.link.link.link.link.data, end = ' ')

# 노드 삽입
# 첫 번째 위치에 노드 삽입
# 1. 새 노드 생성
# 2. 새노드.link = head 로
# 3. 마지막 노드 찾기 (while 노드.link != head)
# 4. 마지막 노드.link = 새노드
# 5. head = 새 노드

node = Node()
node.data = "김"
node.link = head    # head == "수한무"

last = head

while last.link != head:
    last = last.link

last.link = node
head = node

print(head.data, end = ' ')
print(head.link.data, end = ' ')
print(head.link.link.data, end = ' ')
print(head.link.link.link.data, end = ' ')
print(head.link.link.link.link.data, end = ' ')
print(head.link.link.link.link.link.data, end = ' ')
print(head.link.link.link.link.link.link.data, end = ' ')
print(head.link.link.link.link.link.link.link.data, end = ' ')

# 노드 삽입
# 중간 위치에 노드 삽입 (거북이를 찾아 자라를 추가) -> 두 번째 노드부터 삽입하는 로직
# 1. 거북이 찾기 (while current.link != head)
# 2. 거북이 찾으면 새 노드 생성 (if current.data == "거북이")
# 3. 새 노드에 자라 입력 (새 노드.link = current, pre.link = 새 노드.link)

pre = head
current = head

while current.link != head:
    pre = current
    current = current.link
    
    if current.data == "거북이":
        node = Node()
        node.data = "자라"
        node.link = current
        pre.link = node
        
        break

print(head.data, end = ' ')
print(head.link.data, end = ' ')
print(head.link.link.data, end = ' ')
print(head.link.link.link.data, end = ' ')
print(head.link.link.link.link.data, end = ' ')
print(head.link.link.link.link.link.data, end = ' ')
print(head.link.link.link.link.link.link.data, end = ' ')
print(head.link.link.link.link.link.link.link.data, end = ' ')
print(head.link.link.link.link.link.link.link.link.data, end = ' ')

# 노드 삭제
# 첫 번째 노드 삭제
# 1. 첫 번째 노드를 current로 지정 (current = head)
# 2. 다음 노드를 head를 지정 (head = head.link)
# 3. 마지막 노드 찾기 (while last.link != current)
# 4. current 노드 삭제

current = head
head = head.link
last = head

while last.link != current:
    last = last.link

last.link = head
del(current)

print(head.data, end = ' ')
print(head.link.data, end = ' ')
print(head.link.link.data, end = ' ')
print(head.link.link.link.data, end = ' ')
print(head.link.link.link.link.data, end = ' ')
print(head.link.link.link.link.link.data, end = ' ')
print(head.link.link.link.link.link.link.data, end = ' ')

# 노드 삭제
# 중간 위치 노드 삭제
# 1. 거북이 찾기
# 2. pre.link = current.link로 수정
# 3. current 노드 삭제
pre = head
current = head

while current.link != head:
    pre = current
    current = current.link
    
    if current.data == "거북이":
        pre.link = current.link
        del(current)
        
        break

print(head.data, end = ' ')
print(head.link.data, end = ' ')
print(head.link.link.data, end = ' ')
print(head.link.link.link.data, end = ' ')
print(head.link.link.link.link.data, end = ' ')
print(head.link.link.link.link.link.data, end = ' ')
```
