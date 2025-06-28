<!-- ctrl + shift + p              > Markdown PDF : Export Pdf        -->
<p align="center">
  <img src="A.png" alt="Logo" width="150" style="border-radius: 50%; border: 2px solid #ccc;"/>
</p>
<h1 align="center">🛡️ Smart Contract Vulnerability Report</h1>

---

### 📛 Vulnerability Title  
Out of Gas error with Update Whitelist & 
Lack of Input Validation 

---

### 🗂 Report Type
**Smart Contract**

---

### 🎯 Target
🔗 [GitHub](https://vscode.blockscan.com/)

---
### 🗒️Asset
**SmartContractName.sol**

---

### 🚨Rating
<table>
  <tr>
    <td style="color:red"><strong>Severity: Critical 🔥</strong></td>
    <td style="color:red"><strong>Impact: Low
l 🔥</strong></td>

  </tr>
</table>


---

### 📄 Description

For updating the whitelist, due to the lack of input size restrictions, the function cannot handle more than **840** addresses. If **841** or more addresses are provided, it results in an **out-of-gas error** and the transaction reverts. This causes the function to stop working (locked). This issue is caused by the absence of proper limits on the input array size.

The function responsible for adding or removing addresses from the whitelist lacks proper validation checks. It does not prevent invalid addresses, such as the zero address (address(0)), from being added or removed. Additionally, there is no mechanism to detect or prevent duplicate addresses.

---

### 🧨 Impact

- This bug can effectively disable the function by passing a large input array, leading to a complete ``lock`` of its execution. As a result, the protocol’s security mechanism that relies on this function (such as whitelist control or pause/unpause capability) becomes entirely non-functional.

---

### 🔍 Vulnerability Details

```solidity


```
---

### 🧪 Proof of Concept (PoC)

foundry test
```solidity 




```

---

### How to fix it (Recommended)

```solidity



```
---

### 🔗 References
🔗 [vscode.blockscan](https://vscode.blockscan.com/ethereum/)
🔗 [etherscan](https://etherscan.io/)



