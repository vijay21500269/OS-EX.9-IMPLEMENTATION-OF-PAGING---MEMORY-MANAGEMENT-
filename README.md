# OS-EX.9-IMPLEMENTATION-OF-PAGING---MEMORY-MANAGEMENT-

# AIM

To write a C program to implement Page Replacement technique using FIFO.

# ALGORITHM

1. Start the program.
  
2. Get the number of pages and their sequence from the user

3. Get the number of available page frames from the user.

4. In FIFO, on the basics of first in first out, replace the pages respectively, then find number of page faults occurred.

5. Compare all frames with incoming page-

6. If the incoming page is already available in page frame, set the match flag to indicate ‘no need of page replacement’.

7. If the incoming page is not available in all frames, then remove the page which is loaded into the memory long back and give space for new incoming page.

8. Increment the ‘number of Page faults counter

9. Print the number of page faults.

10. Stop the program.

# PROGRAM
```
def main():
    n = int(input("ENTER THE NUMBER OF PAGES:\n"))
    a = list(map(int, input("ENTER THE PAGE NUMBER:\n").split()))
    no = int(input("ENTER THE NUMBER OF FRAMES: "))

    frame = [-1] * no
    j = 0
    count = 0

    print("\tRef string\t Page Frames")
    for i in range(n):
        print(f"{a[i]}\t\t\t", end='')
        avail = 0
        for k in range(no):
            if frame[k] == a[i]:
                avail = 1

        if avail == 0:
            frame[j] = a[i]
            j = (j + 1) % no
            count += 1
            for k in range(no):
                print(f"{frame[k]}\t", end='')

        print()

    print("\nPage Fault Is", count)

if __name__ == "__main__":
    main()

```

# OUTPUT

![image](1.png)

# RESULT

Thus the implementation of FIFO page replacement is successfully executed.
