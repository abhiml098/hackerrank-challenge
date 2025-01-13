def isBalanced(s):
    st = []
    
    
    for char in s:
        if char in "({[":
            
            st.append(char)
        elif char in ")}]":
            
            if not st:
                
                return "NO"
            top = st.pop()
            if (char == ')' and top != '(') or (char == '}' and top != '{') or (char == ']' and top != '['):
                
                return "NO"
    
    if not st:
        return "YES"
    else:
        return "NO"
