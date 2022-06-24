1. I have used Java Spring Boot for this task. Therefore running the main class inside "src/main/java/com/intervie/notes/NotesApplication.java"
 will get the project up and running.

2. You have to build your UI to facilitate the following task in the way I have mentioned.
   I. create a note - pass the following JSON body as a POST request to the path http://localhost:8080/api/notes
      {"content":"John9", "userId":3, "isArchived":false}
      You do not have to pass the note Id since it will be auto generated. you will get 201 CREATED HTTPResponse with the JSON body of the created Note.
      Your user Id will be null checked.

   II update a note - pass the following JSON body as a PUT request to the path http://localhost:8080/api/notes
      {"id": 1 , "content":"John9", "userId":3, "isArchived":false}
      You have to put the Id of the note you want to update and your user Id. if the particular note is not authorized with your user Id you will not
      be able to update it.
      You will get 200 OK HTTPResponse with the JSON body of the updated Note.

   III Archive or Unarchive a note - pass the following JSON body as a PUT request to the path http://localhost:8080/api/notes/{archived}
       {"id": 1 , "content":"John9", "userId":3}
       {archived} has to be true or false based on you want to archive it or unarchive it. if the particular note is not authorized with your user Id you will not
       be able to update it.
       You will get 200 OK HTTPResponse with the JSON body of the updated Note.

   IV Get archived notes list - pass a GET request to the path http://localhost:8080/api/notes/archived/{userId} 
      {userId} has to be your User Id. only the notes authorized by your user Id will be updated.

   V  IV Get the notes list which are not archived - pass a GET request to the path http://localhost:8080/api/notes/notArchived/{userId}
      {userId} has to be your User Id. only the notes authorized by your user Id will be updated.
   
   VI Delete a note - pass a DELETE request to the path http://localhost:8080/api/notes/{noteId}/{userId}
      {noteId} has to be the Id of the note you want to delete. {userId} has to be your user Id. if the particular note is not authorized with your user Id 
      you will not be able to update it. a successful deletion youll get 204 NO CONTENT HTTPResponse.

3. I Used Java Spring Boot since it can be used to do rapid development which easyly get up and running, 
   it gives an embedded DB H2 (which I used here),
   It gives annotations to create CRUD operations,
   can be used to write test cases easyly.
   I loved to use Node JS here since that is used in your company. But there is a limited time frame I used Spring Boot since I am more familiar with it.

4. I. I could not write test cases inside the limited time frame. I will definitely do that if I got more time.
   II. I implemented this for multiuser environment that allow only authorized users can do the data manipulation or reading. I got user ID as a parameter 
   here. I know that is not the proper authorization process. If I got more time I will implement a proper authorization process.
   III. sinc I used a parameter authorization everytime the user did not get the appropriate response for some reason I gave 404 NOT FOUND HTTPResponse
   instead of giving a proper error message. I did that because proper error message will help the user to determine that his/her USER ID is correct or not.
   In a proper authorization process I will give the correct error message.
   

  
