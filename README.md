# Algorithm for file updates in Python




<h2>Scenario</h2>
  
You are a security professional working at a health care company. As part of your job, you're required to regularly update a file that identifies the employees who can access restricted content. The contents of the file are based on who is working with personal patient records. Employees are restricted access based on their IP address. There is an allow list for IP addresses permitted to sign into the restricted subnetwork. There's also a remove list that identifies which employees you must remove from this allow list.

Your task is to create an algorithm that uses Python code to check whether the allow list contains any IP addresses identified on the remove list. If so, you should remove those IP addresses from the file containing the allow list. 
<br />



<h2>Opening the file that contains the allow list</h2>
In this step, I am starting by opening the text file using the <code>import_file</code> variable, the <code>with</code> keyword, and the <code>open()</code> function with the <code>"r"</code> parameter.


https://github.com/ToniT0dorov/Update-a-file-through-a-Python-algorithm/blob/3a8c2ee815f15cf44709dea8411dc2fdb7dfa415/code.py#L1-L11

<h2>Reading the file contents</h2>
Now, I use the <code>.read()</code> method to read the imported file and store it in a variable named <code>ip_addresses</code>.

Afterwards, I display <code>ip_addresses</code> to examine the data in its current format.

https://github.com/ToniT0dorov/Update-a-file-through-a-Python-algorithm/blob/d89ed2e62ff3f5b56dc3f65c93436c06992f3ed8/2.py#L1-L19

<h3>Output of the above code :</h3>
https://github.com/ToniT0dorov/Update-a-file-through-a-Python-algorithm/blob/bd33324eb7ce9443ebf9ad2bf9bfb70325314ee2/3#L1-L18

<h2>Converting the string into a list</h2>
After reading the file, I reassign the <code>ip_addresses</code> variable so its data type is updated from a string to a list. I use the  <code>.split()</code> method to achieve this. Adding this step will allow me to iterate through each of the IP addresses in the allow list instead of navigating a large string that contains all the addresses merged together.

Afterwards, I display the <code>ip_addresses</code> variable to verify that the update took place.

https://github.com/ToniT0dorov/Update-a-file-through-a-Python-algorithm/blob/cd6b79a722d132f111c1245697753c8411830260/3.py#L1-L23

<h2>Iterating through the remove list</h2>
Now I will need a code that removes the elements of <code>remove_list</code> from the <code>ip_addresses list</code>. This will require both an iterative statement and a conditional statement.
For now i will just add the iterative statement
https://github.com/ToniT0dorov/Update-a-file-through-a-Python-algorithm/blob/bb8d854a1da4e24485ed4517254d3f27b4d49554/5.py#L1-L29
