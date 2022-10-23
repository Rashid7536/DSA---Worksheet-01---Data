// Java program for implementation of Insertion Sort
import java.util.Random;

// Java program for implementation of Insertion Sort
public class InsertionSort {
	/*Function to sort array using insertion sort*/
    public static int[] add_element(int n, int myarray[], int ele) { 
         int i; 
 
         int newArray[] = new int[n + 1]; //Create a new array and add 
         //one more space to it
         for (i = 0; i < n; i++)
              newArray[i] = myarray[i]; //copy elements form old array
         //to new one
        newArray[n] = ele; //Copy the newest addition to the array
 
        return newArray; //return newArray
        
    } 
 
	void sort(int arr[])
	{
		int n = arr.length;
		for (int i = 1; i < n; ++i) {
			int key = arr[i];
			int j = i - 1;

			/* Move elements of arr[0..i-1], that are
			greater than key, to one position ahead
			of their current position */
			while (j >= 0 && arr[j] > key) {
				arr[j + 1] = arr[j];
				j = j - 1;
			}
			arr[j + 1] = key;
		}
	}

	/* A utility function to print array of size n*/
	static void printArray(int arr[])
	{
		int n = arr.length;
		for (int i = 0; i < n; ++i)
			System.out.print(arr[i] + " ");

		System.out.println();
	}

	// Driver method
	public static void main(String args[])
	{
                int array[] = {1,2}; //Create an array with 2 elements
                int e = 2; //Define a variable 'e'
                InsertionSort ob = new InsertionSort(); //This is for sorting
                Random r = new Random(); //To create Random values 
                
                for (int l=0;l<2000;l++){ //loop where the main function runs
                    long inTime = System.nanoTime(); //using System library
                    //take the system time at this point
                    int ele = r.nextInt(50000); //create random numbers, since it
                    //will create negative numbers, a bound has been created,
                    //which means it can generate numebrs form 0-50000 and equate to ele
                    //which will be sent to the function
                    //where elements will be added to the initial array
                    //int ele = e; //equate e to ele which will be sent to the functio
                    //where elements will be added to the initial array
                    array = add_element(l, array, ele);
                    //printArray(array);
                    int array2[] = array.clone(); //clone the array and copy to 
                    //the array2
                    ob.sort(array2); //sort the array2
                    e++; // increase the 'e' by 1
                    //printArray(array2);
                    long offTime = System.nanoTime(); // take the system time
                    //at this point
                    long totalTime = offTime - inTime; // calculate the time difference
                   
                    System.out.println(totalTime); //record the time to the output
                }  
                      

		//ob.sort(array);

		//printArray(array);
	}
}


/* This code is contributed by Rajat Mishra and Edited by Rashid Aman */




