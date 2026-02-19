In this repo, we aim to write a AlphaGeometry.md, a markdown file, introducing the AlphaGeometry paper placed in the docs folder, to an audience of PhD students in AI and a professor in a group meeting. **Always abide to the technical requirements in your writing.**

# Requirements:

- Give a succinct overview and background. 

- Give a brief description of what kind of environment the paper builds of Euclidean Gerometry and works with.

- Give a detailed self-contained explanation to how data synthesization is done. Importantly, explain directed acyclic graphs and their role here/traceback, etc. Explain how AR + DD are done. They were only briefly introduced in the main body of the paper, and I believe more detail can be found in the appendix.

- Explain the model structure, rationale of the structure and how training is done using `(P, N, G(N))`. 

- Explain what is learnt by the model and what core challenge it addresses.

- Present the results and findings of the paper. Be detailed and highlight the contributions.

- Highlight the limitations of AlphaGeometry.

# Specific points to answer:

- Does the env of AlphaGeometry have a proof-verification kernel like Lean?

- How is search parallelization done?

- Why don't we use a compute-heavy approach like TTRL in AlphaProof when solving the geometry problems? Is it because Euclidean geometry is easy or much more specific/narrow?

# Technical Requirements:

- Include diagrams and tables from the paper whenever it helps to explain. If you cannot extract the table or diagrams from the paper, use a placeholder, let's say a bracket, and the name of that table, so I can do it manually later.

- I have presented on AlphaProof in another group meeting. So you can reference from and make analogy to the AlphaProof paper as if the audience has seen a presentation of it.

- Leave out technical details that don't matter. Think of this presentation as a presentation to a general audience of AI. So we are trying to learn from the algorithm and the techniques here. So the technical details should be left out, but the presentation itself should still be self-contain and complete.

- Illustrate with examples whenever possible. Prefer to use examples used in the paper.

- After each time the user asks you to write or edit the main alphageometry.md file, write a report of what has been changed or created in a new report.md file inside the job reports folder.

- Check appendix whenever the main body refers to that part of the paper.

- **Do NOT** be too verbose in the presentation file. **NEVER** throw in long paragraphs. Put things in point forms and at most medium-length sentences. Optimize for readability and conciseness.

- After each write/rewrite, read the whole thing and make sure its self-contained, good and up to the standards.

- Every diagram/table included **MUST** be explained in context. Otherwise they are useless.