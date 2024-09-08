import openai

# Set your OpenAI API key
openai.api_key = "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"

text = input(str("pokemon nature: "))

# Define the text you want to analyze or interact with


# Make a request to the OpenAI GPT-3.5 API
response = openai.ChatCompletion.create(
    model="gpt-3.5-turbo-0125",
    messages=[
        # prompt
        {"role": "system", "content": "ตอบชื่อโปเกม่อน1ตัวเป็นชื่อภาษาอังกฤษ และร่างพัฒนาทั้งหมดที่มี ถ้าไม่มีไม่เป็นไร"},
        {"role": "user", "content": text}
    ]
)

# Extract the response text
response_text = response['choices'][0]['message']['content'].strip()

print("Response from GPT-3.5:", response_text)
