# LearningQuest

##### The Learning Quest will connect all the users to the main database, and would allow them to reuse the credentials on all applications developed by REDU Edu Network.
####
####

<p align="center">
<img width="750" src="Redu LQ.drawio.png" alt="LQDB logo">
</p>

If one would observe above flow, the REDU developers will be using Primary APIs and will make a call upon following APIs provided to get certain details,


1.	**[signUp_LQ]**, this API will be used to signup a user. In addition, to call this API it requires to pass following values,
```yaml
{
   “name”: “Eric”,
   “email”: “eric@email.com”,
   “password”: “123123123”,
   “date_of_birth”: “00-00-0000” 	
}
```
###### Providing correct values should return following outcome,

```yaml
{
   “status”: “200”,
   “message”: “user registration successful”
}
```

###### If user already exists in the system,

```yaml
{
   “status”: “200”,
   “message”: “user already registered”
}
```

_____________________________________________________________________

2.	**[login_LQ]**, calling this API requires passing of following credentials,
```yaml
{
   “email”: “eric@email.com”,
   “password”: “123123123”
}
```
###### If the credentials are correct, the outcome should be as following,

```yaml
{
   “status”: 200,
   “message”: “user found”,
   “user_id”: “22”,
   “token”: “%$234wdsff1@”
} 
```
###### Otherwise, if the user is not found or credentials are not provided correctly, the outcome should be as following,

```yaml
{
   “status”: 200,
   “message”: “user not found”,
   “user_id”: “n/a”,
   “token”: “n/a”
}
```

_____________________________________________________________________

3.	**[get_user_profile_LQ]**, to make a call upon this API function, passing of the following values is required,
```yaml
{
   “user_id”: “22”,
   “token”: “%$234wdsff1@”
}
```
###### If the user has not yet logged into his/her xumm account, it should return the outcome as following, 

```yaml
{
   "status": 200,
   	 "data": 
       {
         “id”: “22”,
         “name”: “Eric”,
         “email”: “eric@email.com”,
         “date_of_birth”: “00-00-0000”,
         “xumm_account”: “n/a”,
         "assets": [],
         “date_created”: “2020-10-02 00:00:00”,
         “date_updated”: “n/a”,
         “last_login”: “2021-09-07 01:54:02”,
}
```
###### If the user has already logged into his/her xumm account, it should return the outcome as following,

```yaml
{
   "status": 200,
   "data": 
      {
         “id”: “22”,
         “name”: “Eric”,
         “email”: “eric@email.com”,
         “date_of_birth”: “00-00-0000”,
         “xumm_account”: “rDpw131ffoine34xxxxxxxxxxxxxxx43112a”,       
         "assets":
         [
            {
               "currency": "XRP",
               "balance": "12",
               "issuer": ""
            }
         ],
         “date_created”: “2020-10-02 00:00:00”,
         “date_updated”: “n/a”,
         “last_login”: “2021-09-07 01:54:02”,
}
```
