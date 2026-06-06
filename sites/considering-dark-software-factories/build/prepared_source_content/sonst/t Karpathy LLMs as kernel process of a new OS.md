https://x.com/karpathy/status/1707437820045062561

[[person - Andrej Karpathy]]

With many pieces dropping recently, a more complete picture is emerging of LLMs not as a chatbot, but the kernel process of a new Operating System. E.g. today it orchestrates:
- Input & Output across modalities (text, audio, vision)
- Code interpreter, ability to write & run programs
- Browser / internet access
- Embeddings database for files and internal memory storage & retrieval
...
[[LLM OS]]

A lot of computing concepts carry over. Currently we have single-threaded execution running at ~10Hz (tok/s) and enjoy looking at the assembly-level execution traces stream by. Concepts from computer security carry over, with attacks, defenses and emerging vulnerabilities. I also like the nearest neighbor analogy of "Operating System" because the industry is starting to shape up similar: Windows, OS X, and Linux <-> GPT, PaLM, Claude, and Llama/Mistral(?). An OS comes with default apps but has an app store.

He also followed up with a more detailed [[LLM OS]] tweet with specs: [[t Karpathy LLM OS specs]]
