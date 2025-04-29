# 🧠 OpenAI Chat Completion Example (Python)

This project is a minimal example demonstrating how to use the official **OpenAI Python SDK** to interact with a GPT model (`gpt-3.5-turbo`) for generating code responses.

---

## 🚀 What It Does

The script sends a prompt to GPT-3.5 Turbo asking it to write a simple "Hello World" program in Python. The system role is set to instruct the model to respond as an experienced programmer and return clean, high-quality code only.

---

## 📦 Requirements

Install the official OpenAI SDK:

```bash
pip install openai
```

---

## 🔐 API Key Configuration

Before running the script, make sure your OpenAI API key is set as an environment variable:

### On Linux/macOS:

```bash
export OPENAI_API_KEY="your_api_key_here"
```

### On Windows (PowerShell):

```powershell
$env:OPENAI_API_KEY="your_api_key_here"
```

---

## 📄 Example Code

```python
from openai import OpenAI

client = OpenAI()

completion = client.chat.completions.create(
    model="gpt-3.5-turbo",
    max_tokens=200,
    temperature=0.1,
    messages=[
        {"role": "system", "content": "Você é um experiente programador. Retorne apenas códigos limpos e de qualidade."},
        {"role": "user", "content": "Escreve um código de Hello World em Python."}
    ]
)

print(completion.choices[0].message.content)
```

---

## 📤 Output Example

```
print("Hello, World!")
```

---

## 📌 Notes

- The `temperature=0.1` ensures that responses are consistent and deterministic.
- You can modify the prompt or system instructions to generate code in other languages or styles.
