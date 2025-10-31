# WaveTip Privacy Policy

**Last Updated:** October 31, 2025  
**Effective Date:** November 1, 2025

## 1. Introduction

WaveTip ("Extension", "we", "us", "our") is a Chrome browser extension that enables Twitch viewers to send cryptocurrency tips to streamers using RLUSD on the XRP Ledger blockchain. We are committed to protecting your privacy and being transparent about how we collect, use, and share your data.

This Privacy Policy explains our data practices. Please read it carefully. If you do not agree with this policy, please do not use WaveTip.

---

## 2. What Data We Collect

WaveTip only collects the minimum data necessary to function. We collect data in two main ways:

### 2.1 Data You Provide Directly

- **Username:** Used to identify your WaveTip account
- **Password:** Used only to encrypt/decrypt your wallet locally; never stored by us (unless hashed for authentication)

### 2.2 Data Collected Automatically

- **Twitch Channel Information:** Streamer channel URLs you visit for tipping
- **Transaction Details:** Amount sent, recipient address, your wallet address, public transaction hash, timestamp
- **Wallet Balance:** Queried from the XRP Ledger
- **Transaction History:** Tips sent from your wallet
- **Browser Information:** Extension version, manifest version

**We explicitly do NOT collect:**

- Your browsing history outside of twitch.tv
- IP address
- Device identifiers
- Cookies or tracking data
- Location data
- Other websites visited
- Keystroke/form data outside the extension

---

## 3. Wallet Creation, Key Handling, and Storage

### 3.1 Creation and Delivery (One-Time Only)

1. WaveTip backend generates a wallet (address + raw seed/private key) and funds it.
2. Backend sets trustline for RLUSD.
3. Backend returns the raw seed/private key and wallet address ONCE to the extension.
4. The backend immediately deletes the seed/private key after this delivery and retains no copy.

### 3.2 Client-Side Encryption and Storage

- The extension receives the raw seed.
- The extension immediately encrypts the seed locally using your password (AES-256-GCM, PBKDF2-SHA512, random IV/salt).
- Only the encrypted seed blob (plus IV and salt) is stored in `chrome.storage.local`.
- The seed is kept unencrypted only temporarily in RAM for transaction signing or wallet unlock.
- **You NEVER see the raw seed or private key in the UI. There is NO export feature.**
- The wallet therefore can only ever be used through WaveTip.

| Data | Storage Location | Security | Accessibility |
|------|---|---|---|
| Raw Seed (unencrypted) | RAM only, short duration | Not persisted | Only for unlock/signing flow |
| Encrypted Seed (AES256+PBKDF2) | chrome.storage.local | AES-GCM + unique IV/Salt | Extension only |
| Wallet Address | chrome.storage.local | Plain text | UI-visible |
| IV, Salt | chrome.storage.local | Random secret | Used for encryption only |
| Password | Never stored; RAM only | Used to derive key | Only known to user |

### 3.3 Key Deletion

- Once delivered, WaveTip backend deletes all private key material.
- Key/custody passes fully to the client extension; WaveTip has zero knowledge after delivery.

---

## 4. How We Use Your Data

### 4.1 Core Functionality

- Account creation and wallet setup
- Enable tipping (sign/send transactions)
- Display balance and transaction history
- Local encryption/decryption for secure storage

### 4.2 Technical Operations

- Update, error logging (no sensitive data in logs)
- Maintain extension compatibility
- Secure session management

### 4.3 Never Used For

- Marketing or ads
- Behavioral tracking
- Selling or sharing data
- Machine learning/AI training
- Credit assessment or lending
- Cross-site tracking

### Limited Use Compliance

WaveTip's use of information received from Chrome APIs adheres to the 
Chrome Web Store User Data Policy, including all Limited Use requirements. 
We do not use collected data for personalized advertising, third-party 
sharing, or any purpose unrelated to providing the tipping feature.

---

## 5. Data Sharing

### 5.1 Shared Data

