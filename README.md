# a
char[] chars = { 'w', 'o', 'r', 'd' }; sbyte[] bytes = { 0x41, 0x42, 0x43, 0x44, 0x45, 0x00 };  // Create a string from a character array. string string1 = new string(chars); Console.WriteLine(string1);  // Create a string that consists of a character repeated 20 times. string string2 = new string('c', 20); Console.WriteLine(string2);  string stringFromBytes = null; string stringFromChars = null; unsafe {    fixed (sbyte* pbytes = bytes)    {       // Create a string from a pointer to a signed byte array.       stringFromBytes = new string(pbytes);    }    fixed (char* pchars = chars)    {       // Create a string from a pointer to a character array.       stringFromChars = new string(pchars);    } } Console.WriteLine(stringFromBytes); Console.WriteLine(stringFromChars); // The example displays the following output: //       word //       cccccccccccccccccccc //       ABCDE //       word
