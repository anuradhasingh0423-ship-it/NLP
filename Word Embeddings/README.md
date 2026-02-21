<img width="1280" height="791" alt="image" src="https://github.com/user-attachments/assets/19a73613-e40d-48b6-a6d7-c6ce7bca08ec" />
<img width="1299" height="584" alt="image" src="https://github.com/user-attachments/assets/7745d459-95c9-4f92-b1fc-249d94f62878" />
<img width="1315" height="724" alt="image" src="https://github.com/user-attachments/assets/2cf89ffe-a57b-4843-99b0-34e1eedc2825" />
<img width="1270" height="678" alt="image" src="https://github.com/user-attachments/assets/6fd63bb7-ab6d-4b72-ae9b-2360b5500224" />
<img width="1231" height="480" alt="image" src="https://github.com/user-attachments/assets/e8ff285a-068d-4e63-b51a-84976cae8203" />
<img width="1201" height="655" alt="image" src="https://github.com/user-attachments/assets/26a021b4-0ffb-4052-80fb-4815ff19ae7e" />
<img width="1287" height="725" alt="image" src="https://github.com/user-attachments/assets/4e90773b-9a1c-45dd-ae77-0196d9197f10" />
<img width="1305" height="761" alt="image" src="https://github.com/user-attachments/assets/d8733690-a858-456b-815d-62708670daa9" />
<img width="1230" height="769" alt="image" src="https://github.com/user-attachments/assets/31215bd6-ee39-4ed6-92bd-9a789eae9bfe" />
<img width="1288" height="749" alt="image" src="https://github.com/user-attachments/assets/459d8a4e-a0a3-4ad9-b0b7-569ce8af0a90" />
<img width="793" height="735" alt="image" src="https://github.com/user-attachments/assets/5757def0-10f5-48c1-8d9b-56edc8173927" />
<img width="1246" height="709" alt="image" src="https://github.com/user-attachments/assets/a751267a-b880-4da0-a318-5549e0d5e190" />
<img width="1233" height="675" alt="image" src="https://github.com/user-attachments/assets/73fb0692-ad39-468a-957f-9ab423de331c" />

import torch

import torch.nn as nn

import torch.optim as optim


# Define CBOW model

class CBOWModel(nn.Module):

    def __init__(self, vocab_size, embed_size):
    
        super(CBOWModel, self).__init__()
        
        self.embeddings = nn.Embedding(vocab_size, embed_size)
        
        self.linear = nn.Linear(embed_size, vocab_size)
        

    def forward(self, context):
    
        context_embeds = self.embeddings(context).sum(dim=1)
        
        output = self.linear(context_embeds)
        
        return output

context_size = 2

raw_text = "word embeddings are awesome"

tokens = raw_text.split()

vocab = set(tokens)

word_to_index = {word: i for i, word in enumerate(vocab)}

data = []

for i in range(2, len(tokens) - 2):

    context = [word_to_index[word] for word in tokens[i - 2:i] + tokens[i + 1:i + 3]]
    
    target = word_to_index[tokens[i]]
    
    data.append((torch.tensor(context), torch.tensor(target)))

# Hyperparameters

vocab_size = len(vocab)

embed_size = 10

learning_rate = 0.01

epochs = 100

# Initialize CBOW model

cbow_model = CBOWModel(vocab_size, embed_size)

criterion = nn.CrossEntropyLoss()

optimizer = optim.SGD(cbow_model.parameters(), lr=learning_rate)


# Training loop

for epoch in range(epochs):

    total_loss = 0
    
    for context, target in data:
    
        optimizer.zero_grad()
        
        output = cbow_model(context)
        
        loss = criterion(output.unsqueeze(0), target.unsqueeze(0))
        
        loss.backward()
        
        optimizer.step()
        
        total_loss += loss.item()
        
    print(f"Epoch {epoch + 1}, Loss: {total_loss}")

# Example usage

word_to_lookup = "embeddings"

word_index = word_to_index[word_to_lookup]

embedding = cbow_model.embeddings(torch.tensor([word_index]))

print(f"Embedding for '{word_to_lookup}': {embedding.detach().numpy()}")

<img width="1243" height="329" alt="image" src="https://github.com/user-attachments/assets/0db82820-96a7-4821-bc8d-0cbf10d85187" />

<img width="1204" height="255" alt="image" src="https://github.com/user-attachments/assets/657aacb9-7e36-4234-8abf-0973e9eeee9d" />
<img width="1258" height="623" alt="image" src="https://github.com/user-attachments/assets/858a5feb-ec9d-49df-a403-e988a93af0ce" />
<img width="1288" height="676" alt="image" src="https://github.com/user-attachments/assets/8c632149-2e74-410a-99db-682b68365432" />
<img width="1004" height="523" alt="image" src="https://github.com/user-attachments/assets/cb06f489-2cab-4320-98c6-d8dd68169893" />
<img width="1224" height="621" alt="image" src="https://github.com/user-attachments/assets/4fbacdd7-6fd0-4a76-9a99-f70bf7346ef2" />
<img width="1231" height="113" alt="image" src="https://github.com/user-attachments/assets/df468c1a-fdee-4c81-bdb4-aa6d1c612d06" />
<img width="1278" height="601" alt="image" src="https://github.com/user-attachments/assets/a71d60b3-541d-4454-8fa4-d9aa8376fb8b" />

