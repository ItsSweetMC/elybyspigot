![logo111](https://github.com/user-attachments/assets/ff7cee43-4cf9-4443-b6b0-f5c961305aae)

---

# ElyBySpigot

**A Spigot fork that uses Ely.by authentication instead of Mojang's system.**

---

## Overview

ElyBySpigot is a prebuilt fork of Spigot that replaces Mojang's authentication system with Ely.by's custom **authlib**. This allows players with Ely.by accounts to log in securely to your server while retaining online mode functionality.

---

## How It Works

ElyBySpigot interacts with Ely.by's services to authenticate users. Here are key API endpoints used:

> **UUID by Username**  
Retrieve the UUID associated with a given username.

- **Request:**
  ```http
  GET /api/users/profiles/minecraft/{username}
  ```
- **Response:**
  ```json
  {
    "id": "ffc8fdc95824509e8a57c99b940fb996",
    "name": "ErickSkrauch"
  }
  ```

> **Username History by UUID**  
Retrieve all usernames associated with a specific UUID.

- **Request:**
  ```http
  GET /api/user/profiles/{uuid}/names
  ```
- **Response:**
  ```json
  [
    {
      "name": "Admin"
    },
    {
      "name": "ErickSkrauch",
      "changedToAt": 1440707723000
    }
  ]
  ```

For more details, see the [Ely.by API Documentation](https://docs.ely.by/en/api.html).

---

## Installation

1. **Download ElyBySpigot**  
   Get the latest prebuilt version from the [Releases](https://github.com/ItsSweetMC/elybyspigot/releases) page.

2. **Place the Server in Your Directory**  
   Add the downloaded server `.jar` file to your server directory.

3. **Run and Stop the Server**  
   Start the server once, then stop it to generate configuration files.

4. **Modify `server.properties` File**  
   Open the `server.properties` file and set:  
   ```properties
   enforce-secure-profile=false
   ```  
   This enables chat support.

5. **Start the Server**  
   Launch the server again. You can now join using your Ely.by account.

---

## Features

- **Custom Authentication:** Supports Ely.by accounts for secure login.  
- **Chat Support:** Fully functional chat with the required secure profile adjustments.  
- **Spigot Compatibility:** Operates just like traditional Spigot, with minimal modifications.  

---

## Debugging and Support

If you run into any issues, watch this video where I troubleshoot common bugs:  
[Debugging ElyBySpigot](https://youtu.be/f3N10ql_BEM)

---

Feel free to report issues or contribute to the project on GitHub!
