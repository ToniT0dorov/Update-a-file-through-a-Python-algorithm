# Algorithm for file updates in Python




<h2>Scenario</h2>
  
You are a security professional working at a health care company. As part of your job, you're required to regularly update a file that identifies the employees who can access restricted content. The contents of the file are based on who is working with personal patient records. Employees are restricted access based on their IP address. There is an allow list for IP addresses permitted to sign into the restricted subnetwork. There's also a remove list that identifies which employees you must remove from this allow list.

Your task is to create an algorithm that uses Python code to check whether the allow list contains any IP addresses identified on the remove list. If so, you should remove those IP addresses from the file containing the allow list. 
<br />
<h2>Project description</h2>
At my organization, access to restricted content is controlled with an allow list of IP addresses.
The "allow_list.txt" file identifies these IP addresses. A separate remove list identifies IP
addresses that should no longer have access to this content. I created an algorithm to
automate updating the "allow_list.txt" file and remove these IP addresses that should
no longer have access.


<h2>Opening the file that contains the allow list</h2>
In this step, I am starting by opening the text file using the <code>import_file</code> variable, the <code>with</code> keyword, and the <code>open()</code> function with the <code>"r"</code> parameter.


https://github.com/ToniT0dorov/Update-a-file-through-a-Python-algorithm/blob/3a8c2ee815f15cf44709dea8411dc2fdb7dfa415/code.py#L1-L11
In my algorithm, the <code>with</code> statement is used with the <code>.open()</code> function in read mode to open
the allow list file for the purpose of reading it. The purpose of opening the file is to allow me to
access the IP addresses stored in the allow list file. The with keyword will help manage the
resources by closing the file after exiting the with statement. In the code with
<code>open(import_file, "r") as file:</code>, the <code>open()</code> function has two parameters. The first
identifies the file to import, and then the second indicates what I want to do with the file. In this
case, <code>"r"</code> indicates that I want to read it. The code also uses the as keyword to assign a
variable named file; file stores the output of the <code>.open()</code> function while I work within the
with statement.
<h2>Reading the file contents</h2>
Now, I use the <code>.read()</code> method to read the imported file and store it in a variable named <code>ip_addresses</code>.

Afterwards, I display <code>ip_addresses</code> to examine the data in its current format.

https://github.com/ToniT0dorov/Update-a-file-through-a-Python-algorithm/blob/d89ed2e62ff3f5b56dc3f65c93436c06992f3ed8/2.py#L1-L19
When using an <code>.open()</code> function that includes the argument <code>"r"</code> for “read,” I can call the
<code>.read()</code> function in the body of the <code>with</code> statement. The <code>.read()</code> method converts the file
into a string and allows me to read it. I applied the <code>.read()</code> method to the file variable
identified in the <code>with</code> statement. Then, I assigned the string output of this method to the
variable <code>ip_addresses</code>.
<h3>Output of the above code :</h3>
https://github.com/ToniT0dorov/Update-a-file-through-a-Python-algorithm/blob/bd33324eb7ce9443ebf9ad2bf9bfb70325314ee2/3#L1-L18

<h2>Converting the string into a list</h2>
After reading the file, I reassign the <code>ip_addresses</code> variable so its data type is updated from a string to a list. I use the  <code>.split()</code> method to achieve this. Adding this step will allow me to iterate through each of the IP addresses in the allow list instead of navigating a large string that contains all the addresses merged together.

Afterwards, I display the <code>ip_addresses</code> variable to verify that the update took place.

https://github.com/ToniT0dorov/Update-a-file-through-a-Python-algorithm/blob/cd6b79a722d132f111c1245697753c8411830260/3.py#L1-L23
Output:https://github.com/ToniT0dorov/Update-a-file-through-a-Python-algorithm/blob/767807667f7c2c44fa446afc77c7add7173b444c/split#L1C1-L1C320

The <code>.split()</code> function is called by appending it to a string variable. It works by converting the
contents of a string to a list. The purpose of splitting <code>ip_addresses</code> into a list is to make it
easier to remove IP addresses from the allow list. By default, the <code>.split()</code> function splits the
text by whitespace into list elements. In this algorithm, the <code>.split()</code> function takes the data
stored in the variable <code>ip_addresses</code>, which is a string of IP addresses that are each
separated by a whitespace, and it converts this string into a list of IP addresses. To store this
list, I reassigned it back to the variable <code>ip_addresses</code>.