- **XRP Ledger:** Public wallet address, transaction details (on blockchain, permanent)
- **Twitch.tv:** Page loads needed to show extension UI; never shares wallet or private key

### 5.2 Never Shared

- Raw/unencrypted private key/seed (deleted by backend, never shown to user)
- Encrypted private key (never leaves device)
- Password
- Transaction history with outside advertisers
- Personal info with brokers, analytics, or unlisted third parties

---

## 6. Data Security

### 6.1 Security Measures

- Seed encrypted client-side, never leaves device unencrypted
- Password never transmitted or stored (only used locally for derivation)
- Auto-lock mechanisms and session isolation
- Transactions and sensitive crypto operations never expose raw secrets to network or UI

### 6.2 Risks and Responsibilities

- If your device is compromised by malware or extension hijacks, attackers may recover encrypted seed or intercept password during unlock
- **We cannot recover your wallet if you forget your password or uninstall the extension.**
- **You cannot export your seed or private key, nor use this wallet in another app.**
- Blockchain transactions are permanent and publicly visible

---

## 7. Wallet Portability Limits

- Your wallet is exclusive to WaveTip; there is no seed export, reveal, or interoperability feature.
- You cannot import this wallet elsewhere.
- If you uninstall or lose your extension/device, your funds are lost (unless you can restore encrypted storage and password).

---

## 8. Data Retention & Deletion

- Your seed is cached encrypted as long as you have the extension installed
- When you uninstall, all local data (encrypted seed, transaction history, keys) is erased
- Your wallet address and transactions remain visible forever on the XRP Ledger

---

## 9. User Rights & Choices

- **Access:** You can view balance and transaction history, never private key
- **Delete:** Uninstall extension to erase all local data
- **Portability:** Not possible; wallet can't be exported/use elsewhere
- **Consent:** Using WaveTip means accepting these limits and security tradeoffs

---

## 10. Third-Party Services

- XRP Ledger (public blockchain)
- Twitch.tv (no private wallet data shared)

---

## 11. Children & Age Restrictions

- **Not for users under 18.** We do not knowingly collect data from children. If we become aware a child is using WaveTip, we will take steps to prevent further use.
- WaveTip requires cryptocurrency understanding and involves financial transactions. Users should understand these risks before using this service.

---

## 12. Blockchain & Cryptocurrency Considerations

### 12.1 Blockchain Transparency and Public Visibility

All transactions on the XRP Ledger are permanently recorded and publicly visible on the blockchain. This means:

- **Your wallet address is public** and visible to anyone
- **Transaction amounts are public** - anyone can see how much RLUSD you sent
- **Recipient addresses are public** - anyone can see which streamer received your tip
- **Transaction timestamps are visible** - when you sent each tip is recorded
- **All data is searchable** - anyone can use block explorers like XRPScan to look up your wallet and see your complete tipping history
- **Transactions cannot be reversed or deleted** - once confirmed on the blockchain, the data is permanent and immutable

### 12.2 Linking Your Identity

Because blockchain transactions are transparent:

- If your wallet address becomes associated with your Twitch username (for example, through public discussion or streamer announcements), anyone can link your identity to your tipping history
- Your complete transaction history on that wallet address becomes visible to anyone who knows the connection
- Streamers and their audiences may see your tip amounts and frequency

### 12.3 No Anonymity

WaveTip does not provide anonymity or privacy on the blockchain:

- Your wallet address is permanently linked to all your transactions
- Your Twitch presence may be linked to your wallet address
- Tips are traceable to both you and the recipient indefinitely
- The blockchain maintains this transparency by design

### 12.4 Financial and Cryptocurrency Risks

Using cryptocurrency for tipping involves risks you should understand:

- **Volatility:** RLUSD and XRP values can fluctuate; the value of your tips may change
- **Irreversibility:** Transactions cannot be undone or refunded once sent
- **No chargeback:** Unlike credit cards, there is no dispute resolution or chargeback mechanism
- **Loss of funds:** If you lose access to your WaveTip account, your funds in that wallet become inaccessible
- **Regulatory risk:** Cryptocurrency regulations vary by country and may change, affecting your ability to use WaveTip

