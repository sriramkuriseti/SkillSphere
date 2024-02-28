USING POSTMAN TO TEST THE BACKEND:
 POSTMAN it is popular API testing tool used in the development process to ensure that APIs are working as expected, even if there is no frontend interface yet.

TESTING:

 create base urls:

  * BASE_AUTH :  http://localhost:4000/api/v1/auth
  * BASE_PROFILE : http://localhost:4000/api/v1/profile
  * BASE_COURSE : http://localhost:4000/api/v1/course
  * BASE_PAYMENT: http://localhost:4000/api/v1/payment
___________________________________________
AUTHENTICATION :
  SENDING OTP :
  POST : {BASE_AUTH}/sendotp
  body : { "email":"kurisetisriram@gmail.com" }
  response: { 
             "success":true,
              "message":"OTP Sent Successfully",
              "otp":"131676"
            }
       
   SIGN UP:  enter the recieved otp
   POST: {BASE_AUTH}/signup
   body: {
           "firstName" : "sriram",
            "lastName" : "kuriseti",
            "password" : "123456",
            "confirmPassword" : "123456",
            "email" : "kurisetisriram@gmail.com",
            "accountType" : "Student",
            "otp" : "131676"
            }
     response : {
    "success": true,
    "user": {
        "firstName": "sriram",
        "lastName": "kuriseti",
        "email": "divya29102003@gmail.com",
        "password": "$2b$10$rIEMjrGPXn3zUxYnpR3pYuhSwlekjXnZq5pYFnUor5H19ebqGIjEG",
        "accountType": "Student",
        "active": true,
        "approved": true,
        "additionalDetails": "65df0be9fa0d44231f9829fb",
        "courses": [],
        "image": "https://api.dicebear.com/5.x/initials/svg?seed=sriram kuriseti",
        "courseProgress": [],
        "_id": "65df0be9fa0d44231f9829fd",
        "createdAt": "2024-02-28T10:33:13.681Z",
        "updatedAt": "2024-02-28T10:33:13.681Z",
        "__v": 0
    },
    "message": "User registered successfully"
}
       

Similarly Create accounts for instructor and admin

LOGIN:
post : {BASE_AUTH}/login
body :
      {

    "email" : "divyapinikeshi29@gmail.com",
    "password" :"123456"
}

response:
{
    "success": true,
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6ImRpdnlhcGluaWtlc2hpMjlAZ21haWwuY29tIiwiaWQiOiI2NWRmMGY5YmZhMGQ0NDIzMWY5ODJhMjgiLCJhY2NvdW50VHlwZSI6Ikluc3RydWN0b3IiLCJpYXQiOjE3MDkxMTc0ODEsImV4cCI6MTcwOTIwMzg4MX0.fF7qITp4qDJZMAV0mj-F9K2s0uDm8Oc9lieyTsY-CAs",
    "user": {
        "_id": "65df0f9bfa0d44231f982a28",
        "firstName": "Divya",
        "lastName": "pinikeshi",
        "email": "divyapinikeshi29@gmail.com",
        "accountType": "Instructor",
        "active": true,
        "approved": true,
        "additionalDetails": {
            "_id": "65df0f9bfa0d44231f982a26",
            "gender": null,
            "dateOfBirth": null,
            "about": null,
            "contactNumber": null,
            "__v": 0
        },
        "courses": [],
        "image": "https://api.dicebear.com/5.x/initials/svg?seed=Divya pinikeshi",
        "courseProgress": [],
        "createdAt": "2024-02-28T10:48:59.892Z",
        "updatedAt": "2024-02-28T10:48:59.892Z",
        "__v": 0,
        "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6ImRpdnlhcGluaWtlc2hpMjlAZ21haWwuY29tIiwiaWQiOiI2NWRmMGY5YmZhMGQ0NDIzMWY5ODJhMjgiLCJhY2NvdW50VHlwZSI6Ikluc3RydWN0b3IiLCJpYXQiOjE3MDkxMTc0ODEsImV4cCI6MTcwOTIwMzg4MX0.fF7qITp4qDJZMAV0mj-F9K2s0uDm8Oc9lieyTsY-CAs"
    },
    "message": "User Login Success"
}

Instructor