<h2>Iterating through the remove list</h2>
Now I will need a code that removes the elements of <code>remove_list</code> from the <code>ip_addresses list</code>. This will require both an iterative statement and a conditional statement.
For now i will just add the iterative statement
https://github.com/ToniT0dorov/Update-a-file-through-a-Python-algorithm/blob/bb8d854a1da4e24485ed4517254d3f27b4d49554/5.py#L1-L29

Output:
https://github.com/ToniT0dorov/Update-a-file-through-a-Python-algorithm/blob/767807667f7c2c44fa446afc77c7add7173b444c/3#L1-L18
A key part of my algorithm involves iterating through the IP addresses that are elements in the
remove_list. To do this, I incorporated a for loop:

The <code>for</code> loop in Python repeats code for a specified sequence. The overall purpose of the <code>for</code>
loop in a Python algorithm like this is to apply specific code statements to all elements in a
sequence. The for keyword starts the <code>for</code> loop. It is followed by the loop variable <code>element</code>
and the keyword <code>in</code>. The keyword <code>in</code> indicates to iterate through the sequence
<code>ip_addresses</code> and assign each value to the loop variable <code>element</code>.

<h2>Removing IP addresses that are on the remove list</h2>
Now Iam building a  conditional statement to remove the elements of <code>remove_list</code> from the <code>ip_addresses</code> list. The conditional statement will be placed inside the iterative statement that loops through <code>ip_addresses</code>. In every iteration, if the current element in the ip_addresses list is in the remove_list, the remove() method will be used to remove that element.

Afterwards,I display the updated ip_addresses list to verify that the elements of remove_list are no longer in the ip_addresses. 
https://github.com/ToniT0dorov/Update-a-file-through-a-Python-algorithm/blob/7082c1476825f315c80708914b6dee4897c5d193/6.py#L1-L38
First, within my <code>for</code> loop, I created a conditional that evaluated whether or not the loop
variable <code>element</code> was found in the <code>ip_addresses</code> list. I did this because applying
<code>.remove()</code> to elements that were not found in <code>ip_addresses</code> would result in an error.
Then, within that conditional, I applied <code>.remove()</code> to <code>ip_addresses</code>. I passed in the loop
variable <code>element</code> as the argument so that each IP address that was in the <code>remove_list</code>
would be removed from <code>ip_addresses</code>.

Output:
https://github.com/ToniT0dorov/Update-a-file-through-a-Python-algorithm/blob/79da886cdb4a22853f5118b9208a7e5391547617/remove#L1

<h2>Updating the file with the revised list of IP addresses</h2>
The next step is to update the original file that was used to create the <code>ip_addresses</code> list. A line of code containing the <code>.join()</code> method be added to the code so that the file can be updated. This is necessary because ip_addresses must be in string format when used inside the with statement to rewrite the file.

The <code>.join()</code> method takes in an iterable (such as a list) and concatenates every element of it into a string. The <code>.join()</code> method is applied to a string consisting of the character that will be used to separate every element in the iterable once its converted into a string. In the code below, the method is applied to the string <code>" "</code>, which contains just a space character. The argument of the <code>.join()</code> method is the iterable I want to convert, and in this case, that's <code>ip_addresses</code>. As a result, it converts <code>ip_addresses</code> from a list back into a string with a space between each element and the next.

After this line with the <code>.join()</code> method, i am building the <code>with</code> statement that rewrites the original file. Use the <code>"w"</code> parameter when calling the <code>open()</code> function to delete the contents in the original file and replace it with what I want to write. 
https://github.com/ToniT0dorov/Update-a-file-through-a-Python-algorithm/blob/f3be4a4244390e28635f3be40cefea3557927b67/7.py#L1-L46

<h2>Summary</h2>
I created an algorithm that removes IP addresses identified in a <code>remove_list</code>code> variable from
the <code>"allow_list.txt"</code>code> file of approved IP addresses. This algorithm involved opening the
file, converting it to a string to be read, and then converting this string to a list stored in the
variable <code>ip_addresses</code>code>. I then iterated through the IP addresses in <code>remove_list</code>code>. With each
iteration, I evaluated if the element was part of the <code>ip_addresses</code>code> list. If it was, I applied the
<code>.remove()</code>code> method to it to remove the element from <code>ip_addresses</code>code>.. After this, I used the
<code>.join()</code>code> method to convert the <code>ip_addresses</code>code> back into a string so that I could write over
the contents of the <code>"allow_list.txt"</code>code> file with the revised list of IP addresses.
