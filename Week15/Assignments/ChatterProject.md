# Chatter
## Due: Tuesday, May 23, 2017 at 5:30 pm
### - [Submission Link](https://docs.google.com/forms/d/e/1FAIpQLScrrd5G-1ExyCYLOoTdRCaPrkiK_hLluhUEjA8IGCF-05vCnw/viewform)

## Overview
Chatter is a web application that is similar in functionality to Twitter. Throughout this project, you will not only gain practical experience in working on a real-world web app, but will learn new concepts as well as integrate previous knowledge.

## Skills Required
- MVC
- JavaScript and jQuery
- AJAX
- SQL and LINQ
- JSON
- HTML and CSS

## Tasks
- [ ] Let’s determine the actual fields we want to return for our chats. Select as few as possible (you don’t want to waste the bandwidth on useless data -- that will make your pages run slower and probably cost you more money in hosting data transfer fees, plus you don’t want to show end users more information than necessary for security reasons).
    - [ ] I want to select the Chat message, and the AspNetUsers user name, ordering the chats in descending order by the chat timestamp. 
    - [ ] What is the SQL Query for this? (Hint: Use an Inner Join to select from Chat and AspNetUsers.) 
    - [ ] Enter your query in the SQL statement window in Linqer.
    - [ ] Convert the SQL to LINQ.
- [ ] Copy both your SQL Query and your LINQ syntax to your TestJson method in the ChatsController (Visual Studio).  
    - [ ] Comment out your SQL Query, but leave it in there -- this will be part of your project grade.
    - [ ] Under that add your LINQ query so your TestJson  method looks similar to the following (Note: I’ve purposefully hidden some of the code to ensure you can write the SQL statement.)

    ```
    public JsonResult TestJson()
    {
        //SQL Statment HERE (mine is not shown since this is part of //your project grade).
        
        //Now, the LINQ equivalent is declared as a variable (below).
        var chats = from [NOT SHOWN PURPOSEFULLY] in db.Chats
       	            orderby
                    Chats.Timestamp [NOT SHOWN]
                    select new
                    {
                        Chats.Message,
                        Chats.AspNetUser.UserName
                    };

        //Next we serialize our data in the model to JSON(Newtonsoft //library at work). 
        //FYI: the query isn’t run until you call the ToList() method.

        var output = JsonConvert.SerializeObject(chats.ToList());

        //Finally, we return Json to the view
        return Json(output, JsonRequestBehavior.AllowGet);
    }
    ```
- [ ] Update your View so it shows the users with their chats in an attractive way. Your ultimate solution must be different than my example (above), you can
use the same techniques though. 
- [ ] Add ```[Authorize]``` and ```[RequireHttps]``` attributes in your ChatsController. (Authorize forces a user to be logged in to see a page.)
- [ ] Test all to ensure attributes work and your view successfully shows the chats you entered into your table.
- [ ] Move your $.get() code into a separate function. Call that function from your button’s click handler (instead of an anonymous function -- see hint below).

    ```
    $("#getChats").click(myFunction);

                function myFunction(){
                    $.get("@Url.Action("TestJson","Chats")", function (serverResponse) {
                        var jsonTest = JSON.parse(serverResponse);
                        //console.log(jsonTest);

                        var ul = $("<ul>", { id: "messageList", "class": "bg-primary" });
                        ul.click(function () { alert("ul was clicked!"); });
                        $("#response").append(ul);

                        $.each(jsonTest, function (inx, val) {
                            var myBgClass = ["bg-info","bg-warning"];
                            var li = $("<li>", { id: "li" + inx, "class": myBgClass[inx % 2] });
                            li.text(val.Message);
                            li.click(function () { alert("my index is " + inx); });
                            ul.append(li); 
                        });
                    })
                }
    ```
- [ ] Finally, not only do you want to retrieve chats when the button is clicked, but also on an interval. Investigate a way to call your new function that has the $.get() statement on such an interval so your page refreshes regularly with no chats repeated.
- [ ] Most importantly, read about the post object at [jQuery](https://api.jquery.com/jquery.post/), and create a controller method in your ChatsController to receive the post (using AJAX within your browser) and save it to your database. You must use comments to explain what you are doing in both your Javascript/jQuery, as well as the controller method you create. 
- [ ] Redirect users to the Chat Index page after they successfully login.
- [ ] Complete the look and feel of your project. This will not be part of your grade (the functionality is more important), but you might want to show off your work when you have finished.
