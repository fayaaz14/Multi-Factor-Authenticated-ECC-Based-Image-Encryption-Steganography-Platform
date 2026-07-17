## Multi-Factor-Authenticated-ECC-Based-Image-Encryption-Steganography-Platform
An advanced, highly secure, and lightweight image protection system. This platform combines Elliptic Curve Cryptography (ECC) with Least Significant Bit (LSB) Steganography to encrypt sensitive target images (such as medical X-rays) and embed them invisibly within standard carrier images. The application features a real-time security analytics dashboard, Multi-Factor Authentication (MFA), and secure automated audit logging.
📌Features:
1. Multi-Factor Authentication (MFA)Secure administrative sign-in portal requiring username, password, and Time-Based One-Time Password (TOTP) verification.  Prevent unauthorized encryption, decryption, or log tampering at the entry point.  
2. Dual-Layer Security: ECC + LSB SteganographyECC (brainpoolP256r1): Generates ephemeral, high-strength keys using Elliptic Curve Diffie-Hellman (ECDH) key exchange.  Byte-Level XOR Scrambling: Encrypts the raw image bytes using a key derived from the ECDH shared secret.  LSB Steganography: Embeds the encrypted byte payload directly into the least significant bits of an optional carrier image. This produces a normal-looking Stego Image to prevent visual detection (covert communication).  
3. Real-Time Security Analytics & Integrity ChecksSHA-256 Fingerprinting: Automatically calculates and compares cryptographic hashes to detect any form of tampering.  Advanced Metrics Evaluation: Computes and displays structural security scores:Mean Squared Error (MSE): Measures the degree of structural modification.  Peak Signal-to-Noise Ratio (PSNR): Gauges image distortion strength to evaluate encryption efficacy.  Information Entropy: Verifies that the scrambled payload approaches maximum randomness (8.0). 
4. Automated Audit Logging & Key VaultingEvery operations cycle is registered in a secure log viewer, ensuring complete traceability.  Automatically archives derived keys in a secure key vault categorized by timestamp and file identity
Application Workflows:
🛡️ Multi-Factor Secure Sign-In
Provides gatekept access for authorized administrators using integrated TOTP tokens.
<img width="1077" height="506" alt="Screenshot 2026-04-29 212611" src="https://github.com/user-attachments/assets/10cd6e95-b654-40a4-b707-0b00068757d0" />
📥 Image Encryption & Embedding Workspace
Allows the user to upload a sensitive "Target Image" alongside an optional "Carrier Image". The platform encrypts the target and hides it inside the carrier using LSB insertion.
<img width="1078" height="549" alt="Screenshot 2026-04-29 212620" src="https://github.com/user-attachments/assets/c72100a8-5a42-4dcb-bb6f-d59bdb6ef088" />
🔓 Payload Extraction & Decryption Workspace
Reverses the process by parsing a uploaded Stego PNG file, extracting the LSB payload, and performing ECC decryption to recover the original target image losslessly.
<img width="1150" height="532" alt="Screenshot 2026-04-29 212630" src="https://github.com/user-attachments/assets/5d18c311-acf2-4633-8e55-616a958a88e9" />
📈 Integrity & Security Metrics Dashboard
Evaluates the mathematical robustness of the encryption routine, measuring MSE, PSNR, and Shannon Entropy.
<img width="1199" height="513" alt="Screenshot 2026-04-29 212642" src="https://github.com/user-attachments/assets/69d7c2c6-435c-4f47-9ffb-74d9e4843980" />
 Tech StackFront-end Framework: 
 Streamlit (Python-based web platform)  
 Cryptographic Core: TinyEC (utilizing the brainpoolP256r1 elliptic curve), PyCryptodome 
 Image Processing: Pillow (PIL - Python Imaging Library), NumPy 
 MFA Integration: PyOTP (Time-based OTP generation) 
