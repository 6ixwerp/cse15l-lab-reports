# Lab Report 2
**PART 1:**

This is the code for the StringServer web server... 
![Image](StringServerCode.png)

Here are screenshots of two instances where I had used the /add-message...
![Image](HelloSearchBar.png)
![Image](HowAreYouSearchBar.png)

For my code, the method that was called was the String handleRequest(URI url) which would come from the Handler class and handles the HTTP requests. The relevant argument to the method would be the "URI url" as it is a parameter that is supposed to be representative of the incoming HTTP requests, and the relevant field in my StringServer class would be the num and s. The num is representative of being a counter and the s is a string. The num and s would be changed based on specific requests through user input, for example when the address has an "/add-message" as well as contains an "s" parameter, then this would mean that the "num" gets incremented and the "s" is updated with the incremented number as well as the string after the "s=".

**PART 2:**

The bug I had chosen from the list given to me was under the Array examples where I needed to successfully reverse an array with all the elements in that order. 
My first step was to create a failure inducing input for the buggy program, as a JUnit test. 

    import static org.junit.Assert.assertArrayEquals;
    import org.junit.Test;

    public class reverseFail {

    @Test
    public void testReverseFail() {
        int[] input = {1, 2, 3, 4, 5};
        int[] expected = {5, 4, 3, 2, 1};
        int[] reversedArray = ReversedArray.reversed(input);
        assertArrayEquals(expected, reversedArray);
    }
}

My second step was to create a JUnit test that doesn't induce a failing output. 

    import static org.junit.Assert.assertArrayEquals;
    import org.junit.Test;

    public class reversePass {

    @Test
    public void testReversePass() {
        int[] input = {5, 4, 3, 2, 1};
        int[] expected = {1, 2, 3, 4, 5};
        int[] reversedArray = ReversedArray.reversed(input);
        assertArrayEquals(expected, reversedArray);
    }
}

*I WAS HAVING TROUBLE RUNNING THE TWO CODES ABOVE, IT WAS WORKING PRIOR BUT STOPPED WORKING SO I AM GOING TO TAKE IT IN TOMORROW TO GET LOOKED AT*

The before and after code for this bug would look like this...

Before:

    static int[] reversed(int[] arr) {
        int[] newArray = new int[arr.length];
        for(int i = 0; i < arr.length; i += 1) {
          arr[i] = newArray[arr.length - i - 1];
        }
        return arr;
      }
  
  After:
   
    static int[] reversed(int[] arr) {
        int[] newArray = new int[arr.length];
        for (int i = 0; i < arr.length; i++) {
            newArray[i] = arr[arr.length - i - 1];
        }
        return newArray;
    }
    
This fix would have solved the issue that the previous program contained because I created a new array to store the values of the reversed integers. This was to ensure that the 'arr' variable wouldn't be modified and the new array can be placed in the 'newArray'. 

**PART 3:**

I had learned alot from these past 2 weeks of lab, but I think the one thing that really stood out to me was being able to create the web server. It was interesting being able to develop and test a URL and to be able to tweak it to output certain things on the screen. This could range from incrementing a number to displaying text. 
