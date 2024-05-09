# 19AI308-Object-Oriented-Programming-using-CSharp-Exp-10-File-Manipulation
Develop a C# program to get the values from the user using structure and store it in a file in a specific path using file stream concept

# AIM:
To develop a C# program using file streams.

# ALGORITHM:
# Step 1: Define a structure UserData to hold user data fields like name, age, and email.
# Step 2: Create an array of UserData to store multiple user data entries. Use a loop to prompt the user to input their name, age, and email, and store the input in the array.
# Step 3: Specify the file path where the user data will be stored.
# Step 4: Inside the loop, for each user data entry, open the file in append mode using StreamWriter and write the user data to the file.
# Step 5: Close the file after writing all user data.
# Step 6: Display a message indicating that the user data has been saved to the file.

# PROGRAM:
# NAME : THRIKESWAR
# REGISTER NUMBER : 212222230162
```
using System;
using System.IO;

struct UserData
{
    public string Name;
    public int Age;
    public string Email;
}

class Program
{
    static void Main(string[] args)

    {
        string filePath = @"C:\Users\SEC\Desktop\exp10.txt";
        UserData[] ud=new UserData[3];
        for(int i=0; i<3;i++)
        {
            Console.WriteLine("Enter your name:");
            ud[i].Name = Console.ReadLine();

            Console.WriteLine("Enter your age:");
            ud[i].Age = int.Parse(Console.ReadLine());

            Console.WriteLine("Enter your email:");
            ud[i].Email = Console.ReadLine();

            WriteUserDataToFile(filePath, ud[i]);
        }  
        Console.WriteLine("User data has been saved to the file.");
    }

    static void WriteUserDataToFile(string filePath, UserData userData)
    {
        //using (FileStream fs = new FileStream(filePath, FileMode.Create))
        using (StreamWriter writer = File.AppendText(filePath))
        {
            
            writer.WriteLine($"Name: {userData.Name}");
            writer.WriteLine($"Age: {userData.Age}");
            writer.WriteLine($"Email: {userData.Email}");
            
        }
    }
}
```

# OUTPUT:
![Screenshot 2024-05-09 211735](https://github.com/thrikesh/19AI308-Object-Oriented-Programming-using-CSharp-Exp-10-File-Manipulation/assets/119576222/97ec6c8d-3761-463c-91e1-1665a9ac1735)



# RESULT:
Thus the C# program to get the values from the user using structure and store it in a file in a specific path using file stream concept executed successfully.
