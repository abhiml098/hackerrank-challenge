def twoStacks(maxSum, a, b):
    asum = 0
    acount = 0
    for i in range(len(a)):
        if asum+ a[i] > maxSum:
            break
        asum += a[i]
        acount += 1

    
    max_score = acount
    bsum = 0
    bcount = 0

    for i in range(len(b)):
        bsum += b[i]
        bcount += 1

        while asum + bsum > maxSum and acount > 0:
            acount -= 1
            asum -= a[acount]

        if asum + bsum <= maxSum:
            max_score = max(max_score, acount + bcount)

    return max_score
