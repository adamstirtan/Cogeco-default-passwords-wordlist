A wordlist file that contains strings in the form: "{00-FF}{00-FF}{00-FF}COGECO". This is the default password format for Cogeco WiFi routers.

## C# Code

```
using System;
using System.IO;

namespace CogecoPasswordGenerator
{
    class Program
    {
        static void Main(string[] args)
        {
            string docPath = Environment.GetFolderPath(Environment.SpecialFolder.MyDocuments);

            using StreamWriter outputFile = new StreamWriter(Path.Combine(docPath, "cogeco_passwords.txt"));

            for (int r = 0; r < 256; r++)
            {
                for (int g = 0; g < 256; g++)
                {
                    for (int b = 0; b < 256; b++)
                    {
                        string password = $"{r:X2}{g:X2}{b:X2}COGECO";

                        outputFile.WriteLine(password);
                    }
                }
            }
        }
    }
}
```
