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

I decided to use the *grep* command and four interesting command-line options I chose were the *-i* which would tell grep to perform a case-sensitive search, so it would match the text regardless of if it was uppercase or lowercase. Another command-line option was the *-v* which would tell grep to invert the match, displaying lines that do not contain the specified pattern. There also is the option of using *-n* display the matched lines and their line numbers. Lastly, another command-line that can be used with *grep* would be the *-o* which prints only the matched parts of a matching line, with each such output on a separate output line. 

Using *-i*:
Input:

    grep -i "resuscitated" /Users/ethanheath/docsearch/technical/biomed/1468-6708-3-3.txt 
#
Output:

    death, non-fatal myocardial infarction, resuscitated sudden
        myocardial infarction and resuscitated sudden cardiac death
        resuscitated sudden cardiac death, worsening heart failure,
#
Input: 

    grep -i "geneticists" /Users/ethanheath/docsearch/technical/plos/journal.pbio.0020190.txt
#
Output:

    biologists. For geneticists and cell biologists who study meiosis, the existence of
        For population geneticists, much of the interest in recombination hotspots comes from
#

Using *-v*:
Input:

    grep -v -i "the" /Users/ethanheath/docsearch/technical/biomed/1468-6708-3-3.txt
#
Output:

    Three published [ 1 2 3 ] and one recently presented [ 4
        ] randomized placebo-controlled clinical trial have
        unequivocally demonstrated that 3-Hydroxy-3-methylgluatryl
        coenzyme A (HMG CoA) reductase inhibitors (statins) reduce
        death, myocardial infarction, unstable angina, percutaneous
        and surgical coronary revascularization, and stroke in
        persons with 
        stable coronary disease. Because
        patients who had experienced an acute coronary syndrome
        within three to six months of enrollment were excluded,
        recently 
        initiated immediately following an acute coronary syndrome
        cardiac events is much greater in patients with unstable
        Ischemia Reduction with Aggressive Cholesterol Lowering
        (MIRACL) trial set out to answer this question.
#
Input:

    grep -v -i "and" /Users/ethanheath/docsearch/technical/biomed/bcr620.txt
#
Output:

    Introduction
        Breast cancer is a major cause of death among women in
        localized, many patients will succumb to the disease if the
        primary tumor metastasizes to secondary organs. Although
        treating the primary tumor, the ability to predict the
        or control recurrent disseminated malignancy remain major
        clinical challenges in oncology.
        We have previously characterized an experimental system
        an isogenic background [ 2 ] . Two independent clones of
        opposing metastatic phenotype were derived from the
        nonmetastatic NM-2C5 cell lines). When inoculated into the
        mammary fat pad of athymic mice, both cell lines form
        primary tumors. While clone M-4A4 aggressively metastasizes
        nonmetastatic. Initial comparative gene expression analysis
        of the two clones revealed the secreted, integrin-binding
        protein osteopontin (OPN) [ 3 ] to be significantly
        increased in the metastatic M-4A4 cell line. Conversely,
        tyrosinase-related protein-1 (TYRP-1) was markedly
        overexpressed in the nonmetastatic NM-2C5 cell line [ 2 5 ]
