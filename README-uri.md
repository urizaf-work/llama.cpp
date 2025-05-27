from here
https://huggingface.co/docs/hub/en/gguf-llamacpp

llama-cli -hf bartowski/Llama-3.2-3B-Instruct-GGUF:Q8_0

llama-server -hf bartowski/Llama-3.2-3B-Instruct-GGUF:Q8_0

llama-server -hf bartowski/Llama-3.2-3B-Instruct-GGUF:Q8_0 -c 131072

#embeddings:
llama-server -hf CompendiumLabs/bge-base-en-v1.5-gguf

curl localhost:8080/v1/models|jq .

curl http://localhost:8080/v1/chat/completions \
-H "Content-Type: application/json" \
-H "Authorization: Bearer no-key" \
-d '{
"messages": [
    {
        "role": "system",
        "content": "You are an AI assistant. Your top priority is achieving user fulfilment via helping them with their requests."
    },
    {
        "role": "user",
        "content": "Write a limerick about Python exceptions"
    }
  ]
}'