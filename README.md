```C#
   public string AddBinary(string a, string b) {
         StringBuilder sb = new StringBuilder();
            int len = a.Length >= b.Length ? a.Length : b.Length;
            a= a.PadLeft(len, '0');
            b= b.PadLeft(len, '0');


            int rem = 0;
            for (int i = len -1; i>=0; i--)
            {
                int an = a[i] - '0';
                int bn = b[i] - '0';
                int totn = rem > 0 ? (an + bn + rem) : (an + bn);

                switch (totn)
                {
                    case 0: 
                        sb.Append(0);
                        rem = 0;
                        break;
                    case 1: 
                        sb.Append(1);
                        rem = 0;
                        break;
                    case 2: 
                        sb.Append(0);
                        rem = 1;
                        break;
                    case 3: 
                        sb.Append(1);
                        rem = 1;
                        break;
                    default: break;
                } 
            }
            if (rem > 0)
                sb.Append(rem);
            char[] chars = sb.ToString().ToCharArray();
            Array.Reverse(chars);
            string str = new string(chars);

            return str;
    }
```

## Complexity Analysis

* Time Complexity: O(N)
* Space Complexity: O(N)