---

## 13. International Users & Regulatory Compliance

WaveTip is available globally. However:

- Data is stored locally on your device (where you are located)
- Some countries may have additional privacy regulations (GDPR, CCPA, etc.)
- You are responsible for complying with local laws
- Cryptocurrency regulations vary by jurisdiction
- WaveTip may not be legal or available in all countries

### 13.1 EU Users (GDPR)

If you're in the EU, you have rights under GDPR:

- **Right to Access:** Request a copy of your data by emailing [contact@wavetip.fi](mailto:contact@wavetip.fi)
- **Right to Delete:** Request account/data deletion (see Section 8)
- **Right to Portability:** Your transaction data is yours, but your private key cannot be exported
- **Right to Withdraw Consent:** Stop using the extension
- **Right to Lodge a Complaint:** Contact your national data protection authority

For GDPR inquiries, email [contact@wavetip.fi](mailto:contact@wavetip.fi) with "GDPR REQUEST" in the subject line.

### 13.2 California Users (CCPA)

If you're in California, you have rights under CCPA:

- **Right to Know:** Request what personal information we have about you
- **Right to Delete:** Request data deletion
- **Right to Opt-Out:** Stop using the extension
- **No Sale of Information:** We never sell your data

For CCPA inquiries, email [contact@wavetip.fi](mailto:contact@wavetip.fi) with "CCPA REQUEST" in the subject line.

---

## 14. Limitation of Liability

**You acknowledge and agree that:**

- WaveTip is provided on an "as-is" basis
- We are not responsible for blockchain network failures, delays, or errors
- We cannot recover lost, stolen, or inaccessible wallets
- We cannot reverse or refund blockchain transactions
- We are not liable for third-party service failures (XRP Ledger, Twitch.tv)
- Your use of WaveTip is at your own risk
- We are not responsible for unauthorized access if your device is compromised

---

## 15. Policy Changes & Updates

We may update this privacy policy to reflect changes in our practices, technology, or applicable law. We will notify you of material changes by:

- Updating the "Last Updated" date at the top of this policy
- Posting a notice in the extension
- Requiring your explicit consent if required by law

Your continued use of WaveTip after material changes constitutes acceptance of the updated policy. We encourage you to review this policy periodically for updates.

---

## 16. Contact Us

**For privacy questions, concerns, or requests:**

- **Email:** [contact@wavetip.fi](mailto:contact@wavetip.fi)
- **Response Time:** We aim to respond within 7 business days

**For specific requests:**
- Include "GDPR REQUEST" for GDPR inquiries
- Include "CCPA REQUEST" for CCPA requests
- Include "DATA ACCESS" for data access requests
- Include "ACCOUNT DELETION" for deletion requests

---

## 17. Acknowledgment

**By installing and using WaveTip, you acknowledge that you have read, understood, and agree to this Privacy Policy in its entirety.**

You also confirm that:

- You are at least 18 years old
- You understand the risks of cryptocurrency and blockchain transactions
- You accept full responsibility for protecting your password and device
- You accept that your wallet cannot be recovered if you lose access

---

## 18. TL;DR — Key Points

✅ Wallet seed is generated server-side, sent ONCE to extension  
✅ Extension encrypts the seed and never exports/displays it  
✅ Only encrypted seed (plus IV/salt) stored locally, never in backend  
✅ You cannot export, view, or use your wallet anywhere else  
✅ If you lose your extension/password/device, wallet is lost  
✅ No backend custody after initial delivery  
✅ No data selling, tracking, or advertising  
✅ All blockchain transactions are permanent and public  
⚠️ Lost password = permanent wallet loss  
⚠️ Cryptocurrency volatility and irreversibility apply

---

**Last Updated:** October 31, 2025  
**By using WaveTip, you agree to this Privacy Policy.**
