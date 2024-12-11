# AI Models Payment API

This API allows you to pay for and access powerful AI models using Bitcoin over the Lightning Network.

- **No subscriptions**
- **Pay only for what you use**
- **Your data remains private**

---

## Introduction

This API allows you to easily integrate with AI models via the Lightning Network, enabling fast, secure, and private payments for accessing AI services. The API supports a range of powerful AI models such as OpenAI, xAI, and Gemini, allowing you to make payments in Bitcoin and access the models with ease. The combination of the Lightning Network's low transaction fees and the flexibility of these AI models makes this API an ideal solution for applications that need high-performance models with seamless payment integration.  
[Learn more about Lightning Network](https://lightning.network).

---

## AI Models Available

| **Model Name** | **Available Versions**           |
|----------------|----------------------------------|
| xAI            | grok-beta                       |
| Gemini         | 1.5 Pro, 1.5 Flash              |

---

## Example API Call for Gemini

**Description:**  
When you make a request to the Gemini API, the payment is automatically processed through your own Lightning node. No need to manually handle the payment—just send the request and get the response.

**Endpoint:**  
`POST https://llm-for-test.node.website/gemini`

**Request Headers:**  
- `Authorization`: `Bearer YOUR_ACCESS_TOKEN`
- `Payment-URL`: `https://your-node.node.website/pay`

**Request Body:**  
```json
{
  "prompt": "Write a story about a magic backpack."
}
```

<details>
<summary>JavaScript Example</summary>

```javascript
const axios = require('axios');

axios.post('https://llm-for-test.node.website/gemini', {
  "prompt": "Write a story about a magic backpack." 
}, {
  headers: {
    'Authorization': 'Bearer YOUR_ACCESS_TOKEN',
    'Payment-URL': 'https://your-node.node.website/pay'
  }
}).then(response => console.log(response.data))
  .catch(error => console.error(error));
```
</details>

<details>
<summary>Python Example</summary>

```python
import requests

url = "https://llm-for-test.node.website/gemini"
headers = {'Authorization': 'Bearer YOUR_ACCESS_TOKEN', 'Payment-URL': 'https://your-node.node.website/pay'}
data = {"prompt": "Write a story about a magic backpack."}

response = requests.post(url, headers=headers, json=data)
print(response.json() if response.status_code == 200 else f"Error: {response.status_code}")
```
</details>

<details>
<summary>cURL Example</summary>

```bash
curl --location 'https://llm-for-test.node.website/gemini' \
--header 'Authorization: Bearer YOUR_ACCESS_TOKEN' \
--header 'Payment-URL: https://your-node.node.website/pay' \
--data '{
  "prompt": "Write a story about a magic backpack."
}'
```
</details>
