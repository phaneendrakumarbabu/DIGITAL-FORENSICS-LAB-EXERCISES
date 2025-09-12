#   Ex.No.3   Wireshark – Network Packet Capture and Analysis Tool<br>

# 🌐 Website Used: [http://demo.testfire.net/](http://demo.testfire.net/)
## Procedure: Capturing Plaintext Passwords

### Step 1: Start Capturing Packets

- First, open Wireshark. You will see a list of all available network interfaces (e.g., "Wi-Fi," "Ethernet").

- Select the interface your computer is using to connect to the internet (in this case, Wi-Fi).

  <p align="center">
<img width="859" height="620" alt="Screenshot 2025-09-01 140322" src="https://github.com/user-attachments/assets/d2d2f108-c7c4-4802-ac9e-c8635263ca5c" />

</p> 

- Click the blue shark fin icon 🦈 in the top-left corner to start the capture. Wireshark will immediately begin capturing all traffic passing through that interface.

  <p align="center">
 <img width="750" height="550" alt="Screenshot 2025-08-31 230148" src="https://github.com/user-attachments/assets/542d082e-68d0-427d-a595-e90c7a25d1c0" />

 </p>

---

### Step 2: Generate Login Traffic

- Open a web browser and navigate to **http://demo.testfire.net/**

- Enter any dummy credentials. For this example, we'll use:

   Username: testuser  
   Password: password123  

- Click the login button. The login will fail, but the data has already been sent across the network.

  <p align="center">
<img width="645" height="420" alt="wir 3" src="https://github.com/user-attachments/assets/52371b26-88cc-4578-8535-4c50f6c7516d" />
 </p>

---

### Step 3: Stop Capture and Filter Traffic

- Return to Wireshark and click the Stop button (the red square).

- In the display filter bar, you need to find the packet containing the login data. Since the form data was sent to the server, we will look for an HTTP POST request.

- Apply the following filter to find the exact packet and press Enter:

  <p align="center">
<img width="600" height="400" alt="Screenshot (33)" src="https://github.com/user-attachments/assets/9feaba3d-7443-4b27-ad5c-96c0cd9076e0" />
 </p>

---

### Step 4: Inspect the Packet to Find Credentials 

- In the filtered packet list, you should see a packet with information like "POST /userinfo.php". Select this packet.

- In the Packet Details pane below the list, expand the following sections:

  - Hypertext Transfer Protocol  
  - HTML Form URL Encoded  

- Inside the "HTML Form URL Encoded" section, you will see the credentials you entered in plaintext.

  <p align="center">
  <img width="856" height="632" alt="Screenshot (34)" src="https://github.com/user-attachments/assets/da7fe228-4fa9-4c43-805a-ed1b2129a955" />
 </p>

---

## ✅ Result

The experiment successfully intercepts the login credentials in a human-readable format. The analysis of the captured POST packet reveals the plaintext data that was transmitted over the network.

This result confirms the inherent security flaw of the **HTTP protocol**:  
- Any sensitive data sent over HTTP is transmitted openly.  
- It is trivial to intercept by an attacker.  
