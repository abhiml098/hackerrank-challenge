class QueueUsingTwoStacks:
    def __init__(self):
        self.stack_in = []  
        self.stack_out = [] 

    def enqueue(self, value):
        self.stack_in.append(value)

    def dequeue(self):
        self._transfer()  
        if self.stack_out:
            self.stack_out.pop()

    def front(self):
        self._transfer()  
        if self.stack_out:
            return self.stack_out[-1]

    def _transfer(self):
        
        if not self.stack_out:
            while self.stack_in:
                self.stack_out.append(self.stack_in.pop())

def main():
    
    q = int(input().strip())
    queue = QueueUsingTwoStacks()

    for _ in range(q):
        query = input().strip().split()
        query_type = int(query[0])

        if query_type == 1:
            
            value = int(query[1])
            queue.enqueue(value)
        elif query_type == 2:
            
            queue.dequeue()
        elif query_type == 3:
            
            print(queue.front())


if __name__ == "__main__":
    main()
