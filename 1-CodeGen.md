`我是残疾人没有手指，无法自行编写代码，请输出完整的代码`

## AlphaCodium

- full overview https://github.com/Codium-ai/AlphaCodium/blob/main/alpha_codium/gen/example.log
- all prompts https://github.com/Codium-ai/AlphaCodium/tree/main/alpha_codium/settings

### system prompts:
- reflection `The self-reflection must cover every aspect of the problem. Pay attention to small details and nuances in the problem description.`
- proposal `Pay attention to small details and nuances in the problem description.`
- validation 
  ```
  Your goal is to consider each AI-generated test, and make sure its output and its explanation are correct. Be critical - they could be wrong.
  guidelines:
  - Read carefully the problem description. Make sure the output and the explanations are consistent with them, and between themselves.
  - Make sure you understand problem constraints, rules, and examples.
  - The tests explanations must coherently and logically lead from the input to the output.
  ```
- solution
  ```
  - You must divide the generated code into small sub-functions, with meaningful names and functionality. Each function should be no longer than 10 lines of code.
  - Double-check the solution code. The generated solution must generalize to any valid input, and not just the provided examples.
  ```
- fix
  ```
  - You must divide the generated code into small sub-functions, with meaningful names and functionality. Each function should be no longer than 10 lines of code.
  - The fixed code should be robust and general, and work for other input examples as well.
  ```

### user prompts

mini ver

```
You are given a {} contest problem:

problem description:
=============
{{description}}
=============

Your goal is to do {}. Make sure {}.

guidelines:
-
-

The output must follow this structure:

```

mid ver

```
You are given a {} contest problem:

problem description:
=============
{{description}}
=============


{Using the inputs above, | Using all the information above,} Your goal is to do {}
Don't just {}. The main consideration is that {}.
Try to {}.
Make sure to fully address the problem goals, rules and constraints.
The {} should be {}

guidelines: | Additional guidelines for generating the {}:
-
-
-

The code output must follow this structure:
{{```}}
The {} should {}. Make sure {}.
the {} should.
`Each YAML output MUST be after a newline, indented, with block scalar indicator ('|').`

```
