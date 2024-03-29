# L2B2-Frontend-Path-Assignment-6-Server-Starter-Pack

## Live Link:

Server Live Link [peace_server](https://peace-server-main.vercel.app/).

## Installation:

1. Clone the repository.
2. Install dependencies using `npm install`.
3. Rename `.env.example` to `.env`.
4. Run the server using `npm run dev`.

### Before Pushing Code:

1. Before pushing your code to the remote repository, ensure that you have run the following command in your terminal (Git Bash):
   ```bash
   rm -rf .git
   ```

## Configuration:

- Environment Variables:
  - `PORT`: Port number the server listens on. Default: 3000
  - `MONGODB_URI`: URI for MongoDB database.
  - `JWT_SECRET`: Secret key for JWT token generation.
  - `EXPIRES_IN`: Token expiration time.

## Usage:

- API Endpoints:

  - POST `/api/v1/login`

    - Description: Authenticates user and returns a JWT token.
    - Request:
      ```json
      {
        "email": "example@email.com",
        "password": "password"
      }
      ```
    - Response:
      ```json
      {
        "success": true,
        "message": "User registered successfully"
      }
      ```

  - POST `/api/v1/register`
    - Description: Registers a new user.
    - Request:
      ```json
      {
        "name": "John",
        "email": "example@email.com",
        "password": "password"
      }
      ```
    - Response:
      ```json
      {
        "success": true,
        "message": "Login successful",
        "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6InBoMkBleGFtcGxlLmNvbSIsImlhdCI6MTcwNzg1MDYyMSwiZXhwIjoxNzA3OTM3MDIxfQ.7EahSgmPLPNuZ_T9ok-B6TayWCJVdxPzi_Nx4UfrhvY"
      }
      ```
  - POST `/api/v1/donation`
    - Description: Creating a new donation post.
    - Request:
      ```json
      {
        "image": "Enter Image Link",
        "title": "example",
        "category": "Food",
        "amount": 50,
        "description": "Enter Description About The Donation"
      }
      ```
    - Response:
      ```json
      {
        "success": true,
        "message": "Successfully donation create!",
        "result": {
          "acknowledged": true,
          "insertedId": "65f2ca6c5b6b39e13c4884d2"
        }
      }
      ```
  - GET `/api/v1/donation`
    - Description: Get All donation post.
    - Response:
      ```json
      {
        "success": true,
        "message": "successfully retrieve donation!",
        "data": []
      }
      ```
  - GET `/api/v1/donation/65f2ca6c5b6b39e13c4884d2`
    - Description: Get a single donation post.
    - Response:
      ```json
      {
        "success": true,
        "message": "successfully retrieve clothe!",
        "data": {
          "_id": "65f2ca6c5b6b39e13c4884d2",
          "image": "https://blessingsofhope.com/wp-content/uploads/2019/07/donation-box.jpg",
          "title": "Homeless Shelter Support",
          "category": "Shelter",
          "amount": 40,
          "description": "In the heart of our bustling city, amidst the towering skyscrapers and bustling streets, lies a community often overlooked and underserved—the homeless. These individuals, facing circumstances beyond their control, navigate the harsh realities of life without the basic comforts and securities many of us take for granted. As temperatures drop and winds howl through the alleys, their plight becomes even more urgent. In recognition of their struggles and in solidarity with our fellow human beings, we are launching a Homeless Shelter Support initiative. This endeavor aims to provide essential aid and comfort to those experiencing homelessness, offering a beacon of hope in their darkest hours. At the core of this initiative is a commitment to compassion and empathy. We believe that every person, regardless of their circumstances, deserves dignity, respect, and a safe place to call home. Our homeless shelters serve as sanctuaries, offering warmth, nourishment, and support to those in need."
        }
      }
      ```

- DELETE `/api/v1/donation/65f2ca6c5b6b39e13c4884d2`
- Description: Delete a specific donation post.
- Response:

  ```json
  {
    "success": true,
    "message": "successfully delete donation!"
    "data": {
        "acknowledged": true,
        "deletedCount": 1
    }
  }
  ```

  - POST `/api/v1/donor`
  - Description: Creating a new donor.
  - Request:
    ```json
    {
      "image": "Enter Image Link",
      "name": "example",
      "email": "example@gmail.com",
      "amount": 50
    }
    ```
  - Response:

    ```json
    {
      "success": true,
      "message": "You provided Donation successfully!",
      "result": {
        "acknowledged": true,
        "insertedId": "65f2ca6c5b6b39e13c4884d2"
      }
    }
    ```

  - GET `/api/v1/donor`
    - Description: Get All donor.
    - Response:
      ```json
      {
        "success": true,
        "message": "successfully retrieve donors!",
        "data": []
      }
      ```
  - GET `/api/v1/donation/65f2ca6c5b6b39e13c4884d2`
    - Description: Get a single donation post.
    - Response:
      ```json
      {
        "success": true,
        "message": "successfully retrieve donor!",
        "data": {
          "_id": "65f2ca6c5b6b39e13c4884d2",
          "image": "https://blessingsofhope.com/wp-content/uploads/2019/07/donation-box.jpg",
          "name": "example",
          "email": "example@gmail.com",
          "amount": 40
        }
      }
      ```

- POST `/api/v1/testimonial`

  - Description: Creating a new testimonial.
  - Request:
    ```json
    {
      "image": "Enter Image Link",
      "name": "example",
      "email": "example@gmail.com",
      "amount": 50,
      "testimonial": "This Is Good Website to Donate"
    }
    ```
  - Response:

    ```json
    {
      "success": true,
      "message": "You posted testimonial successfully!",
      "result": {
        "acknowledged": true,
        "insertedId": "65f2ca6c5b6b39e13c4884d2"
      }
    }
    ```

  - GET `/api/v1/testimonial`

    - Description: Get All Testimonail.
    - Response:

      ```json
      {
        "success": true,
        "message": "successfully retrieve testimonial!",
        "data": []
      }
      ```

- POST `/api/v1/volunteer`

  - Description: Creating a new Volunteer.
  - # Request:
        ```json
        {
          "image": "Enter Image Link",
          "name": "example",
          "email": "example@gmail.com",
          "passion": "Student",
          "phoneNumber": "016454150",
          "location": "Dhaka, Bangladesh"
        }
        ```
  - Response:

    ```json
    {
      "success": true,
      "message": "Volunteer Account Created Successfully!",
      "result": {
        "acknowledged": true,
        "insertedId": "65f2ca6c5b6b39e13c4884d2"
      }
    }
    ```

  - GET `/api/v1/volunteer`
    - Description: Get All Volunteer.
    - Response:
      ```json
      {
        "success": true,
        "message": "successfully retrieve Volunteer!",
        "data": []
      }
      ```

- POST `/api/v1/comment`

  - Description: Creating a new comment.
  - # Request:

        ```json
        {
          "image": "Enter Image Link",
          "name": "example",
          "email": "example@gmail.com",
          "comment": "wonderfull",
          "time": "February 26 2024",
        }
        ```

  - Response:

    ```json
    {
      "success": true,
      "message": "Comment Posted Successfully!",
      "result": {
        "acknowledged": true,
        "insertedId": "65f2ca6c5b6b39e13c4884d2"
      }
    }
    ```

  - GET `/api/v1/comment`
    - Description: Get All Comments.
    - Response:
      ```json
      {
        "success": true,
        "message": "successfully retrieve comment!",
        "data": []
      }
      ```

## Dependencies:

- `bcrypt`: Library for hashing passwords.
- `cors`: Express middleware for enabling CORS.
- `dotenv`: Loads environment variables from .env file.
- `express`: Web framework for Node.js.
- `jsonwebtoken`: Library for generating and verifying JWT tokens.
- `mongodb`: MongoDB driver for Node.js.
- `nodemon`: Utility for automatically restarting the server during development.
