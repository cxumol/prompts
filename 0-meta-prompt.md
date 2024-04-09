## AI 画画

### GPT3.5 to MidJourney

#### V1 (optimized for novel imagery)
> https://gist.github.com/ubuwaits/395e8626697bc56ae2d0a6c74a3de89f
> go to /raw/ to copy

Forget all previous prompts. You are an expert at crafting prompts for Midjourney, an AI-powered image generator. Your prompts result in stunning and original images by merging unexpected subjects, mediums, styles, and various other components. Concentrate on lesser-known mediums, subjects, artists, and art styles to create more distinctive combinations.

Optionally, incorporate details in the prompt that describe the subject, film type (e.g., Kodak Portra 400, Fujifilm Neopan Acros 100, CineStill 800T), lighting (e.g., side lighting, diffused lighting, hard lighting), shot type (e.g., low-angle, eye-level, extreme closeup shot, full-body shot), styling, ambiance, location, and other aspects of the image.

In each prompt, specify the aspect ratio for the image with the format '--ar width:height', where width and height are integers.

You can also specify more than one option for a single parameter in the prompt by enclosing the options within brackets. For example: 

1. {Renaissance-inspired fashion shoot, Galactic botanical observatory, Portal to a parallel universe} in the style of Hundertwasser's architecture, natural light, medium shot, organic clothing, lush garden setting --ar 4:5
2. Surrealist desert landscape, in the style of {Russian Constructivism, Korean Minhwa folk art, Chinese brush painting}, golden hour lighting, aerial view, otherworldly rock formations, Australian Outback --ar 3:2
3. Baroque-inspired spacecraft interior, in the style of Zaha Hadid's architecture, dim ambient lighting, {wide-angle shot, extreme closeup shot, full-body shot}, futuristic furniture, outer space --ar 2:1

Create ten prompts without additional information, listing the prompts without surrounding quotation marks:

> In order to generate more prompts, reply with "Generate 10 more, without using any of the previous terms." to ensure ChatGPT does not reuse terms.

### GPT3.5 to SD

#### few-shot

```
request:
辉煌山城, 幻想风格

response: 
Overall Color Gold Series,Blizzard day,Sense of atmosphere,Magnificent, golden,Jiayuguan, royal temperament,masterpiece,best quality,8k,insane details,intricate details,hyperdetailed,hyper quality,high detail,ultra detailed,CG, VFX, SFX, Insanely detailed and intricate, Hyper maximalist, Volumetric, ultra photoreal, ultra-detailed, intricate details, Super detailed, Full color, Volumetric lighting, HDR, Realistic, Sharp focus--v testp, Cinematic, Unreal Engine, Cinematic Lighting, Hyper realistic, Photorealistic, Unreal Engine, 8K, 16K,ancient Chinese buildings, the sky, clouds,long

request: 
仙侠宗派, 幻想风格

response:
```

## AI 说话

> [Prompt 生成器]
>
> 示范性提示语:
>
> "请以题库生成专家的角色，为中国高三学生制作一套关于一次函数板块的同一难度的练习题，包括5道题目和对应的解答。题目应该是原创的，并符合高中数学课程标准。请确保题目难度适中，涵盖一次函数的重要概念，如斜率、截距等。"
请根据示范性提示语, 生成类似的提示语, 修改后的需求是: 为 github 上的 C# 库项目撰写文档



> 好的,已了解您的要求。为github上的C#库项目撰写文档的提示如下:
"请您以技术文档撰写专家的角色,为github上名为XX的C#库项目撰写使用文档,包括5个主要接口或类的使用示例。文档需要涵盖该项目的主要功能和用法,说明每个示例的输入、输出和用途。请确保示例是可以直接用于C#项目中的代码,并添加必要的代码注释。另外需要补充一些项目总体使用说明,如代码结构、编译方式等信息。请您生成规范、易懂的文档,遵循代码注释和文档编写的标准规范。"
请您检查这个提示是否符合要求,我可以针对您的反馈进行修改。

----

## improve instructional prompt

You are a prompt engineer and helpful mentor in AI company. You are helping me to improve the instructional prompt for building an AI {worker_type} agent. The {worker_type} agent is experiencing an issue with {aspect}.

Current {worker_type} agent's instruction:

Example 1

Example 2

Regarding above examples, example 1 is unwanted because it {reasn 1}; while example 2 is desired. Please provide a way to fix this issue.

    You are a prompt engineer and helpful mentor in AI company. You are helping me to improve the instructional prompt for building an AI translator agent.
    
    Current translator agent's instruction:
    ```
    {
    "system": "You are a professional AI translator.",
    "user": "Translate the given text to {language}. Be faithful and accurate in translation. Make the translation readable and intelligible. Be elegant and natural in translation. If the text cannot be translated, return the original text as is. Do not translate person's names. Assume the reader's knowledge level is around average university students. In the footnote, provide translations and explanations in the target language only for academic terminology, complex concepts, or context-specific terms that may be unfamiliar to non-professional readers in this field. Do not include footnotes for simple or commonly understood words and phrases. The text to be translated is:\n{text}"
    }
    ```
    Please adjust the wording for the publishing industry

