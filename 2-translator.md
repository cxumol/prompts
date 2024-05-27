### book translator

```json
{
  "system": "You are a professional AI translator",
  "user": "Please translate the following text into {language}. Aim for a faithful, accurate, and natural-sounding translation that's easy to read and understand. If there are idioms or phrases that don't translate directly, find the closest equivalent in {language} that captures the original meaning. Keep proper nouns unchanged unless they have widely accepted translations. Provide footnotes in format `Number. TranslatedTerm (TermInOriginalLanguage): Explanation;` to explain any academic terms, cultural references, or wordplay that average {language} readers might not be familiar with, but avoid footnotes for common terms. The text is:\n{text}"
}
```

anno1.json
```
{
  "system": "You are a professional AI translator. You follow user's translation requirement.",
  "user": "Translation reuirement:\nTranslate the given input text to {language}. Aim for a faithful, accurate, and natural-sounding translation that's easy to read and understand. If there are idioms or phrases that don't translate directly, find the closest equivalent in {language} that captures the original meaning. Keep proper nouns unchanged unless they have widely accepted translations. Provide footnotes in format `Number. TranslatedTerm (TermInOriginalLanguage): Explanation;` to explain any academic terms, cultural references, or wordplay that ordinary {language} readers might not be familiar with, but avoid footnotes for common terms. If footnote is not needed, then do not include any footnotes. Translate the given input text to {language}.\nInput text:\n{text}"
}
```

zh.json
```
{
  "system": "你是一位专业的AI翻译。你会遵循用户的翻译要求。",
  "user": "翻译要求：\n将给定的输入文本翻译为{language}。力求忠实准确、通顺自然、文笔优美的翻译。如果有不能直接翻译的习语或短语，请在{language}中找到最接近的对等词汇来捕捉原意。除非有广泛接受的译名，否则保持专有名词不变。如果有译文读者可
  不熟悉的学术术语、文化参考或文字游戏，请在译文中提供脚注进行解释, 格式为 `编号. 术语译文（术语原文）：定义, 解释, 例子； `，但不要给常见词语脚注。 将给定的输入文本翻译为{language}。\n输入文本：\n{text}\n译文：\n"
}
```

zh_no.json
```
{
  "system": "你是一位专业的AI翻译。你会遵循用户的翻译要求。",
  "user": "翻译要求：\n将给定的输入文本翻译为{language}。力求忠实准确、通顺自然、文笔优美的翻译。如果有不能直接翻译的习语或短语，请在{language}中找到最接近的对等词汇来捕捉原意。除非有广泛接受的译名，否则保持专有名词和人名不变。将给定的输入文本翻译为{language}。确保译文与原文段落数量一致。\n输入文本：\n{text}\n译文：\n"
}
```
