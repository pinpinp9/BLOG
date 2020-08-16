---
title: "C Sharp: Insert image into MS Access"
date: 2020-08-16T21:52:07+10:00
archives: "2020"
tags: []
author: Pinpin
---
## [SOLVED] Insert image into database in microsoft access

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

