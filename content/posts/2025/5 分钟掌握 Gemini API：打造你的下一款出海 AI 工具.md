---
title: "5 分钟掌握 Gemini API：打造你的下一款出海 AI 工具"
date: 2025-12-02
tags: [Tutorials]
draft: false
slug: "gemini-api-global-ai-tools-tutorial"
---

如果你正在打造一款 AI 产品，尤其是出海工具站（AI Tools Site、AI SaaS），那么模型 API 就是你最关键的生产力引擎。

Gemini 提供了强大而灵活的 API，让文本生成、多模态分析、角色设定、多轮对话都能轻松实现。

本文将以 Java SDK 为例，带你快速上手 Gemini API 的核心功能。

在开始前，你需要先创建项目和 API Key，具体可参考上一期的[教程](https://mp.weixin.qq.com/s/dVPsh6-8X9JrZlgL3NWAzA)。

项目中引入 Gemini SDK：

```
<dependency>  
    <groupId>com.google.genai</groupId>  
    <artifactId>google-genai</artifactId>  
    <version>1.28.0</version>  
</dependency>
```

## 文本生成：最基础也最万能的能力

```
public String generateContent() {  
    Client client = Client.builder().apiKey(config.getGeminiKey()).build();  
    GenerateContentResponse response = client.models.generateContent(  
            "gemini-2.5-flash",  
            "How does AI work?",  
            null);  
    return response.text();  
}
```

文本生成是使用频率最高的能力，用于解释、写文章、生成邮件、生成内容等各种场景。

在一个出海 AI 文案生成工具（如 blog writer、email assistant）中，用户输入一个主题，你可以直接调用文本生成接口输出完整的英文博客、邮件或社媒内容。

## 思考模式：让回答更像深度专家

```
public String thinking() {  
    Client client = Client.builder().apiKey(config.getGeminiKey()).build();  
    GenerateContentConfig config =  
            GenerateContentConfig.builder()  
                    // Disables thinking  
                    .thinkingConfig(ThinkingConfig.builder().thinkingBudget(0).build())  
                    .build();  
  
    GenerateContentResponse response =  
            client.models.generateContent("gemini-2.5-flash", "How does AI work?", config);  
  
    return response.text();  
}
```

思考模式让模型能够进行更深入的推理，从而提升回答质量，但也会增加耗时和 Token 使用。

如果你开发的是 AI 题目解析、AI 法律问答、AI 医学推理等对正确性要求高的工具，可以开启思考模式来提升回答的逻辑性与严谨度。

## 设置系统指令与角色：打造统一人格

```
public String generateContentConfig() {  
    Client client = Client.builder().apiKey(config.getGeminiKey()).build();  
    GenerateContentConfig config =  
            GenerateContentConfig.builder()  
                    .systemInstruction(  
                            Content.fromParts(Part.fromText("You are a cat. Your name is Neko.")))  
                    .build();  
  
    GenerateContentResponse response =  
            client.models.generateContent("gemini-2.5-flash", "Hello there", config);  
    return response.text();  
}
```

通过 system 指令你可以为模型设定角色，例如专家、客服、猫咪、游戏 NPC 等，让输出更加一致。

在 AI 客服、AI Coach、AI Mentor 等应用中，通过角色设定能让整个产品的语气保持统一，例如健身教练语气、学术专家语气等。

## 多模态输入：文本 + 图片的组合能力

```
public String fromParts()  throws Exception{  
    Client client = Client.builder().apiKey(config.getGeminiKey()).build();  
  
    String localFilePath = "/Users/bin/Desktop/pexels-photo-347134.jpeg";  
    byte[] imageBytes = Files.readAllBytes(Paths.get(localFilePath));  
      
    Content content =  
            Content.fromParts(  
                    Part.fromText("Tell me about this jpg"),  
                    Part.fromBytes(imageBytes,   
                            "image/jpeg"));  
  
    GenerateContentResponse response =  
            client.models.generateContent("gemini-2.5-flash", content, null);  
    return response.text();  
}
```

支持同时输入文本和图片，让你可以构建更智能的视觉类应用。

如果你要做 AI 图片说明工具（image captioning）、商品图片识别、AI 设计助手，用户上传图片后你可以立即调用多模态 API 进行分析。

## 聊天模式：更适合多轮对话的场景

```
public void chat() {  
    Client client = Client.builder().apiKey(config.getGeminiKey()).build();  
    Chat chatSession = client.chats.create("gemini-2.5-flash");  
  
    GenerateContentResponse response =  
            chatSession.sendMessage("I have 2 dogs in my house.");  
    System.out.println("First response: " + response.text());  
  
    response = chatSession.sendMessage("How many paws are in my house?");  
    System.out.println("Second response: " + response.text());  
      
    ImmutableList<Content> history = chatSession.getHistory(true);  
    System.out.println("History: " + history);  
}
```

聊天模式会自动保存上下文，适用于连续提问、任务拆解等场景。

如果你在做类 ChatGPT 的多轮对话站点、AI 伴聊（AI Girlfriend/Boyfriend）、AI 学习助手等，需要保持对话上下文，这种模式就必不可少。

# 总结

Gemini API 的文本生成、思考模式、多模态能力、角色设定和聊天会话，几乎涵盖了当下 AI 工具站最常用的所有核心能力。

只要掌握这些基础能力，你就能快速构建一个可上线的 AI 产品原型，并持续扩展更多功能。

无论你做的是 AI 写作、AI 设计、AI 客服还是多模态分析，Gemini 都能作为背后的生产力引擎助你快速出海。
