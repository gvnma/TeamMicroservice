Login Microservice for Che-Han Hsu

Communication Contract
* Always send data using 'pipe.send' as a dictionary with a valid 'action' key
* Expect responses to follow a consistent format with a 'status' key



***How to Request Data:
To request a login, send a dictionary via the pipeline with the action 'login' and include a 'username' and 'password' field.


Example call (Python):

pipe.send({

'action': 'login',
'username': 'user123',
'password': 'password123'
)}

pipe.send({'action': 'exit'}) # Shuts down the program

***How to Receive Data:
To receive the data from the login, wait for the response, which will be a dictionary with a status key using pipe.recv()

Example: 

response = pipe.recv()
if response['status'] == 'success':
    print("Login successful!")
else:
    print("Login failed.")


UML Diagram:

[UML diagram.PNG](https://github.com/gvnma/TeamMicroservice/blob/df0e5e9cf1ed8acddf784a3c9f0d79a202c63810/UML%20diagram.PNG)



