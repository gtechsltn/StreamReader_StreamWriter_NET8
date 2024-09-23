# StreamReader StreamWriter in .NET 8.0

https://medium.com/programming-with-c/working-with-files-in-net-using-c-adad9ce621b3

https://docs.google.com/document/d/1rjZbbtsX7TC5_wvMtvAW4PrmJkc28RRylmiO8AzaBDo/

## StreamWriter
```
using System;
using System.IO;

class Program
{
    static void Main()
    {
        string filePath = @"E:\Data_\TMP_\Lorem_Ipsum.txt";

        try
        {
            using (StreamWriter sw = new StreamWriter(filePath))
            {
                sw.WriteLine("Hello, world!");
                sw.WriteLine("This is a sample text.");
            }
        }
        catch (Exception e)
        {
            Console.WriteLine("The file could not be written:");
            Console.WriteLine(e.Message);
        }
    }
}
```

## StreamReader
```
using System;
using System.IO;

class Program
{
    static void Main()
    {
        string filePath = @"E:\Data_\TMP_\Lorem_Ipsum.txt";

        try
        {
            using (StreamReader sr = new StreamReader(filePath))
            {
                string line;
                while ((line = sr.ReadLine()) != null)
                {
                    Console.WriteLine(line);
                }
            }
        }
        catch (Exception e)
        {
            Console.WriteLine("The file could not be read:");
            Console.WriteLine(e.Message);
        }
    }
}
```

## Check File Exists
```
using System;
using System.IO;

class Program
{
    static void Main()
    {
        string filePath = @"E:\Data_\TMP_\Lorem_Ipsum.txt";

        if (File.Exists(filePath))
        {
            Console.WriteLine("File exists.");
        }
        else
        {
            Console.WriteLine("File does not exist.");
        }
    }
}
```
