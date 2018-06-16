# gsa.apple.com.cn
 how to write a prety pure c code authenticating the account by yourself.
 apple's srp proto is standard SRP-6a. 
 some diffrences
 c is for cookie
 sp selected proto
 s salt
 i iteration count for pbkdf2_hmac digest iter count
 SRP password is not the user input password, apple use pbkdf2_hmac dk as SRP password.
 
 
 
