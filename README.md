# Imaginary-CTF-Web-Unique

This is a writeup for the Imaginary CTF Web challenge: Unique

We first visit the provided URL and see the source code: http://puzzler7.imaginaryctf.org:8000/

Note the routes. Take special notice to how a new user object is created in a post request, then redirected to display the user name and text. This will work for the user puzzler7 if we can guess the secret user id. 

How are the user IDs generated? 

  UUID4(NAMESPACE_OID, username)
  
So, UUID4(NAMESPACE_OID, "puzzler7") will generate the required userid.

UUID4(NAMESPACE_OID, "puzzler7") -> 13d68dfc-7d23-5ce9-b8bc-62819792a934

http://puzzler7.imaginaryctf.org:8000/user/13d68dfc-7d23-5ce9-b8bc-62819792a934 gives us the flag.
