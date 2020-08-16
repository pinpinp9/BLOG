---
title: "C Sharp: Insert image into MS Access"
date: 2020-08-16T21:52:07+10:00
archives: "2020"
tags: [
    "c#",
    "image",
    "MS Access"   
]
author: Pinpin
weight: 10
---
## [SOLVED] Insert image into database in microsoft access

For beginners, it is not an easy task to deal with complicated data such as byte, binary, etc.

This article will show an samply way of how to insert such data into Microsoft Access. You also can adapt the code

by yourself if you are working with a database. I assume that you are familiar with SQL command, and have some C# or Java knowledge.

I'll explain how to make the connection between both sides (MS ACCESS and VS CODE) and how you can convert raw data to binary. 

Then, you will be fine to insert such data into your backend.


#####  C#- CREATE CONNECTION TO MS ACCESS

Create the connection with Microsoft Access



```
   OleDbConnection con = new OleDbConnection(@"Provider=Microsoft.ACE.OLEDB.12.0;Data Source=C:\Employee.accdb");

```

#####  C#-CONVERT IMAGE TO BINARY DATA

Using MemoryStream to convert data to byte

```
private byte[] SavePhoto() {
    //converting photo to binary data
    MemoryStream ms = new MemoryStream();
    byte[] photo_aray;
           
    //using MemoryStream:
    pictureBox1.Image.Save(ms, ImageFormat.Jpeg);
    photo = new byte[ms.Length];
    ms.Position = 0;
    ms.Read(photo_aray, 0, photo.Length);
    return photo;
  }
  
```

#####  C#-INSERT DATA INTO DATABASE

```
   OleDbCommand cmd = new OleDbCommand();
   cmd.CommandType = CommandType.Text;
   cmd.CommandText = "INSERT INTO employee ([name],[department],[image]) VALUES (?,?,?) WHERE ID=?";

    try
    {   
        if(pictureBox1.Image!=null){
           cmd.Connection = con;
           con.Open();             
           cmd.Parameters.AddWithValue("@name", textBox1.Text.Trim());
           cmd.Parameters.AddWithValue("@dpt", textBox2.Text.Trim());
           cmd.Parameters.AddWithValue("@photo", SavePhoto());
           cmd.ExecuteNonQuery();
           con.Close();
         }
          MessageBox.Show("Data inserted successfully");
    }catch (Exception x)
       {
          MessageBox.Show(ex.Message.ToString());
       }
```