admin:
{
    "success": true,
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6ImRpdnlhYmhhcmF0aGlwaW5pa2VzaGlAZ21haWwuY29tIiwiaWQiOiI2NWRmMGVmZWZhMGQ0NDIzMWY5ODJhMTUiLCJhY2NvdW50VHlwZSI6IkFkbWluIiwiaWF0IjoxNzA5MTE3NjI5LCJleHAiOjE3MDkyMDQwMjl9.fgb9aNGq0QkeqoA2Jbl-VgpyE7uBYW7eaRz66Hcf9YU",
    "user": {
        "_id": "65df0efefa0d44231f982a15",
        "firstName": "Divya",
        "lastName": "kuriseti",
        "email": "divyabharathipinikeshi@gmail.com",
        "accountType": "Admin",
        "active": true,
        "approved": true,
        "additionalDetails": {
            "_id": "65df0efefa0d44231f982a13",
            "gender": null,
            "dateOfBirth": null,
            "about": null,
            "contactNumber": null,
            "__v": 0
        },
        "courses": [],
        "image": "https://api.dicebear.com/5.x/initials/svg?seed=Divya kuriseti",
        "courseProgress": [],
        "createdAt": "2024-02-28T10:46:22.813Z",
        "updatedAt": "2024-02-28T10:46:22.813Z",
        "__v": 0,
        "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6ImRpdnlhYmhhcmF0aGlwaW5pa2VzaGlAZ21haWwuY29tIiwiaWQiOiI2NWRmMGVmZWZhMGQ0NDIzMWY5ODJhMTUiLCJhY2NvdW50VHlwZSI6IkFkbWluIiwiaWF0IjoxNzA5MTE3NjI5LCJleHAiOjE3MDkyMDQwMjl9.fgb9aNGq0QkeqoA2Jbl-VgpyE7uBYW7eaRz66Hcf9YU"
    },
    "message": "User Login Success"
}
student:
{
    "success": true,
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6InNyaXJhbWt1cmlzZXRpQGdtYWlsLmNvbSIsImlkIjoiNjVkZjBlNjRmYTBkNDQyMzFmOTgyYTA3IiwiYWNjb3VudFR5cGUiOiJTdHVkZW50IiwiaWF0IjoxNzA5MTE3NjYyLCJleHAiOjE3MDkyMDQwNjJ9.-mZs1KjmMwvVredr3bO6ZkbtqL0b7U1kQZ_K_QNqdz0",
    "user": {
        "_id": "65df0e64fa0d44231f982a07",
        "firstName": "sriram",
        "lastName": "Pinikeshi",
        "email": "sriramkuriseti@gmail.com",
        "accountType": "Student",
        "active": true,
        "approved": true,
        "additionalDetails": {
            "_id": "65df0e64fa0d44231f982a05",
            "gender": null,
            "dateOfBirth": null,
            "about": null,
            "contactNumber": null,
            "__v": 0
        },
        "courses": [],
        "image": "https://api.dicebear.com/5.x/initials/svg?seed=sriram Pinikeshi",
        "courseProgress": [],
        "createdAt": "2024-02-28T10:43:48.397Z",
        "updatedAt": "2024-02-28T10:43:48.397Z",
        "__v": 0,
        "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6InNyaXJhbWt1cmlzZXRpQGdtYWlsLmNvbSIsImlkIjoiNjVkZjBlNjRmYTBkNDQyMzFmOTgyYTA3IiwiYWNjb3VudFR5cGUiOiJTdHVkZW50IiwiaWF0IjoxNzA5MTE3NjYyLCJleHAiOjE3MDkyMDQwNjJ9.-mZs1KjmMwvVredr3bO6ZkbtqL0b7U1kQZ_K_QNqdz0"
    },
    "message": "User Login Success"
}
_____________________________________________
RESET PASSWORD:
send reset mail -> check mail -> click on it -> get the token from the url

sending link to mail : post :{BASE_AUTH}/reset-password-token
body: { "email" : "sriramkuriseti@gmail.com"
response : { "success" :true, message : " otp reset mail sent successfully check your mail to reset it" }

resetting password through token : post : {BASE_AUTH}/ reset-password
body :{
    "password" : "divyasri",
    "confirmPassword" : "divyasri",
     "token" : "09d5e59dc9bd54e5992b21419861b32867ece165"
}
response :{
    "success": true,
    "message": "Password Reset Successful"
}
_________________________________________________

Profile :
Updating Display Picture :
put : {BASE_PROFILE"/updateDisplayPicture
body: as form -data with value type as file
key:displayPicture
value:passpic.jpg

response :
{
    "success": true,
    "message": "Image Updated successfully",
    "data": {
        "_id": "65df0e64fa0d44231f982a07",
        "firstName": "sriram",
        "lastName": "Pinikeshi",
        "email": "sriramkuriseti@gmail.com",
        "password": "$2b$10$QH3wbcRP9OassyhdmFD6fOJ9wnCwAqPOL8LwFa2lS.SKXPpCxOwM2",
        "accountType": "Student",
        "active": true,
        "approved": true,
        "additionalDetails": "65df0e64fa0d44231f982a05",
        "courses": [],
        "image": "https://res.cloudinary.com/dbblwmol1/image/upload/v1709118379/Upload/dilof0imqt5cymemnjxu.jpg",
        "courseProgress": [],
        "createdAt": "2024-02-28T10:43:48.397Z",
        "updatedAt": "2024-02-28T11:06:25.147Z",
        "__v": 0
    }
}

Updating the profile[additional details]
put :{BASE_PROFILE}/updateProfile
body :
{

    "about" : "Enthusiast passionate coder",
    "contactNumber" : "6302317026",
    "dateOfBirth" : "25.07.2002"
}
response :
{
    "success": true,
    "message": "Profile updated successfully",
    "profile": {
        "_id": "65df0e64fa0d44231f982a05",
        "gender": null,
        "dateOfBirth": "25.07.2002",
        "about": "Enthusiast passionate coder",
        "contactNumber": 6302317026,
        "__v": 0
    }
}

Getting the current logged in UserDetails :
get:{BASE_PROFILE}/getUserDetials
response:
{
    "success": true,
    "message": "User Data fetched successfully",
    "data": {
        "_id": "65df0e64fa0d44231f982a07",
        "firstName": "sriram",
        "lastName": "Pinikeshi",
        "email": "sriramkuriseti@gmail.com",
        "password": "$2b$10$QH3wbcRP9OassyhdmFD6fOJ9wnCwAqPOL8LwFa2lS.SKXPpCxOwM2",
        "accountType": "Student",
        "active": true,
        "approved": true,
        "additionalDetails": {
            "_id": "65df0e64fa0d44231f982a05",
            "gender": null,
            "dateOfBirth": "25.07.2002",
            "about": "Enthusiast passionate coder",
            "contactNumber": 6302317026,
            "__v": 0
        },
        "courses": [],
        "image": "https://res.cloudinary.com/dbblwmol1/image/upload/v1709118379/Upload/dilof0imqt5cymemnjxu.jpg",
        "courseProgress": [],
        "createdAt": "2024-02-28T10:43:48.397Z",
        "updatedAt": "2024-02-28T11:06:25.147Z",
        "__v": 0
    }
}

