# Lightning Node API

Easily connect and interact with your own Lightning Network node. Lightning Network is the decentralized payment layer for Bitcoin, enabling faster and lower-cost transactions.

## Features

- **Pay:** Send payments via the Lightning Network.
- **Generate Invoice:** Create invoices for incoming payments.
- **View Balance:** Check the balance of your node, including on-chain and channel funds.
- **Get public key:** Get public key of your node

## 1. Pay Invoice

### Description
Pay a Lightning invoice by providing a BOLT11-encoded invoice string, which contains the payment details.

### Endpoint
`POST https://your-node.node.website/pay`

**Request Headers:**  
- `Authorization`: `Bearer YOUR_ACCESS_TOKEN`

### Request Body
```json
{
  "invoice": "lnbcrt110n1.."
}
```

<details>
<summary>JavaScript Example</summary>

```javascript
const axios = require('axios');

axios.post('https://your-node.node.website/pay',
  {
    "invoice": "lnbcrt110n1.."  // Any invoice
  },
  {
    headers: {
      'Authorization': 'Bearer YOUR_ACCESS_TOKEN'
    }
  }
).then(response => console.log(response.data))
  .catch(error => console.error(error));
```
</details>

<details>
<summary>Python Example</summary>

```python
import requests

url = "https://your-node.node.website/pay"
headers = {
    'Authorization': 'Bearer YOUR_ACCESS_TOKEN',
}
data = {
    "invoice": "lnbcrt110n1..."  // Any invoice
}

response = requests.post(url, headers=headers, json=data)
print(response.json())
```
</details>

<details>
<summary>cURL Example</summary>

```bash
curl --location 'https://your-node.node.website/pay' \
--header 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
--data '{
    "invoice": "lnbcrt100n1.."  // Any invoice
}'
```
</details>

### 2. **Generate invoice**

**Description:** Request for generating invoice with given amount in satoshis.  

**Endpoint:**  
`POST https://your-node.node.website/invoice`

**Request Headers:**  
- `Authorization`: `Bearer YOUR_ACCESS_TOKEN`

**Request Body:**  
```json
{
  "amount": 100
}
```

<details>
<summary>JavaScript Example</summary>

```javascript
const axios = require('axios');

axios.post('https://your-node.node.website/invoice',
  {
    "amount": 100
  },
  {
    headers: {
      'Authorization': 'Bearer YOUR_ACCESS_TOKEN'
    }
  }
).then(response => console.log(response.data))
  .catch(error => console.error(error));
```
</details>

<details>
<summary>Python Example</summary>

```python
import requests

url = "https://your-node.node.website/invoice"
headers = {
    'Authorization': 'Bearer YOUR_ACCESS_TOKEN',
}
data = {
    "amount": 100
}

response = requests.post(url, headers=headers, json=data)
print(response.json())
```
</details>

<details>
<summary>cURL Example</summary>

```bash
curl --location 'https://your-node.node.website/invoice' \
--header 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
--data '{
    "amount": 100
}'
```
</details>

### 3. **Get balance**

**Description:** Request to retrieve the balance of LND Node in satoshis.  

**Endpoint:**  
`GET https://your-node.node.website/balance`

<details>
<summary>JavaScript Example</summary>

```javascript
const axios = require('axios');

axios.get('https://your-node.node.website/balance',
  {
    headers: {
      'Authorization': 'Bearer YOUR_ACCESS_TOKEN'
    }
  }
).then(response => console.log(response.data))
  .catch(error => console.error(error));
```
</details>

<details>
<summary>Python Example</summary>

```python
import requests

url = "https://your-node.node.website/balance"
headers = {
    'Authorization': 'Bearer YOUR_ACCESS_TOKEN',
}

response = requests.get(url, headers=headers)
print(response.json())
```
</details>

<details>
<summary>cURL Example</summary>

```bash
curl --location 'https://your-node.node.website/balance' \
--header 'Authorization: Bearer YOUR_ACCESS_TOKEN'
```
</details>

### 3. **Get Public Key**

**Description:** Request to retrieve the public key of your Lightning Node.  

**Endpoint:**  
`GET https://your-node.node.website/pubkey`

<details>
<summary>JavaScript Example</summary>

```javascript
const axios = require('axios');

axios.get('https://your-node.node.website/pubkey',
  {
    headers: {
      'Authorization': 'Bearer YOUR_ACCESS_TOKEN'
    }
  }
).then(response => console.log(response.data))
  .catch(error => console.error(error));
```
</details>

<details>
<summary>Python Example</summary>

```python
import requests

url = "https://your-node.node.website/pubkey"
headers = {
    'Authorization': 'Bearer YOUR_ACCESS_TOKEN',
}

response = requests.get(url, headers=headers)
print(response.json())
```
</details>

<details>
<summary>cURL Example</summary>

```bash
curl --location 'https://your-node.node.website/pubkey' \
--header 'Authorization: Bearer YOUR_ACCESS_TOKEN'
```
</details>

## Support
For assistance, please contact our support team:
📧 Email: support@economy-v1.com
