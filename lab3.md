**Part 1**
<p>Here is my code for the Chat Server.</p>

![Image](Code.png)

<p>I tried several times to see the function of the Chat Server.</p>

![Image](Server_1.jpg)
<p>For this line, I add /add-message?s=How%20are%20you&user=yash to the url. The method of handleRequest is used. In this method, when the argument is eqaul to /add-message, the program will pass the if statement and get into the next stage.</p>
<p>Then, the method will check the format of the command, whether it has the message and the user.</p>
<p>When the command is in the format of message and user, the method will first seperate the query into the message string, and the message object in this case is "How are you" and user name string, which is "yash".</p> 
<p>Then, the method will combine them into the form of the output. In this case is the "yash: How are you".</p>
<p>Finally, prints the combined output onto the server and store it into the text file.</p>

![Image](Server_2.jpg)
<p>For this line, I add /add-message?s=Im%20fine%20thx&user=Sylvia to the end of the url. The same method is used, and the same logic is followed.</p>
<p>In this case, the method will seperate the command line into two strings, "Im fine thx" is the first one as message and "Sylvia" as the user name.</p>
<p> Then, the combined output is "Sylvia: Im fine thx". This line is showed on the server as well as stored in the text file.</p>

**Part 2**

![Image](Public_keys.png)
<p>The picture is showing the path of public keys, it also shows the file and directories under it by the command ls.</p>

![Image](Without_key.png)
<p>The screenshot shows the way that I do not need to type in my password to log into my ieng6 accound. After I type "ssh yic091@ieng6.ucsd.edu" and press enter, the log in process happens without the need of entering password.</p>

**Part 3**
<p>I learnt about the things about the command ssh, mkdir, etc. Also, I gained more idea about establishing a server by myself and also the way to log into the remote accound of ieng6. What's more, I learnt the easier way to log into the ieng6 account without entering the password every time.</p>
