**PART 1**

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

**PART 2**

I decided to use the *grep* command and four interesting command-line options I chose were the *-i* which would tell grep to perform a case-sensitive search, so it would match the text regardless of if it was uppercase or lowercase. Another command-line option was the *-v* which would tell grep to invert the match, displaying lines that do not contain the specified pattern. There also is the option of using *-A* which displays the lines that match the pattern and also a specified number of lines that follow the matching lines. Lastly, another command-line that can be used with *grep* would be the *-l* which lists only the names of files containing a specific pattern, rather than displaying the matching lines. 