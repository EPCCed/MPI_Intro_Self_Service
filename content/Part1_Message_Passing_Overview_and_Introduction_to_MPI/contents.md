# Introduction to the Message Passing Programming Model and MPI

In this section, we first cover message-passing at a conceptual level, and illustrate the basic concepts using a traffic-modelling thought experiment. We then introduce the very basics of MPI and how to develop real MPI programs on ARCHER2 or Cirrus. This is enough information to write simple "Hello World" programs in MPI, and get to grips with compiling and running your own parallel programs. This block also includes the main [MPI Exercise Sheet](https://learn-eu-central-1-prod-fleet01-xythos.content.blackboardcdn.com/5d1b15b77a8ac/10690687?X-Blackboard-S3-Bucket=learn-eu-central-1-prod-fleet01-xythos&X-Blackboard-Expiration=1689940800000&X-Blackboard-Signature=WlhNL9BkPaiiBup%2FmGRizAUIVElD3VbxxeZ3hlQpA5w%3D&X-Blackboard-Client-Id=301835&X-Blackboard-S3-Region=eu-central-1&response-cache-control=private%2C%20max-age%3D21600&response-content-disposition=inline%3B%20filename%2A%3DUTF-8%27%27MPP-exercises.pdf&response-content-type=application%2Fpdf&X-Amz-Security-Token=IQoJb3JpZ2luX2VjEDAaDGV1LWNlbnRyYWwtMSJHMEUCIARGwZydIL9bDYn%2BMqMbQIPg%2Bh%2F9lz%2F%2F3jusmuTeTlC3AiEAjoINEZnVrtLDv7UZB5VOH0B23zPF4X%2BRhim6OTkvFJYqxgUIuf%2F%2F%2F%2F%2F%2F%2F%2F%2F%2FARADGgw2MzU1Njc5MjQxODMiDGH5CwddKLQjIlw%2B1SqaBVn%2BRAfc1VboU3ezLv%2FEwWOPWIlH6OS6gDauiXLalaoZPFczz0cwpvPIXlBt1Z34WLaUPE3LOGQFA8GT9wFW27VQXGUxYtUuNOP7vH33r%2Byns5ePE8%2BhvtV24%2BT3MNUAxvwRAfy2tjAo6VTGFWdcPkhjc7dCZ0Il1ppUL9d2zlWTYQXp1q6J8HJCA7oiFxXTtJjEffFhAD%2FOQR1NTWpKAxtYBpw36IjvKhlaKYAJ1x3UcEGz1aPCYj3hNe6u9cJKIrzX01gw%2FZziFX1C0OgLIEv8W4sEZhJ2sM92M90Gwjfy%2BHfVF0h9RoXo3L2wYWqDKiwLX7kHlQMKPew1Xk9p%2FF3RM0W2GMzHUqmnEyTUgKQbZbsQ1Rg1PBtUO4RCTz8iMlwc23vJMbEwY20mjpFSsKYDbjFrBSBIV2i9Ox7Wi%2FcgjqifDAOGKmpR7eGhoJXcDRod5AVfFp591kUNZyj6RY2VjOXiPZQHqz0I8YgPEnGtjI3Mor6xyhcUo8oSP8%2BCG7EEuWMr0Eyhwe1UMNqhP51tYHlDkw5SWPQHG%2F0PTU%2B8xGvujFVvv%2FyWZkMf%2BGAJM5vbNzUPvbt5OOjwhrooofDUdys2Ykc4Gf84pSbjiiRr2K7fzZW2ZFdmonhJGxiz3TxjBXIAjV54WarvUkYRubwzjr9EfQiJYW7w%2BbDFwvbo6vA%2BPgA6y0bXPnABPJaM0FUVfWRLeYgrh9pSinI9xRCrFcGdSO%2FL7dJuSVoDPfrw5cLCl83F%2BH9VBlKAnzBTBJA5pdE1089eWjTQBIyKCXuQGTs%2BIZpS3Ndwb9lzaFMD8ltRqlmbkePN1sS260I4643YkAyO5s4UpuFwogrsBaqiPph1kGEyUdIR8zZ%2FEu66mU4eAQgOqx3G6zDo6uilBjqxAUI1gf2VsjMEh4tal%2F0gtMW46QUYnzHrk5iSF%2FZwEPWFmBBei5CndC865T3IEOj33y6SZkkfzY4gyYdOKMdznnczryflmq%2Bv%2FEmU1DkYNOiBuQPbG8jKXuSEMy1SD8cBKy2BBIRIBzJt%2BDTPcsuKqdebVbFBLcVvKr46m54pbC3t8JgIojCJXSFWoGqYvIGv2t2xK7ceO4f8J3TCkTbZ8q56McsKNQPXzKFW9jrvw5CJog%3D%3D&X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Date=20230721T060000Z&X-Amz-SignedHeaders=host&X-Amz-Expires=21600&X-Amz-Credential=ASIAZH6WM4PLRMBHRR7H%2F20230721%2Feu-central-1%2Fs3%2Faws4_request&X-Amz-Signature=7ecc552df4ac4330b768ffaa1d8de1d0f6e758e1d4c222b51d803fb077cb1ea9) which we will use for the whole course, although only Exercise 1 is relevant here.


---

## Objectives of this section

After completing this section the student will gain:

- a thorough understanding of the Message Passing programming model
- familiarity with core function define by Message Passing Interface (MPI) standard
- experience implementing, comiling, linking and running simple MPI programs

---

## Message Passing Programming Model


## Traffic Modelling


## Introduction to MPI Programming

