import numpy as np

def arithmatic(a, b):
    print("\n Performing Arithmatic Operations ")
    print("Addition of both arrays:", np.add(a, b))
    print("Subtraction of both arrays:", np.subtract(a, b))
    print("Multiplication of both arrays:", np.multiply(a, b))
    print("Division of both arrays:", np.divide(a, b))
    print("Power operation between arrays:", np.power(a, b))

def statistics(a):
    print("\n Performing Statistical Analysis ")
    print("Mean of the array:", np.mean(a))
    print("Median of the array:", np.median(a))
    print("Standard deviation of the array:", np.std(a))
    print("Variance of the array:", np.var(a))
    print("Minimum value in the array:", np.min(a))
    print("Maximum value in the array:", np.max(a))
    print("Sum of all elements:", np.sum(a))
    print("Product of all elements:", np.prod(a))
    print("Shape of the array:", a.shape)
    print("Size of the array:", a.size)
    print("Data type of the array:", a.dtype)

def manipulation(a):
    print("\n Performing Array Manipulations ")
    print("Original array:", a)
    print("Shape:", a.shape, "| Total elements:", a.size)

    print("\n All Possible 2D Reshapes ")
    for i in range(1, a.size + 1):
        if a.size % i == 0:
            try:
                print(f"Reshaped to {i} x {a.size//i}:\n", a.reshape(i, a.size//i))
            except:
                pass

    
    print("\n All Possible 3D Reshapes ")
    for i in range(1, a.size + 1):
        for j in range(1, a.size + 1):
            if a.size % (i * j) == 0:
                try:
                    print(f"Reshaped to {i} x {j} x {a.size//(i*j)}:\n", a.reshape(i, j, a.size//(i*j)))
                except:
                    pass

    print("\nSorted array (ascending order):", np.sort(a))
    print("Sorted array (descending order):", np.sort(a)[::-1])

    print("Unique values in the array:", np.unique(a))

    print("First element of the array:", a[0])
    print("Last element of the array:", a[-1])

    print("Minimum element from the array:",np.min(a))
    print("Maximum element from the array:",np.max(a))

    mean_val = np.mean(a)
    print(f"\nMean value of the array: {mean_val}")
    print("Elements greater than the mean:", a[a > mean_val])

def main():
    print("=============================================================")
    print("\n NumPy Mathematical Calculator ")
    print("\n=============================================================")
    while True:
        print("\nSelect an option:")
        print("1. Perform Arithmatic Operations")
        print("2. Perform Statistical Analysis")
        print("3. Perform Array Manipulations")
        print("4. Exit the Program")
        print("\n=============================================================")

        try:
            choice = int(input("Enter your choice (1–4): "))
            if choice == 4:
                print("\n Exiting the program... \nThankyou For Using the Calculator \n Bye Byeeee......")
                break

            a = np.array(list(map(float, input("\nEnter the elements of the first array space-separated: ").split())))

            if choice == 1:
                b = np.array(list(map(float, input("Enter the elements of the second array space-separated: ").split())))
                arithmatic(a, b)
            elif choice == 2:
                statistics(a)
            elif choice == 3:
                manipulation(a)
            else:
                print("Please enter a valid option between 1 and 4.")
        except Exception as e:
            print("\nAn error occurred:", e)

main()

