# Task1_Guvi
Task1_Login_ID_system_Python
STAGE -- 1 (Registration)

    import re
    def signup():
           email = input("Enter email address: " )
           pwd = input("Enter password: ")
           conf_pwd = input("Confirm password: ")
           email_regex = "^[a-z0-9]+[\._]?[a-z0-9]+[@]\w+[.]\w{2,3}$" ## ALL SMALL APLHANUMERIC
           pwd_regex = "^.*(?=.{5,17})(?=.*\d)(?=.*[a-z])(?=.*[A-Z])(?=.*[@#$%^&+=]).*$"
           pwd_result = re.findall(pwd_regex, pwd)
    
    if(re.search(email_regex,email)):
        print("Valid Email")
        if (pwd_result) and pwd==conf_pwd:
            print("Valid Password")
            return {email:pwd}
        else:
            print("Password not valid")
    else:   
        print("Invalid Email")
        
Stage --- 2 ( Once the username and password are validated, store those values in a file)

     data_base = {}
     def store_cred(result):
         data_base.update(result)
    
Stage -- 3 ( When the user chooses to Login, check whether his/her credentials exist in the file or not based on the user input If doesn’t exist ask them to go for Registration or If they have chosen forget password you should be able to retrieve their original password based on their username provided in the user input.If nothing matches in your file you should ask them to Register)

    def forget_pass():
        email_id = input("Enter Valid Email here: ")
        if email_id in data_base.keys():
            print(data_base[email_id])
