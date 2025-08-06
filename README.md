# temp


class Solution
{
public:

    static bool isprime(int n)
    {
        n=sqrt(n);
        for(int i=0;i<n;i++)
        {
            if(n%i == 0)
                return false;
        }
        return true;
    }

    int countPrimes(int n)
    {
        int i;
        vector<int> arr(n,0);
        for(i=2;i*2<=n;i++)
        {
            if(arr[i] == 1)
                continue;
            if(isprime(arr[i]))
            {
                int j=2;
                while(j*i <n )
                {
                    arr[j*i] = 1;
                }
            }
        }
        int count=0;
        for(i=2;i<n;i++)
        {
            if(arr[i] == 0)
                count++;
        }
        return count;
    }
};
