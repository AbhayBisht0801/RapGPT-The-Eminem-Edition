
---

## 🧠 Eminem-Style Rap Lyrics Generator (Fine-Tuned LLM)

### 🚀 Model Name: `em_rap_model`
📍 Hugging Face: https://huggingface.co/ababhay08/em_rap_model

### 🔥 Overview
This project features a fine-tuned Language Model (LLM) trained to generate rap lyrics in the style of **Eminem**, inspired by his intricate rhymes, emotional depth, and socially conscious themes. Leveraging powerful transformer architectures, the model takes a title or prompt as input and outputs original rap verses that reflect the intensity, flow, and storytelling Eminem is known for.

---

### 🧾 Features
- ✅ **Fine-tuned on Eminem’s lyrical patterns** using prompt-based training.
- 🎤 **Generates creative rap verses** with emotional depth, rhyme schemes, and wordplay.
- 📝 Input a custom title or theme and receive an original rap lyric.
- 🌐 Ready for integration into apps, websites, and creative writing tools.

---

### 📚 Training Details
- **Base Model**: `unsloth/llama-3.2-3b-instruct-unsloth-bnb-4bit` or similar (you can change this based on what you used).
- **Dataset**: Instruction-style dataset with prompts like `Write a rap like Eminem titled Enemies`.
- **Training Method**: Fine-tuning with supervised learning on synthetic rap instruction-response data.
- **Epochs**: (Add how many you trained, e.g., 3 epochs)
- **Loss**: (Add your final training loss if available)


---
---
### For Inferencing this model
```python
if True:
  model,tokenizer=FastLanguageModel.from_pretrained(
      model_name='ababhay08/em_rap_model',
      max_seq_length=max_seq_length,
      dtype=dtype,
      load_in_4bit=load_in_4bit,
  )
  FastLanguageModel.for_inference(model)
  prompt = f"### Instruction:\nWrite a rap like Eminem titled Enemies\n\n### Response:\n"
  inputs = tokenizer([prompt], return_tensors="pt").to("cuda")

  outputs = model.generate(
      input_ids=inputs.input_ids,
      attention_mask=inputs.attention_mask,
      max_new_tokens=300,
      do_sample=True,  # important for creativity
      top_k=50,        # control diversity
      top_p=0.95,
      temperature=1.0,
      repetition_penalty=1.2,
  )
  response = tokenizer.decode(outputs[0], skip_special_tokens=True)
  print(response)
```
    

---

### 🎯 Intended Use
This model is designed for:
- 🎙️ Rap lyric inspiration and content creation
- 🎧 AI-powered creative tools for musicians and songwriters
- 🧪 Experimentation with stylistic generation from language models

