# Lab 5: TryHackMe Vulnerable Machine

**Room:** Overheard at Breakfast (OSINT)  

---

## 1. Target
- **Target Handle / Name:** `Lambo!` (`@Lambo` / `Lam-boh`)
- **Associated Location:** Byte Lotus Hotel / Resort
- **Discovered Email:** `lambobytelotushotel@gmail.com`
- **Platform Clue:** Free profile/link-in-bio service starting with **G** (**Gravatar**), with claims that everything was wiped.

  <img width="803" height="853" alt="Screenshot 2026-11-21 144337" src="https://github.com/user-attachments/assets/20a5993d-3d83-4fe8-98ad-05345662b6bf" />


---

## 2. Methodology Used
- **Conversation & Clue Extraction (SOCMINT):** Inspected the chat transcript to extract actionable identifiers, contact details, and platform hints.
- **Cryptographic Hash Pivoting (OSINT):** Computed MD5 and SHA-256 hashes of the target email address to query Gravatar profiles.
- **Data Encoding & Decoding:** Identified a Base64-encoded payload in the profile bio and decoded it to retrieve the plaintext flag.

---

## 3. Step-by-Step Walkthrough
1. **Download the Task File in Room Access and Analyze The Conversation:**
   
   Read through the chat between **Ponzi - Influencer** and **Lambo!** to capture `Byte Lotus`, `lambobytelotushotel@gmail.com`, and the hint regarding a tool starting with `G`.

   <img width="943" height="640" alt="Screenshot 2026-11-21 144414" src="https://github.com/user-attachments/assets/212c7689-edc3-4d57-8cd0-0592ca488c57" />
   
2. **Recognize The Clue In The Conversation By Lambo:**

   <img width="942" height="147" alt="image" src="https://github.com/user-attachments/assets/e618b2ce-4484-4c6a-82ce-deed6029a1d3" />


3. **Generate Email Hashes & Locate Gravatar Profile:**

   <img width="1912" height="847" alt="image" src="https://github.com/user-attachments/assets/ff50998b-a661-44fc-8f8a-52343dfe4e7b" />
   

   <img width="1882" height="738" alt="Screenshot 2026-11-21 152410" src="https://github.com/user-attachments/assets/24e84020-0457-42bc-b21c-436a0a65eff2" />
   
   ```bash
   echo -n "lambobytelotushotel@gmail.com" | md5sum
   echo -n "lambobytelotushotel@gmail.com" | sha256sum
   
4. **Decode the Base64 string You Found In The Profile Bio:**
   

   Command Executed: 'echo | base64 -d'

   <img width="767" height="195" alt="Screenshot 2026-11-21 153220" src="https://github.com/user-attachments/assets/834bf3f2-6d82-44bb-b34d-5b6d1c13c487" />

6. **Copy the Decoded Flag, Paste It Into TryHackMe, And Submit:**

   <img width="1070" height="148" alt="Screenshot 2026-11-21 154344" src="https://github.com/user-attachments/assets/9e6c6f13-c25d-4276-adef-213506a787d0" />

   
