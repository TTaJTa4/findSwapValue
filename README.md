public class findSwapValue
{
    public static void main(String[] args)
    {
        int[] a = {1,1,1,2,4};
        int[] b = {3,3,3,6};
        findSwapValue(a,b);
        
        int[] a = {1,2,3,8};
        int[] b = {4,5,6,7};
        findSwapValue(a,b);
        
        int[] a = {1,2,3};
        int[] b = {8,9,10};
        findSwapValue(a,b);
    }

    public static void findSwapValue(int[] a, int[] b)
    {
        int target = getTarget(a,b);

        // If target is 0, answer is not possible
        if(target == 0)
            return;

        // Declaration of each array's index
        int indA = 0, indB = 0;
        while(indA < a.length && indB < b.length)
        {
            int diff = a[indA] - b[indB];
            if(diff == target)
            {
                System.out.println(a[indA] + " & " + b[indB]);
                return;
            }
            else if(diff < target)
                indA++;
            else
                indB++;
        } // end of while
    }

    // Method to calculate: a - b = (sumA - sumB)/2
    public static int getTarget(int[] a, int[] b)
    {
        // Calculates sum of each array
        int sumA = getSum(a);
        int sumB = getSum(b);

        // target must be an integer
        if((sumA - sumB) % 2 != 0)
            return 0;
        return ((sumA - sumB)/2);

    }

    // Method to calculate sum of elements of array
    public static int getSum(int[] a)
    {
        int count = 0;
        for(int i = 0; i < a.length; i++)
            count = count + a[i];
        return count;
    }
}
