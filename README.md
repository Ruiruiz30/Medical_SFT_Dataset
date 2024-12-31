---
license: BSD3
language:
- en and zh-cn
tags:
- text-generation
pretty_name: medical
task_categories:
- text-generation
---

# Dataset for medical
中英文医疗数据集
  
## Dataset Description

Medical dataset. 医疗数据集，可用于医疗领域大模型监督微调训练。

```
tree medical
|-- finetune  # 监督微调数据集，可用于SFT和RLHF
|   |-- newtest_en_1.json
|   |-- newtest_zh_0.json
|   |-- newtrain_en_1.json
|   |-- newtrain_zh_0.json
|   |-- newvalid_en_1.json
|   |-- newvalid_zh_0.json
|-- `README.md
```




### Original Dataset Summary

- newtrain_zh.json: 共195万条，来自1）中文医疗对话数据集[Toyhom/Chinese-medical-dialogue-data](https://github.com/Toyhom/Chinese-medical-dialogue-data)的六个科室医疗问诊数据，
有79万条；2）在线医疗百科 huatuo_encyclopedia_qa ，有36万条；3）医疗知识图谱 huatuo_knowledge_graph_qa，有79万条。三部分合并，共195万条。
- newtrain_en.json：共11万条，来自英文医疗问诊对话数据[Kent0n-Li/ChatDoctor](https://github.com/Kent0n-Li/ChatDoctor)，合并了HealthCareMagic-100k、GenMedGPT-5k 数据集，共11万条。
- HuatuoGPT_sft_data_v1_sharegpt.jsonl ：共22万条，来自华佗医疗数据集项目[huatuo_medical_qa_sharegpt ](https://huggingface.co/datasets/shibing624/huatuo_medical_qa_sharegpt)      
- HuatuoGPT2_sft_instruct_GPT4_sharegpt.jsonl ：共5万条，来自华佗医疗数据集项目[huatuo_medical_qa_sharegpt ](https://huggingface.co/datasets/shibing624/huatuo_medical_qa_sharegpt)      


### Supported Tasks and Leaderboards
中文医疗对话模型

The dataset designed for medical task training pretrained language models.

### Languages

The data are in Chinese and English.

## Dataset Structure

### Data Instances

An example of "train" looks as follows:


train_zh_0.json
```json
{"conversations": [{"from": "human","value": "血热的临床表现是什么?"},{"from": "gpt","value": "初发或复发病不久。皮疹发展迅速，呈点滴状、钱币状或混合状。常见丘疹、斑丘疹、大小不等的斑片，潮红、鲜红或深红色。散布于体表各处或几处，以躯干、四肢多见，亦可先从头面开始，逐渐发展至全身。新皮疹不断出现，表面覆有银白色鳞屑，干燥易脱落，剥刮后有点状出血。可有同形反应;伴瘙痒、心烦口渴。大便秘结、小便短黄，舌质红赤，苔薄黄或根部黄厚，脉弦滑或滑数。血热炽盛病机，主要表现在如下四个面：一、热象：血热多属阳盛则热之实性、热性病机和病证、并表现出热象。二、血行加速：血得热则行，可使血流加速，且使脉道扩张，络脉充血，故可见面红目赤，舌色深红（即舌绛）等症。三、动血：在血行加速与脉道扩张的基础上，血分有热，可灼伤脉络，引起出血，称为“热迫血妄行”，或称动血。四、扰乱心神：血热炽盛则扰动心神，心主血脉而藏神，血脉与心相通，故血热则使心神不安，而见心烦，或躁扰发狂等症。"}]}
```

train_en_1.json
```json
{"conversations": [{"from": "human","value": "how do i know if i should test for leukemia? my grandpa might have it and i was curious as to what the symptons were. so far i have all of the symptomsl; anemia, bone and joint pain, abdominal distress, swollen lymph nodes, and difficulty breathing."},{"from": "gpt","value": "Thanks for your question on Chat Doctor. I can understand your concern. Leukemia can be hereditary. And you're all symptoms like anemia, joint pain, bone pain, swollen lymph node, breathing difficulty, abdominal pain etc. are seen in leukemia. You are also having positive family history for leukemia. So better to consult oncologist and get done lymph node biopsy and bone marrow biopsy for the diagnosis of leukemia. Hope I have solved your query. Wish you good health. Thanks."}]}
```

HuatuoGPT_sft_data_v1_sharegpt.jsonl
```json
{"conversations": [{"from": "human", "value": "下列医生诊断是很多领域专家共同讨论出的方案，包括吃哪种药品、采取哪种食疗方案、在何种疾病患者使用哪种治疗方法等。应如何操作？\n"}, {"from": "gpt", "value": "作为医生，我们会尊重患者的意见和选择，但在制定治疗方案时，我们会根据各种因素，包括疾病类型、患者年龄、身体条件、用药史等方面进行综合分析和判断。我们会提供针对性较强且最适合患者的治疗方案，并会解释方案的详细信息和治疗效果。在治疗过程中，我们也会不断与患者进行交流和反馈，调整治疗方案。同时，我们也会给予患者一些额外的建议，帮助他们更好地管理自己的健康。"}]}
```

HuatuoGPT2_sft_instruct_GPT4_sharegpt.jsonl
```json
{"conversations": [{"from": "human", "value": "带隐形眼镜..有什么要特别注意的??"}, {"from": "gpt", "value": "佩戴隐形眼镜需要注意以下几点：\n\n1. **清洁手部**：在戴上或取下隐形眼镜之前，一定要确保手部清洁，以防止细菌或其他污染物进入眼睛。\n\n2. **正确使用和保养**：遵循眼科医生或光学专家的建议，正确使用和保养隐形眼镜。这包括按照正确的程序戴上和取下眼镜，以及定期清洁和更换眼镜。\n\n3. **不要过度佩戴**：避免长时间佩戴隐形眼镜，特别是在睡觉时。长时间佩戴可能会导致眼睛缺氧，引发眼睛不适或感染。\n\n4. **定期检查**：定期去眼科诊所进行眼睛检查，以确保眼睛健康，隐形眼镜的度数和型号仍然适合你。\n\n5. **避免在水中佩戴**：游泳或淋浴时应避免佩戴隐形眼镜，因为水中的细菌和其他微生物可能会附着在眼镜上，增加感染的风险。\n\n6. **注意眼睛的不适**：如果佩戴隐形眼镜后感到眼睛不适，如红眼、疼痛、视力模糊、光敏感等，应立即取下眼镜，并尽快就医。\n\n7. **不要与他人共用隐形眼镜**：每个人的眼睛形状和度数都是不同的，而且共用眼镜可能会传播眼部感染。\n\n8. **使用专用的清洁液**：不要用水或其他非专用的液体来清洁隐形眼镜。\n\n以上就是佩戴隐形眼镜需要注意的一些事项，希望对你有所帮助。"}]}
```

 
### Contributions

- 原始数据来源：[shibing624](https://github.com/shibing624) 
- 由 三明学院人工智能与信息融合应用创新研究中心 重新整合并转换为 [MedicalGPT](https://github.com/shibing624/MedicalGPT) 支持格式
