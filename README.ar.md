# AI Tools Dataset

[English](README.md) · **العربية**

> مجموعة بيانات نظيفة وقابلة لإعادة الاستعمال لأدوات الذكاء الاصطناعي وتصنيفاتها ونماذج تسعيرها ومنصاتها وبياناتها العامة.

<!-- counts:start -->
![Records](https://img.shields.io/badge/records-748-informational)
<!-- counts:end -->
![Contributions welcome](https://img.shields.io/badge/contributions-welcome-brightgreen)
[![License: CC BY 4.0](https://img.shields.io/badge/license-CC%20BY%204.0-lightgrey)](LICENSE)

٧٤٨ أداة ذكاء اصطناعي بصيغتَي CSV وJSON، بالحقول العشرة نفسها في كل سجل، وكل رابط فيها
فُتح عبر HTTP قبل الإصدار. وهي صغيرة بما يكفي لتُقرأ وتُحمَّل وتُفحص يدويًا، وذلك هو المقصود:
فجدول من أربعين ألف صف لم يتحقق منه أحد أسوأ من عديم النفع في البحث.

والسجلات التي رسبت في التحقق لم تُشحن. وقد أسقط ذلك ١٨٢ مرشحًا، منها أربعة انتهت نطاقاتها
وصارت تحوّل إلى صفحة بيع نطاقات، وهو السبب الأول لكون هذه المجموعة أصغر من الفهرس الذي
سُحبت منه.

بإشراف [TiorAI](https://tiorai.com/)، وعملها اليومي فهرسة أدوات الذكاء الاصطناعي.

<!-- last-reviewed:start -->
**آخر مراجعة:** 2026-08-26
<!-- last-reviewed:end -->

## المحتويات

- [ما في مجموعة البيانات](#ما-في-مجموعة-البيانات)
- [السجلات](#السجلات)
- [Education and learning](#education-and-learning)
- [Automation and agents](#automation-and-agents)
- [Customer support](#customer-support)
- [Research and knowledge](#research-and-knowledge)
- [Business and finance](#business-and-finance)
- [Health and lifestyle](#health-and-lifestyle)
- [SEO and search](#seo-and-search)
- [Productivity and workflow](#productivity-and-workflow)
- [Marketing and advertising](#marketing-and-advertising)
- [Coding and development](#coding-and-development)
- [Data and analytics](#data-and-analytics)
- [Audio, music, and voice](#audio-music-and-voice)
- [Sales and CRM](#sales-and-crm)
- [Presentations and documents](#presentations-and-documents)
- [Design and creative](#design-and-creative)
- [Image generation and editing](#image-generation-and-editing)
- [Writing and content](#writing-and-content)
- [Video](#video)
- [Developer infrastructure and models](#developer-infrastructure-and-models)
- [Chatbots and assistants](#chatbots-and-assistants)
- [المخطط](#المخطط)
- [كيف تتحقق السجلات](#كيف-تتحقق-السجلات)
- [استعمال البيانات](#استعمال-البيانات)
- [حدود معروفة](#حدود-معروفة)
- [اقتراح تصحيح](#اقتراح-تصحيح)
- [المساهمة](#المساهمة)
- [إخلاء مسؤولية](#إخلاء-مسؤولية)
- [الرخصة](#الرخصة)
- [عن TiorAI](#عن-tiorai)

## ما في مجموعة البيانات

```text
data/
├── ai-tools.csv        748 سجلًا، 10 أعمدة، UTF-8، RFC 4180
├── ai-tools.json       السجلات الـ748 نفسها، بأنواع محدَّدة
├── categories.csv      التصنيفات العشرون، بوصف وعدد لكل منها
└── schema.json         مخطط JSON لملف ai-tools.json، للتحقق مقابله
```

**لقراءة السجلات نفسها، افتح [`data/ai-tools.csv`](data/ai-tools.csv).** يعرضه GitHub جدولًا قابلًا للفرز والبحث، فيمكنك تصفّح الـ748 كلها دون استنساخ المستودع أو تنزيل أي شيء. وملف [`data/ai-tools.json`](data/ai-tools.json) هو السجلات نفسها بأنواع محدَّدة، و[`data/categories.csv`](data/categories.csv) قائمة التصنيفات.

هذا الملف يوثّق مجموعة البيانات ولا يعيد نشرها. فـ748 سجلًا تصنع صفحة لا تُقرأ ونسخة ثانية من البيانات يجب إبقاؤها متطابقة، والملفات أعلاه هي المنتج نفسه.

ملف CSV وملف JSON متطابقان دلاليًا. ويحدّد JSON أنواع الحقول كما ينبغي؛ فـ`pricing_model`
و`platform` مصفوفتان، و`open_source` و`api_available` قيمتان منطقيتان، و`secondary_category`
نص أو `null`. أما CSV فيسطّح المصفوفات بفاصل `; ` ليفتح نظيفًا في برنامج جداول.

أسماء التصنيفات تبقى بالإنجليزية لأنها قيم في البيانات نفسها، وترجمتها هنا كانت ستجعل الجدول
مخالفًا لملف `categories.csv`.

والتوزيع يعكس ما نجا من التحقق لا شكل الميدان. وهو ليس عيّنة من سوق الذكاء الاصطناعي ولا
ينبغي أن يُستعمل كذلك. انظر [حدود معروفة](#حدود-معروفة).

<!-- records:start -->

## السجلات

السجلات الـ748 كلها، مجموعةً حسب `primary_category` ومرتبةً بالاسم داخل كل مجموعة. والترتيب لا يحمل أي معنى.

هذا القسم مولَّد من `data/ai-tools.json`، فلا يمكن أن يختلف عن ملفات البيانات. فهي المصدر وهذا عرضٌ لها، ويبقى [`data/ai-tools.csv`](data/ai-tools.csv) أسرع في البحث والفرز والتصفية دفعةً واحدة.

أسماء التصنيفات وأسماء المنتجات والأوصاف تظهر بالإنجليزية لأنها **قيم بيانات** لا نثر: هي ما تحمله الحقول نفسها في الملفات، وترجمتها هنا كانت ستجعل هذا العرض مختلفًا عن مصدره.

| التصنيف | السجلات |
|---|---:|
| [Education and learning](#education-and-learning) | 66 |
| [Automation and agents](#automation-and-agents) | 61 |
| [Customer support](#customer-support) | 59 |
| [Research and knowledge](#research-and-knowledge) | 55 |
| [Business and finance](#business-and-finance) | 55 |
| [Health and lifestyle](#health-and-lifestyle) | 50 |
| [SEO and search](#seo-and-search) | 44 |
| [Productivity and workflow](#productivity-and-workflow) | 41 |
| [Marketing and advertising](#marketing-and-advertising) | 37 |
| [Coding and development](#coding-and-development) | 35 |
| [Data and analytics](#data-and-analytics) | 35 |
| [Audio, music, and voice](#audio-music-and-voice) | 34 |
| [Sales and CRM](#sales-and-crm) | 30 |
| [Presentations and documents](#presentations-and-documents) | 28 |
| [Design and creative](#design-and-creative) | 28 |
| [Image generation and editing](#image-generation-and-editing) | 27 |
| [Writing and content](#writing-and-content) | 18 |
| [Video](#video) | 17 |
| [Developer infrastructure and models](#developer-infrastructure-and-models) | 15 |
| [Chatbots and assistants](#chatbots-and-assistants) | 13 |

## Education and learning

Teaching, studying, tutoring, and course material.

- **[101.school](https://101.school/)** — Web-based interactive education platform that enables teachers to create and assign digital exercises and assessments, supporting both in-person and remote learning environments. `Freemium` `Web`
- **[14DaysOfAI](https://www.100school.com/)** — Free, 14-day online challenge by 100 School that helps beginners learn practical AI skills through daily hands-on tasks and community support. `Free` `Web`
- **[31Memorize](https://31memorize.com/)** — AI-driven web platform that provides personalized memory training exercises to improve cognitive function and mental agility. `Freemium` `Web`
- **[Accent Guesser](https://accentguesser.ai/)** — Free online AI tool that identifies English accents from voice recordings by analyzing speech patterns and matching them to known regional accents. `Free` `Web`
- **[Aceify.ai](https://aceify.ai/)** — Study assistant that helps students automate note-taking, generate flashcards, and plan study schedules to improve learning efficiency. `Freemium` `Web`
- **[Achievable - AI adaptive learning](https://achievable.me/)** — Adaptive learning platform that personalizes study plans for professional exam preparation and skill development, optimizing learning efficiency through tailored content and progress tracking. `Paid` `Free Trial` `Web`
- **[Adaapt](https://www.adaapt.ai/)** — AI-driven adaptive learning platform that personalizes educational content and assessments to individual learner needs, enhancing engagement and outcomes. `Paid` `Web`
- **[AdeptLR](https://www.adeptlr.com/)** — AI-driven corporate learning platform that personalizes employee training and manages compliance efficiently. `Paid` `Web`
- **[Adlas.io](https://adlas.io/)** — Web-based platform that provides tools for annotating images, videos, text, and audio to create labeled datasets essential for training AI models. `Paid` `Free Trial` `Web`
- **[Aeon: AI-assisted Video Production](https://project-aeon.com/)** — AI-assisted video production platform that automates editing by analyzing footage to create polished videos quickly, ideal for marketers and content creators. `Freemium` `Web`
- **[afiniti.com](https://www.afiniti.com/)** — AI-driven software that enhances call center performance by pairing customers with agents based on behavioral data to improve outcomes and customer satisfaction. `Paid` `Web` `API`
- **[Agoge-ai](https://www.agoge-ai.com/)** — No-code AI platform that automates data science workflows including data preprocessing, model training, evaluation, and deployment, enabling users to build machine learning models without programming skills. `Paid` `Free Trial` `Web`
- **[ai2006](https://ai2006.io/)** — Web-based AI platform that provides advanced data analytics, business process automation, and machine learning model deployment to help organizations optimize operations and gain insights. `Freemium` `Web`
- **[AI4ANKI](https://www.ai4anki.com/)** — AI-driven tool that generates Anki-compatible flashcards automatically from text or documents, helping learners save time and improve retention. `Freemium` `Web`
- **[AI Bible Verse Studies](https://helpfromthebible.com/)** — Free web tool that uses artificial intelligence to provide detailed explanations and contextual insights for any Bible verse, supporting personal and group scripture study. `Free` `Web`
- **[AI Book Summarizer](https://aibooksummarizer.com/)** — Online platform that uses artificial intelligence to create concise summaries of books, helping users quickly understand main ideas without reading the entire text. `Freemium` `Web`
- **[AI Builder Buddy](https://aibuilderbuddy.com/)** — No-code platform that enables users to create, train, and deploy custom AI models without programming skills, streamlining AI adoption for businesses. `Paid` `Free Trial` `Web`
- **[AICamp](https://aicamp.so/)** — Education platform offering project-based learning to teach AI, machine learning, and data science through hands-on projects and community mentorship. `Freemium` `Web`
- **[AICheatCheck](https://aicheatcheck.com/)** — Tool that detects whether text is AI-generated or plagiarized, helping maintain content authenticity and academic integrity. `Freemium` `Web`
- **[AI ColoringBook](https://www.coloringbook.ai/)** — Web-based tool that uses AI to generate custom line art coloring pages from user prompts, ideal for educational and creative purposes. `Freemium` `Web`
- **[AI Consulting for Finance Teams](https://genfinance.ai/)** — GenFinance AI provides specialized AI consulting services designed to help finance teams improve financial analysis, forecasting, risk management, and automation through tailored AI solutions. `Paid` `Web`
- **[AI Consulting Tools](https://aiconsultingtools.com/)** — AI Consulting Tools provides expert consulting services to help businesses develop AI strategies, automate processes, and plan AI integration for digital transformation. `Paid` `Web`
- **[AI Course Creator - AcademyOcean](https://academyocean.com/)** — AcademyOcean's AI Course Creator is a web platform that uses AI to automate the creation of online courses, helping educators and trainers quickly generate structured content, customize lessons, and manage learner progress. `Paid` `Web`
- **[AI Data Collection Company](https://gts.ai/)** — AI Data Collection Company by GTS AI provides specialized data annotation and collection services for AI and machine learning projects, supporting multiple data types with expert human annotators and quality assurance. `Paid` `Web`
- **[Aidbase](https://www.aidbase.ai/)** — No-code AI platform that enables users to create, train, and deploy custom AI models without programming skills, offering data annotation, automated training, and flexible deployment. `Freemium` `Web`
- **[Aiden Solutions](https://aiden.solutions/)** — Platform that automates business processes and provides predictive analytics to enhance operational efficiency and decision-making. `Paid` `Web` `API`
- **[AI Design Training](https://aidesigntraining.com/coming-soon)** — Online platform that uses artificial intelligence to provide personalized UX/UI and creative design education through interactive courses and project feedback. `Paid` `Free Trial` `Web`
- **[AI Digital Learning](https://aidigitallearning.com/)** — AI-driven platform that personalizes online education by adapting content to individual learner needs, supporting K-12, higher education, and corporate training. `Paid` `Web`
- **[aigclist](https://aigclist.com/)** — Free online directory that aggregates and categorizes AI tools, providing detailed information, user reviews, and AI industry news to help users discover and compare AI solutions. `Free` `Web`
- **[Aigency Labs](https://aigencylabs.com/)** — Platform specializing in custom AI model development and deployment, providing tailored AI solutions and consulting services for enterprises. `Paid` `Web`
- **[AI Homework Helper](https://aihomeworkhelper.co/)** — Study tool that works through homework questions step by step, and covers essay drafting and test preparation. `Freemium` `Web`
- **[AI LingoPlay](https://ailingoplay.com/)** — Language learning platform that offers interactive conversation practice, pronunciation feedback, and personalized lessons to help users learn languages effectively. `Freemium` `Web`
- **[AI Magicx](https://www.aimagicx.com/?gr_pk=dnQL)** — AI-driven marketing automation platform that helps businesses automate and optimize advertising campaigns across multiple platforms like Facebook, Google, and TikTok to improve performance and ROI. `Paid` `Free Trial` `Web`
- **[AI Manga Translators](https://mangatranslator.io/)** — Online tool that uses AI to translate manga images from Japanese to English quickly and efficiently. `Freemium` `Web`
- **[AI Math](https://ai-math.top/)** — Free solver that works through math problems and shows each step of the working rather than only the answer. `Free` `Web`
- **[Ai online course](https://www.aionlinecourse.com/)** — Web-based platform providing structured courses in artificial intelligence, offering video lessons, quizzes, projects, and certification to help learners develop AI skills. `Freemium` `Web`
- **[AI Power](https://aipower.org/)** — Open source artificial intelligence platform that enables users to build, train, and deploy machine learning models with automation and API integration. `Free` `Open Source` `Web` `API`
- **[AIQuizGen](https://aiquizgen.com/)** — Platform that automates quiz creation by generating questions from user-provided content, supporting multiple question types and easy sharing. `Freemium` `Web`
- **[Airscale](https://airscale.io/)** — Web-based platform that provides scalable, customizable data annotation services for AI training datasets, supporting images, videos, and text with quality assurance tools. `Paid` `Web`
- **[AI Teacha](https://aiteacha.com/)** — AI-driven educational platform providing personalized tutoring, homework assistance, and adaptive learning tailored to individual student needs. `Paid` `Free Trial` `Web`
- **[AI Tool Center](https://aitoolcenter.com/)** — Free online directory that helps users discover, compare, and review AI tools across various categories and industries. `Free` `Web`
- **[AIToolGo](https://aitoolgo.com/)** — Free online directory that helps users discover, compare, and evaluate AI software tools across various industries and use cases. `Free` `Web`
- **[AI Tools Bay](https://aitoolsbay.com/)** — Free directory for discovering and comparing AI tools, indexed by category and by industry. `Free` `Web`
- **[aleph-alpha.com](https://aleph-alpha.com/)** — German AI company providing advanced multilingual large language models accessible via API for tasks like text generation, summarization, and semantic search. `Freemium` `Web` `API`
- **[alevels.ai](https://www.alevels.ai/)** — AI-driven platform that helps A-Level students prepare for exams through personalized study plans, AI-generated practice questions, and instant doubt resolution. `Freemium` `Web`
- **[Alexa Translations A.I.](https://alexatranslations.com/)** — AI-driven platform providing fast and accurate multilingual translation and localization services for businesses to communicate globally. `Paid` `Web`
- **[Algo for Podcasts](https://algo.tv/)** — Platform that personalizes podcast recommendations based on your listening preferences using machine learning algorithms. `Freemium` `Web`
- **[Algor Education](https://www.algoreducation.com/en)** — AI-driven tutoring platform that provides personalized homework help, concept explanations, and study support through adaptive learning technology. `Freemium` `Web`
- **[Almeta ML](https://almeta.cloud/)** — Cloud platform that automates machine learning workflows including data preprocessing, model training, and deployment, designed for both data scientists and business users. `Paid` `Web`
- **[AlphaFold](https://alphafold.ebi.ac.uk/)** — System developed by DeepMind that predicts highly accurate 3D protein structures from amino acid sequences, accessible free via the EBI website. `Free` `Web`
- **[anakin.ai](https://anakin.ai/)** — Data analytics platform that helps businesses analyze data, generate predictive insights, and create interactive dashboards to support informed decision-making. `Freemium` `Web`
- **[Analytics Model](https://www.analytics-model.com/)** — Web-based AI platform that automates data analysis and predictive modeling, enabling users to generate insights and visualizations without coding expertise. `Paid` `Free Trial` `Web`
- **[Anki](https://apps.ankiweb.net/)** — Open-source spaced repetition flashcard program that helps users memorize information efficiently by scheduling reviews at optimal intervals to enhance long-term retention. `Free` `Web` `iOS` `Android`
- **[anki-decks.com](https://anki-decks.com/)** — Free web platform offering thousands of user-shared Anki flashcard decks for download and study, supporting efficient spaced repetition learning. `Free` `Web`
- **[AnkiWeb](https://ankiweb.net/)** — Free web-based platform that enables users to create, study, and sync flashcards using spaced repetition to improve memory retention. `Free` `Web` `iOS` `Android`
- **[Anodot](https://www.anodot.com/)** — AI-driven anomaly detection platform that monitors business and operational data in real time, automatically identifying unusual patterns and providing alerts and root cause analysis to help enterprises quickly address issues. `Paid` `Web` `API`
- **[Anxiety Simulator](https://anxietysimulator.com/)** — Free web-based tool that simulates the physical and emotional symptoms of anxiety to educate users and foster empathy. `Free` `Web`
- **[anyLanguage.ai](https://anylanguage.ai/)** — Translation platform covering more than 30 languages, with an API for localizing content in bulk. `Paid` `Free Trial` `Web` `API`
- **[AnyoneCanAI](https://www.anyonecanai.io/)** — No-code AI platform that allows users to create, train, and deploy custom AI models easily without programming skills. `Freemium` `Web`
- **[Apex Vision AI - Homework & Quiz Answering AI](https://apexvision.ai/)** — Educational assistant that provides students with accurate homework and quiz answers along with detailed explanations to enhance learning. `Freemium` `Web`
- **[API2D](https://api2d.com/)** — Cloud-based AI API platform that enables developers to deploy, manage, and access custom AI models via standardized APIs, simplifying AI integration and scaling. `Freemium` `Web` `API`
- **[aporia.com](https://www.aporia.com/)** — Monitoring platform that helps organizations track machine learning model performance, detect data and prediction drift, and maintain compliance through real-time alerts and analytics. `Paid` `Free Trial` `Web`
- **[Appen](https://www.appen.com/)** — Platform offering scalable data annotation and collection services through a global crowd workforce to support AI and machine learning model training. `Paid` `Web`
- **[AppGen](https://symph.ai/)** — Platform by Symph.ai that automates the creation, deployment, and maintenance of software applications, enabling rapid development with minimal coding. `Paid` `Web`
- **[Applio](https://applio.org/)** — Open source platform designed for deploying, managing, and scaling containerized AI models with Kubernetes support, offering APIs, monitoring, and version control. `Free` `Open Source` `Web` `API`
- **[ApplyGoat](https://applygoat.com/)** — AI-driven platform designed to assist students in writing and refining their college application essays by providing personalized prompts, grammar corrections, and feedback. `Freemium` `Web`

## Automation and agents

Workflow automation, integrations, and autonomous agents.

- **[0ptikube](https://www.0ptikube.dev/)** — Open-source tool designed to simplify Kubernetes cluster creation, management, and automation for developers and DevOps professionals. `Free` `Open Source` `Web` `CLI`
- **[10x Rules](https://10xrules.ai/)** — No-code AI platform that enables businesses to automate decision-making and workflows, helping accelerate growth and operational efficiency without coding. `Paid` `Free Trial` `Web`
- **[15minuteplan.ai](https://www.15minuteplan.ai/)** — AI-driven platform that enables entrepreneurs and small businesses to quickly generate professional business plans using guided templates and automated content creation. `Freemium` `Web`
- **[1min.AI](https://1min.ai/)** — AI-driven video creation platform that transforms text into short, engaging videos quickly, featuring automatic voiceovers and customizable templates. `Freemium` `Web`
- **[2Captcha](https://2captcha.com/)** — Online service that automates solving CAPTCHAs using a combination of human solvers and machine learning, accessible via API for integration into automation workflows. `Paid` `Web` `API`
- **[2V AI](https://2v.ai/)** — AI-driven platform that automates video creation from text and images, enabling businesses to produce marketing and social media videos quickly without manual editing. `Paid` `Web`
- **[3Commas](https://3commas.io/)** — Cryptocurrency trading platform that automates trading strategies through bots, offers portfolio management, and integrates social trading and external signals to optimize crypto investments. `Freemium` `Web` `API`
- **[3DPrinterOS](https://www.3dprinteros.com/)** — Cloud platform that enables remote management, workflow automation, and collaboration for 3D printing operations, supporting multiple printers and integration with CAD tools. `Freemium` `Web` `API`
- **[Acedit AI](https://www.acedit.ai/)** — Web-based video editing platform that uses artificial intelligence to automatically edit and trim videos, making video production faster and easier for creators and marketers. `Freemium` `Web`
- **[Actimate](https://www.actimate.io/)** — No-code AI automation platform that enables businesses to automate workflows, integrate multiple applications, and optimize operations efficiently. `Paid` `Free Trial` `Web` `API`
- **[Action Figure](https://actionfigure.pro/)** — Writing assistant designed to help users create marketing copy, blog posts, and SEO-optimized content efficiently through an intuitive web platform. `Paid` `Free Trial` `Web`
- **[activeig.com](https://activeig.com/)** — Web-based Instagram growth tool that automates targeted likes, follows, and comments to help users gain real followers and increase engagement organically. `Freemium` `Web`
- **[Adaptify](https://adaptify.ai/)** — Marketing platform that enables businesses to create personalized, adaptive campaigns by analyzing customer data and behavior in real time. `Paid` `Web`
- **[Adaptiv Me](https://www.adaptiv.me/)** — Chatbot platform that enables businesses to create personalized conversational experiences for customer engagement, lead generation, and support automation. `Freemium` `Web` `API`
- **[AdAstra](https://1trillionclub.com/?linkId=lp_771356&sourceId=creati-ai-chen&tenantId=1-trillion-club)** — Writing assistant designed to help marketers and content creators generate marketing copy, blog posts, emails, and product descriptions quickly and efficiently. `Freemium` `Web`
- **[Adext AI](https://adext.com/)** — AI-driven platform that automates digital ad campaign management by optimizing audience targeting and budget allocation across platforms like Google and Facebook to maximize advertising ROI. `Freemium` `Web`
- **[ADfixer](https://adfixer.com/)** — AI-driven ad optimization platform that automates bid and budget management across multiple advertising platforms to improve campaign performance and ROI. `Paid` `Web`
- **[Adinspiration](https://adinspiration.com/)** — AI-driven advertising tool that helps marketers create creative ad copy and campaign ideas quickly for multiple platforms. `Paid` `Free Trial` `Web`
- **[Admentary](https://www.admentary.com/)** — AI-driven tool that generates persuasive ad copy for social media and digital marketing campaigns, helping marketers create effective ads quickly. `Freemium` `Web`
- **[AdNabu 2.0](https://www.adnabu.com/)** — Google Ads automation tool that helps advertisers optimize PPC campaigns by automating bid adjustments, budget allocation, and ad copy testing to improve ROI and reduce manual management. `Freemium` `Web`
- **[Adpollo](https://adpollo.io/)** — AI-driven platform that helps marketers create, manage, and optimize Facebook and Instagram ads by generating ad creatives and providing performance analytics. `Paid` `Free Trial` `Web`
- **[ADS4GPTs](https://www.ads4gpts.com/)** — AI-driven platform that generates persuasive ad copy for multiple advertising platforms, helping marketers create effective campaigns faster. `Paid` `Free Trial` `Web`
- **[AdsGency AI MVP](https://adsgency.ai/)** — AI-driven platform that helps marketers generate and manage ad campaigns by creating tailored ad copy and automating campaign setup across major platforms. `Freemium` `Web`
- **[AdsRapido](https://adsrapido.com/)** — Web-based tool that automates Facebook ad campaign creation, management, and optimization to save time and improve advertising results. `Paid` `Free Trial` `Web`
- **[AdSync: AI Digital Marketing Solutions](https://adsyncmarketing.com/)** — AI-driven digital marketing platform that automates campaign management, optimizes ad spend, and provides real-time analytics to improve advertising performance. `Paid` `Web`
- **[Adzooma](https://adzooma.com/)** — Advertising platform that automates and optimizes PPC campaigns across Google Ads, Microsoft Ads, and Facebook Ads, helping marketers improve ROI through AI-driven analytics and automation. `Freemium` `Web`
- **[Aesthetic intelligence](https://evoke-ai.com/)** — AI-driven design tool by Evoke AI that analyzes and improves visual content to help users create aesthetically pleasing designs efficiently. `Freemium` `Web`
- **[AgentGPT](https://agentgpt.reworkd.ai/)** — Open-source autonomous AI platform that uses GPT-4 to create and manage AI agents which perform complex tasks independently by planning, executing, and iterating without human intervention. `Free` `Web`
- **[Agilotext](https://www.agilotext.com/)** — Writing assistant that helps users generate, edit, and optimize English content quickly with customizable styles and grammar correction. `Paid` `Free Trial` `Web`
- **[ai4bd.com](https://ai4bd.com/)** — Web-based AI tools platform from Bangladesh that provides business automation, content generation, and productivity AI applications with a freemium pricing model. `Freemium` `Web`
- **[AI Application Assistant](https://www.aiapplicationassistant.com/)** — AI-driven platform that helps developers by providing real-time code suggestions, automated bug detection, code optimization, and documentation generation to streamline app development. `Freemium` `Web` `API`
- **[aiCarousels.com](https://www.aicarousels.com/)** — Web-based AI tool that generates customizable carousel posts for social media platforms, helping marketers and creators produce engaging multi-slide content efficiently. `Paid` `Free Trial` `Web`
- **[AI Data Sidekick](https://www.airops.com/)** — Web-based AI tool that automates data analysis, cleaning, and workflow processes to help businesses extract insights efficiently. `Freemium` `Web`
- **[aidocmaker.com](https://www.aidocmaker.com/)** — Web-based AI tool that automates the creation of business documents using customizable templates and exports them as PDFs. `Paid` `Free Trial` `Web`
- **[AI Email Generator](https://aiemailgenerate.com/)** — Web tool that uses artificial intelligence to help users quickly draft professional emails with customizable tone and templates. `Freemium` `Web`
- **[AIflixhub](https://aiflixhub.com/)** — Platform that converts text scripts into professional videos with AI voiceovers and customizable templates, ideal for marketers and content creators. `Paid` `Free Trial` `Web`
- **[AI-Flow](https://ai-flow.net/)** — No-code platform that allows businesses to automate workflows by integrating multiple AI services and APIs, improving operational efficiency without programming. `Freemium` `Web`
- **[AIOAI](https://aioai.co/)** — Content generation platform that produces marketing copy, blog posts, and creative writing content efficiently through customizable templates and SEO optimization. `Freemium` `Web`
- **[AI Office Bot](https://aiofficebot.com/)** — Virtual assistant designed to automate office tasks such as scheduling, reminders, and communication, helping businesses improve productivity. `Freemium` `Web` `API`
- **[AI Perfect Assistant - GPT for Office365](https://perfectassistant.ai/)** — GPT-4 powered AI tool integrated with Microsoft Office365 apps to automate email drafting, document summarization, and streamline office workflows. `Freemium` `Web`
- **[AI Phone](https://www.aiphone.ai/)** — AI-driven virtual phone system that automates call answering, voicemail transcription, and call routing to improve business communication efficiency. `Paid` `Free Trial` `Web`
- **[AI-Powered Text-to-Video App](https://reemix.co/)** — Reemix turns written text into finished video, with template choices, voiceover, and direct sharing. `Freemium` `Web`
- **[AI-Powered Web Exploration - WebQuery](https://www.webquery.net/en)** — WebQuery extracts data from websites through a no-code interface, then analyzes and exports what it collects. `Paid` `Free Trial` `Web`
- **[Aiquare](https://aiquare.com/)** — Platform that automates customer engagement using conversational AI chatbots and voice assistants, providing multi-channel communication and customer insights. `Paid` `Web` `API`
- **[Ai Regex](https://airegex.pro/)** — Web-based tool that uses artificial intelligence to generate, test, and explain regular expressions from natural language descriptions, helping users create accurate regex patterns efficiently. `Freemium` `Web`
- **[Airparser](https://airparser.com/?gr_pk=wxpK)** — Web-based tool that automatically extracts structured data from emails, enabling automation of workflows by sending parsed data to CRMs, spreadsheets, or other applications. `Freemium` `Web`
- **[Airpost](https://www.airpost.ai/)** — Email assistant that automates inbox management, reply drafting, and workflow automation to help users handle emails more efficiently. `Freemium` `Web` `Browser Extension`
- **[AI Social Post Generator](https://www.flick.social/)** — Create engaging social media captions, research hashtags, and schedule posts to improve Instagram marketing efforts. `Paid` `Free Trial` `Web`
- **[AI Social Recommendator](https://ai.socialrecommendator.com/)** — AI-based tool that provides social media managers with relevant content suggestions and scheduling features to enhance audience engagement. `Freemium` `Web`
- **[Ai & Stuff](https://aiandstuff.com/)** — Web workspace bundling text and image generators, aimed at people running several small content jobs at once. `Freemium` `Web`
- **[AI-Suite: Azen](https://azen.app/)** — Bundle of writing and automation tools for marketing copy, social posts, and email, in one web workspace. `Freemium` `Web`
- **[AI Text Generator](https://ai-text-generator.org/)** — Free web tool that uses AI to generate written content based on user prompts, ideal for content creation and marketing copy. `Free` `Web`
- **[AI TikTok Script Writer](https://claptools.com/)** — Web-based tool by ClapTools that uses AI to generate creative, engaging scripts tailored for TikTok videos, helping creators save time and improve content quality. `Paid` `Free Trial` `Web`
- **[AI Two](https://aitwo.co/)** — AI-driven platform that helps users create various types of written content quickly using customizable templates and automation tools. `Freemium` `Web`
- **[AIVideo](https://www.aivideo.com/)** — Web-based AI video generator that automates video creation and editing using customizable templates and AI-driven tools, ideal for marketers and content creators. `Freemium` `Web`
- **[AI Video API](https://www.aivideoapi.com/)** — Developer-focused platform providing an API to automate video creation and editing using customizable templates and dynamic content insertion. `Paid` `Free Trial` `Web` `API`
- **[AI Video Cut](https://www.aivideocut.com/)** — Web-based tool that uses AI to automatically detect scenes and cut videos into shorter clips, streamlining video editing for creators and marketers. `Paid` `Free Trial` `Web`
- **[AI Video Generator - Veo3](https://www.aivideogenerator.net/)** — Web-based tool that uses AI to automate video creation from text, images, or clips, offering templates, voiceovers, and social media optimized exports. `Paid` `Free Trial` `Web`
- **[AIVlog](https://myaivlog.com/)** — Platform that automates video blog creation by generating scripts, editing videos, and providing customizable templates and voiceovers for efficient content production. `Freemium` `Web`
- **[AI Website Builder](https://hyddle.com/index.html)** — Hyddle's AI Website Builder is a web platform that uses artificial intelligence to automate website creation, enabling users to build responsive, SEO-friendly sites quickly without coding skills. `Freemium` `Web`
- **[AI Workflow Automation Tools](https://aiworkflow.tools/)** — Visual builder for business workflows, connecting the services a process already runs through. `Freemium` `Web` `API`

## Customer support

Helpdesk automation, ticket resolution, and customer-facing chat.

- **[008](https://www.008agent.ai/)** — Conversational agent platform designed to automate customer support and sales processes by handling inquiries, qualifying leads, and scheduling appointments through natural language interactions. `Paid` `Free Trial` `Web` `API`
- **[2Houses](https://www.2houses.com/en/)** — Co-parenting app that helps separated parents manage custody schedules, expenses, and communication in one secure platform. `Freemium` `Web` `iOS` `Android`
- **[6 River Systems](https://6river.com/)** — 6 River Systems offers collaborative mobile robots and cloud software that assist warehouse workers in order fulfillment, improving accuracy and efficiency. `Paid` `Web`
- **[8x8](https://www.8x8.com/)** — Cloud communications suite for businesses, covering VoIP telephony, contact center, video conferencing, and team messaging. `Paid` `Free Trial` `Web` `iOS` `Android`
- **[AccessiBe](https://accessibe.com/)** — AI-based web accessibility solution that automates compliance with ADA and WCAG standards by scanning, remediating, and continuously monitoring websites to ensure accessibility for users with disabilities. `Paid` `Web` `API`
- **[Advanced SystemCare](https://www.iobit.com/en/index.php?s)** — Windows-based PC optimization software by IObit that cleans junk files, optimizes system performance, protects privacy, and removes malware to keep your computer running smoothly. `Freemium` `Windows`
- **[Adviseful](https://adviseful.ai/)** — Chatbot that provides personalized business advice, automates customer support, and delivers data-driven insights to help businesses make informed decisions. `Freemium` `Web`
- **[Afimilk](https://www.afimilk.com/)** — AI-driven dairy farm management system combining IoT sensors and software to monitor cow health, reproduction, and milk production in real-time, helping farmers optimize herd productivity and welfare. `Paid` `Web`
- **[AfterShip](https://www.aftership.com/)** — Shipment tracking platform that consolidates tracking information from over 900 carriers, automates delivery notifications, and provides branded tracking pages to improve e-commerce customer experience. `Freemium` `Web` `API`
- **[Agiloft](https://www.agiloft.com/)** — AI-driven contract management and business process automation platform that helps enterprises automate workflows, manage contracts, and ensure compliance using a customizable no-code environment. `Paid` `Web` `API`
- **[AHelp](https://ahelp.com/)** — Customer support platform that automates helpdesk operations using chatbots and intelligent ticket management to improve response times and customer satisfaction. `Paid` `Free Trial` `Web` `API`
- **[AI Buddy](https://ai-buddy.co/)** — Chatbot platform that helps businesses automate customer support and lead generation through customizable conversational bots and analytics. `Freemium` `Web` `API`
- **[AI Chat Bestie](https://aichatbestie.com/)** — Chatbot platform that automates customer support, lead generation, and conversational assistance primarily in English via a web interface. `Freemium` `Web`
- **[AI Chatbot Hub](https://aichatbothub.com/)** — No-code builder for website and messaging chatbots, aimed at teams that want one deployed without developer time. `Freemium` `Web`
- **[AI Chatroom](https://hi.bulita.net/)** — Free web chatrooms with conversational bots in English and Spanish, usable without creating an account. `Free` `Web`
- **[AI Chat SMS](https://www.aichatsms.com/)** — Builds SMS chatbots for business messaging, so support replies and marketing campaigns run over text rather than a web widget. `Paid` `Free Trial` `Web` `API`
- **[AIChatting](https://www.aichatting.net/)** — Web-based AI chatbot platform that helps businesses automate customer interactions, support, and lead generation with customizable workflows and analytics. `Freemium` `Web`
- **[AiCure](https://aicure.com/)** — Platform that remotely monitors patient medication adherence using video confirmation, primarily for clinical trials and healthcare providers. `Paid` `Web`
- **[AI Engager](https://aiengager.com/)** — Web-based AI chatbot platform designed to automate customer interactions, generate leads, and integrate with CRM systems to improve business engagement. `Paid` `Free Trial` `Web`
- **[AI Grant](https://aigrant.org/)** — Nonprofit platform providing free grant funding specifically for artificial intelligence research and innovation projects, supporting researchers, startups, and organizations. `Free` `Web`
- **[Aii.CX](https://aii.cx/)** — Customer experience platform that automates support with intelligent chatbots and provides analytics to improve customer engagement. `Paid` `Free Trial` `Web` `API`
- **[ai LaMo](https://www.ailamo.com/)** — Chatbot platform that helps businesses automate customer support and engagement with multilingual, customizable chatbots accessible via web and API. `Freemium` `Web` `API`
- **[Aircall](https://aircall.io/)** — Cloud-based VoIP phone system that helps businesses manage inbound and outbound calls with CRM integrations, call routing, and analytics. `Paid` `Free Trial` `Web` `iOS` `Android`
- **[AI Reply](https://ai-reply.work/)** — Web-based AI tool that automates email responses by generating context-aware replies, helping professionals save time and manage inboxes efficiently. `Paid` `Free Trial` `Web`
- **[AI Review Reply Assistant](https://www.mara-solutions.com/)** — Drafts personalized replies to customer reviews, reading sentiment first, and posts them across several review platforms. `Paid` `Free Trial` `Web`
- **[Airship](https://www.airship.com/)** — Customer engagement platform that enables businesses to send personalized push notifications, in-app messages, SMS, and emails to mobile and web users, helping improve retention and conversions through automation and segmentation. `Paid` `Free Trial` `Web` `API`
- **[AI Social Replier](https://replier.social/)** — AI-driven platform that automates responses to comments on Facebook and Instagram posts, enabling faster engagement and improved customer interaction. `Paid` `Free Trial` `Web`
- **[Ai Sofiya](https://aisofiya.com/)** — Chatbot platform that enables businesses to automate customer interactions on websites using a no-code builder and natural language processing. `Freemium` `Web`
- **[AlertMedia](https://www.alertmedia.com/)** — Emergency communication platform that enables organizations to send mass notifications via multiple channels, track employee safety, and manage crisis communications effectively. `Paid` `Web` `API`
- **[Algochat](https://www.algochat.io/)** — Chatbot platform that helps businesses automate customer support and lead generation through an easy visual builder and multi-channel deployment. `Freemium` `Web` `API`
- **[Allego](https://www.allego.com/)** — Sales learning platform that provides video coaching, content management, and mobile learning tools to help sales teams improve skills and accelerate onboarding. `Paid` `Web` `iOS` `Android`
- **[AloAngels](https://www.aloangels.me/)** — Chatbot platform that helps businesses automate customer support and engage users through personalized conversational AI. `Paid` `Free Trial` `Web` `API`
- **[Altermind](https://www.altermind.xyz/)** — AI-driven predictive analytics platform that helps businesses forecast trends, simulate scenarios, and assess risks to make informed decisions. `Paid` `Web`
- **[Amazon](https://www.amazon.com/)** — Global e-commerce platform offering online shopping, seller services, digital content, and cloud computing through AWS. `Freemium` `Web` `iOS` `Android` `API`
- **[Amdocs Fraud Management](https://www.amdocs.com/)** — Telecom-focused software solution that uses AI and real-time analytics to detect, prevent, and manage fraud, helping operators protect revenue and reduce losses. `Paid` `Web` `API`
- **[Anomali](https://www.anomali.com/)** — Cybersecurity threat intelligence platform that aggregates and analyzes threat data to help organizations detect and respond to cyber threats efficiently. `Paid` `Web` `API`
- **[Answer AI](https://answerai.pro/)** — AI-driven customer support platform that combines chatbots and a smart knowledge base to automate responses and improve customer service efficiency. `Paid` `Free Trial` `Web` `API`
- **[AnswerConnect](https://www.answerconnect.com/)** — Virtual receptionist service providing 24/7 live call answering, appointment scheduling, and lead capture to help businesses manage inbound calls professionally. `Paid` `Web`
- **[AnswerTime](https://answerti.me/)** — Chatbot platform that automates customer support by providing instant, conversational responses to website visitors, improving engagement and operational efficiency. `Freemium` `Web` `API`
- **[AppFollow](https://appfollow.io/)** — Platform that centralizes app reviews, tracks keywords for ASO, monitors competitors, and automates review responses to help app marketers and developers improve app visibility and user satisfaction. `Freemium` `Web` `iOS` `Android`
- **[Apptentive](https://apptentive.com/)** — Mobile customer feedback platform that enables app developers to collect real-time user feedback through in-app surveys, ratings, and messaging to improve engagement and product decisions. `Paid` `Free Trial` `Web` `iOS` `Android`
- **[Arkose Labs](https://www.arkoselabs.com/)** — Cybersecurity platform that prevents fraud and automated bot attacks by using adaptive challenge-response tests and real-time risk scoring to secure online accounts and transactions. `Paid` `Web` `API`
- **[Artificial assistance](https://getbot.ai/)** — No-code AI chatbot platform by GetBot AI that automates customer support and lead generation through conversational AI deployed on websites and APIs. `Freemium` `Web` `API`
- **[Arvin - AI Assistant](https://arvin.chat/)** — Web-based chatbot platform that automates customer interactions using natural language processing, helping businesses improve support and lead generation. `Freemium` `Web`
- **[Ask AI - AI Powered Chat Bot Assistant](https://askaichat.app/)** — Web-based AI chatbot assistant that provides instant, natural language responses to user queries for various applications including customer support and content creation. `Freemium` `Web`
- **[AskCory.ai](https://www.askcory.ai/)** — Chatbot platform that helps businesses automate customer support and engagement through personalized conversational workflows and real-time analytics. `Paid` `Free Trial` `Web` `API`
- **[Ask Elle](https://www.askelle.me/)** — Web-based AI chatbot designed for personalized, natural language conversations, customer support, and virtual assistance. `Freemium` `Web`
- **[Askflow AI](https://www.askflow.ai/)** — No-code conversational AI platform that enables businesses to build and deploy chatbots for automating customer support and sales interactions across multiple channels. `Paid` `Free Trial` `Web` `API`
- **[AskGiraffe](https://www.askgiraffe.com/)** — Chatbot that delivers instant answers and conversational support through a web-based interface, suitable for customer service, education, and general inquiries. `Freemium` `Web`
- **[Ask Maya](https://www.askmaya.app/)** — Chatbot platform that automates customer support and lead generation by engaging website visitors with conversational AI. `Freemium` `Web` `API`
- **[AskSpot.ai](https://askspot.ai/)** — Chatbot platform that helps businesses automate customer support and user engagement by creating intelligent chatbots integrated with knowledge bases and deployed on websites or apps. `Freemium` `Web` `API`
- **[AskVideo.ai](https://www.askvideo.ai/)** — AI-driven platform that enables users to ask questions within videos and receive instant, context-aware answers, enhancing engagement in learning and support scenarios. `Freemium` `Web` `API`
- **[Asqme AI](https://asqme.ai/)** — Conversational AI platform that helps businesses automate customer interactions and lead generation through customizable chatbots deployed on websites. `Freemium` `Web`
- **[ASSIST Biz](https://www.assist.biz/)** — Virtual assistant designed to automate customer support, streamline workflows, and enhance business operations through conversational AI. `Paid` `Free Trial` `Web` `API`
- **[Atozai](https://atozai.in/)** — No-code chatbot platform designed to automate customer interactions across multiple channels, improving support and engagement. `Freemium` `Web` `API`
- **[ATZ CRM](https://atzcrm.com/)** — Cloud-based customer relationship management platform designed for small and medium businesses to manage sales, marketing automation, and customer support efficiently. `Paid` `Free Trial` `Web`
- **[Authy](https://www.authy.com/)** — Two-factor authentication app that provides an extra security layer by generating time-based codes and push notifications to verify user identities across multiple devices. `Freemium` `Web` `iOS` `Android`
- **[Autismify](https://autismify.com/)** — AI-based speech therapy platform designed to help children with autism improve communication through personalized exercises and progress tracking. `Freemium` `Web`
- **[Axonify](https://axonify.com/)** — Employee training platform that delivers personalized microlearning and gamified experiences to improve workforce knowledge, engagement, and compliance. `Paid` `Web`

## Research and knowledge

Literature search, citation work, and knowledge management.

- **[10xWinners OKR](https://10xwinners.com/)** — Web platform that helps organizations set, track, and manage Objectives and Key Results to improve alignment and performance through agile goal management. `Paid` `Free Trial` `Web`
- **[1MB V4](https://1mb.co/)** — Lightweight web performance monitoring tool that provides real-time analytics and actionable recommendations to optimize website speed and user experience. `Freemium` `Web`
- **[2Slash](https://2slash.ai/)** — URL shortening tool that provides branded short links, detailed click analytics, and QR code generation to help marketers and businesses optimize their link sharing and track engagement. `Freemium` `Web`
- **[7Assets](https://7assets.app/)** — Cloud-based asset management tool designed to help businesses track, maintain, and audit physical assets efficiently through web and mobile platforms. `Freemium` `Web`
- **[A11YBoost](https://a11yboost.com/)** — Web-based tool that automates accessibility testing by scanning websites for WCAG compliance issues, generating detailed reports, and offering remediation guidance to improve web accessibility. `Paid` `Free Trial` `Web`
- **[aasaan](https://admin.aasaan.app/)** — No-code admin panel builder that enables users to create customizable backend dashboards for web applications without coding, featuring drag-and-drop design, data integration, and role-based access control. `Freemium` `Web`
- **[Academia.edu](https://www.academia.edu/)** — Academic social networking platform that enables researchers to share papers, discover research, and connect with peers globally. `Freemium` `Web` `iOS` `Android`
- **[AcademicGPT](https://academicgpt.net/)** — Writing assistant designed to help students and researchers write, edit, and format academic papers efficiently. `Freemium` `Web`
- **[AceEssay](https://aceessay.ai/en)** — Writing assistant that generates essays and academic papers based on user prompts, offering grammar correction and content rewriting features. `Freemium` `Web`
- **[adfonic.com](https://www.adfonic.com/)** — UK-based mobile advertising platform that provides a demand-side platform (DSP) for programmatic buying of mobile ad inventory, helping app developers monetize and advertisers acquire users through real-time bidding and advanced targeting. `Paid` `Web` `API`
- **[AdGen AI](https://www.adgenai.com/)** — Platform that automates the creation, optimization, and management of digital ads across multiple platforms, helping marketers generate effective ads and improve campaign performance. `Freemium` `Web`
- **[Adola: Voice & Phone Number for your AI](https://adola.ai/)** — Communication platform providing virtual phone numbers and realistic AI voice calls to automate business phone interactions such as customer support and marketing. `Paid` `Free Trial` `Web` `API`
- **[Adthena](https://www.adthena.com/)** — AI-driven competitive intelligence platform that analyzes PPC and search advertising data to help marketers optimize campaigns by uncovering competitor strategies, keywords, and ad copy insights. `Paid` `Web`
- **[AFAnotes - AI Productivity](https://www.afanotes.com/)** — Productivity tool that streamlines note taking, task management, and collaboration by using artificial intelligence to organize content, generate summaries, and prioritize tasks. `Freemium` `Web`
- **[AgapeVerse.app](https://agapeverse.app/)** — Web-based NFT marketplace that allows users to mint, buy, sell, and manage digital art and collectibles securely on the blockchain. `Freemium` `Web`
- **[AgentQL](https://www.agentql.com/)** — Platform that converts natural language questions into SQL queries, enabling users to interact with databases without coding. `Paid` `Free Trial` `Web` `API`
- **[ai4spaces](https://ai4spaces.com/)** — Web-based AI interior design tool that generates optimized room layouts and 3D visualizations to assist users in space planning and interior design. `Freemium` `Web`
- **[AI Agent Store](https://aiagentstore.ai/)** — No-code builder for creating and deploying agents that handle automation and customer conversations, with no programming required. `Freemium` `Web`
- **[Ai Application Catalogue](https://juanbeltran.ch/)** — Free online directory curated by Juan BeltrÃƒÂ¡n that lists and categorizes AI applications across various industries, helping users discover and explore AI tools easily. `Free` `Web`
- **[AI-assisted Contember Studio](https://www.contember.com/)** — Contember Studio is an AI-assisted headless CMS and backend development platform that simplifies content modeling and automatically generates GraphQL and REST APIs for frontend integration. `Freemium` `Web`
- **[AI Badge](https://aibadge.org/)** — Free web-based tool that verifies AI-generated content and issues a standardized badge to indicate authenticity, promoting transparency and trust. `Free` `Web`
- **[AI Coloring Page Generator](https://www.bestcoloringpages.ai/)** — AI Coloring Page Generator creates custom printable coloring sheets using AI based on user input keywords or themes. `Freemium` `Web`
- **[AI Comic Generator](https://aicomicgenerator.net/)** — Web tool that uses AI to create comic strips by generating artwork and text bubbles from user input, enabling easy comic creation without drawing skills. `Freemium` `Web`
- **[AI Disturbance Overlay](https://aidisturbance.online/)** — Free web-based tool that applies real-time AI-generated noise and visual disturbance overlays to images and videos, enabling creators to add unique artistic effects without installation. `Free` `Web`
- **[AI Face Analyzer-Beauty Score Calculator](https://aifaceanalyzer.online/)** — Free web tool that uses AI to analyze facial features and generate a beauty score based on symmetry and proportions. `Free` `Web`
- **[AIFreeBox: Free AI Tools](https://aifreebox.com/)** — Free online platform that curates and provides access to a wide variety of no-cost AI tools across multiple categories, enabling users to discover and use AI utilities without payment or registration. `Free` `Web`
- **[AI Insult Generator](https://aiinsults.com/)** — Free web-based tool that creates humorous and creative insults instantly for entertainment and creative use. `Free` `Web`
- **[AI is a Joke](https://aiisajoke.com/maintenance)** — Joke is a free web platform that generates humorous and satirical AI content for entertainment and creative inspiration. `Free` `Web`
- **[AI Prank Call](https://prankcaller.fun/)** — Free web-based tool that lets you make prank calls using AI-generated voices and voice-changing features without installing software. `Free` `Web`
- **[AI Psychic Reading by Tarotoo](https://tarotoo.com/)** — AI Psychic Reading by Tarotoo provides free, instant tarot card readings generated by artificial intelligence to offer personal insights and guidance. `Free` `Web`
- **[Airbrush](https://www.airbrush.ai/)** — Mobile photo editor for selfies and portraits, with live skin smoothing, blemish removal, and makeup effects. `Freemium` `iOS` `Android`
- **[AirBrush Studio](https://airbrush.com/)** — Online photo editing tool focused on beauty retouching and creative filters, accessible via web browsers without installation. `Freemium` `Web`
- **[AirCMP](https://aircmp.app/)** — AI-driven competitive market analysis tool that automates data collection and provides actionable insights to help businesses monitor competitors and optimize strategies. `Paid` `Free Trial` `Web`
- **[airgeek](https://www.airgeek.link/)** — Web-based tool that shortens URLs and generates QR codes with tracking analytics, designed for marketers and businesses to optimize campaigns. `Freemium` `Web`
- **[AirSim](https://microsoft.github.io/)** — Free, open-source simulator developed by Microsoft that provides realistic environments and sensor models for autonomous vehicle and drone research, enabling safe AI training and testing. `Free` `Open Source` `Windows` `macOS` `Linux`
- **[AI Song](https://aisong.fun/)** — Free online tool that uses artificial intelligence to generate original songs and lyrics based on user input, making music creation accessible to everyone. `Free` `Web`
- **[AI-Spy](https://www.ai-spy.xyz/)** — AI-driven platform that helps businesses monitor competitors and analyze market trends through real-time data aggregation and automated reporting. `Freemium` `Web`
- **[AI Tarot Master](https://tarotnova.ai/)** — Online tool that uses artificial intelligence to generate tarot card readings with detailed interpretations and multiple spread options. `Freemium` `Web`
- **[AITDK](https://aitdk.com/)** — AI-driven platform that centralizes data knowledge and automates workflows to improve business efficiency. `Freemium` `Web`
- **[AI to Human](https://aitohuman.org/)** — Free web platform that promotes ethical collaboration among AI developers, policymakers, and communities to ensure responsible AI innovation. `Free` `Web`
- **[aiupdatesnow.com](https://aiupdatesnow.com/)** — Free online platform that aggregates and curates the latest news and updates about artificial intelligence and machine learning, helping users stay informed about current AI trends and technologies. `Free` `Web`
- **[AI VisionBoard](https://ai-visionboard.com/)** — Web-based tool that uses AI to generate images and layouts for creating personalized vision boards, helping users visualize and achieve their goals. `Freemium` `Web`
- **[AI World Today](https://www.aiworldtoday.net/)** — Free online platform providing daily news, expert analysis, and research updates on artificial intelligence. `Free` `Web`
- **[AI yes-or-no tarot reader](https://yesnotarot.org/)** — Free online tool that provides instant yes-or-no answers to your questions by simulating tarot card readings using AI. `Free` `Web`
- **[Akkadu AI Subtitles](https://akkadu.ai/)** — AI-driven platform that automatically generates, translates, and synchronizes subtitles for videos in multiple languages, supporting both pre-recorded and live content. `Paid` `Web` `API`
- **[allganize.ai](https://www.allganize.ai/)** — Enterprise AI platform specializing in natural language processing to automate document understanding, semantic search, and customer support through AI chatbots. `Paid` `Web` `API`
- **[All Search AI](https://allsearch.ai/)** — Universal search engine that aggregates information from multiple sources and uses semantic understanding to deliver relevant, comprehensive search results quickly. `Freemium` `Web`
- **[AlphaResearch](https://alpharesearch.io/)** — AI-driven platform that automates market research by enabling users to create surveys, analyze data in real time, and generate actionable insights to support business decisions. `Freemium` `Web`
- **[AlTable.ai: No-code Al Agents Builder](https://aitable.ai/)** — No-code platform that lets users create custom AI agents to automate tasks and workflows by integrating data and APIs without programming skills. `Freemium` `Web`
- **[Amarkdown](https://amarkdown.com/)** — Free, minimalist web-based markdown editor that provides live preview and supports standard markdown syntax without requiring signup. `Free` `Web`
- **[Analogenie](https://analogenie.com/)** — Writing assistant designed to help users generate, edit, and improve creative and technical content through advanced natural language processing. `Freemium` `Web`
- **[anvsoft.com](https://www.anvsoft.com/)** — Anvsoft provides multimedia software for converting video and audio files, ripping DVDs, and basic video editing on Windows and Mac platforms. `Paid` `Free Trial` `Windows` `macOS`
- **[Anyscale | Scalable Compute for AI and Python](https://www.anyscale.com/)** — Managed cloud platform that simplifies scaling Python and AI applications using the Ray framework, providing autoscaling clusters, multi-cloud support, and developer tools for distributed computing. `Freemium` `Web` `API`
- **[AppAI](https://appai.co.uk/)** — UK no-code platform for prototyping mobile apps quickly, aimed at validating an idea before committing to a build. `Freemium` `Web`
- **[AppBuzz](https://www.appbuzz.ai/)** — AI-driven app store analytics platform that provides real-time data, competitor benchmarking, keyword analysis, and market insights to help mobile app developers and marketers optimize growth and visibility. `Freemium` `Web`

## Business and finance

Finance, legal, human resources, commerce, and operations.

- **[2020 Background Screening](https://www.2020screening.com/)** — 2020 Background Screening provides detailed employment and tenant background checks, drug testing, and compliance tools to help businesses make informed hiring and leasing decisions. `Paid` `Web`
- **[202 QUALITY APPS](https://app.quality.de/guest)** — Web-based quality management software that helps organizations digitize quality assurance, audit management, and compliance processes to improve efficiency and maintain standards. `Paid` `Web`
- **[Aave](https://aave.com/)** — Decentralized finance protocol that allows users to lend and borrow cryptocurrencies without intermediaries, featuring flash loans and community governance. `Free` `Web` `API`
- **[AccountingSolverAI](https://accountingsolver.com/)** — Accounting software that automates bookkeeping, invoice processing, and financial reporting to help businesses reduce manual work and improve accuracy. `Freemium` `Web` `API`
- **[Addepar](https://addepar.com/)** — Financial technology platform that aggregates and analyzes complex investment portfolios, providing wealth managers and advisors with customizable reporting and client communication tools. `Paid` `Web` `API`
- **[Afterpay](https://www.afterpay.com/global/country-select)** — Buy Now Pay Later service that lets consumers split online purchases into four interest-free payments, improving affordability and cash flow management. `Free` `Web` `iOS` `Android`
- **[Agree.com](https://agree.com/)** — Web-based contract management platform that enables users to create, collaborate on, sign, and manage digital agreements with workflow automation and e-signature capabilities. `Paid` `Free Trial` `Web`
- **[Agreee.ai](https://www.agreee.ai/)** — AI-driven contract review platform that automates legal document analysis, identifies risks, and facilitates collaboration to speed up contract management. `Freemium` `Web`
- **[AI Amazon Product Reviews / Manuals](https://productreviewgpt.com/)** — Web tool that uses AI to generate detailed product reviews and manuals from Amazon product data, helping sellers and buyers quickly understand product features and customer feedback. `Freemium` `Web`
- **[AI Bookkeeping](https://bookeeping.ai/en)** — Web-based software that automates bookkeeping by categorizing transactions, tracking expenses, and generating financial reports using artificial intelligence. `Paid` `Free Trial` `Web`
- **[AI Garage Sale](https://www.aigaragesale.com/)** — Online marketplace that helps users buy and sell used items with AI-assisted price suggestions and personalized recommendations. `Freemium` `Web`
- **[AI Gift Guru](https://aigiftguru.com/)** — AI-driven platform that provides personalized gift recommendations based on recipient details and occasion, helping users find thoughtful gifts quickly. `Freemium` `Web`
- **[AIJobs.com](https://www.aijobs.com/)** — Free online platform that aggregates AI and tech job listings, helping job seekers find relevant AI career opportunities and employers to post AI-related job openings. `Free` `Web`
- **[AI Law](https://www.ai.law/)** — UK-based legal technology platform that uses artificial intelligence to automate contract review, risk assessment, and legal document drafting, helping legal teams improve efficiency and accuracy. `Paid` `Web`
- **[AI Lawyer](https://ailawyer.pro/)** — AI-driven legal tech platform that automates contract drafting and document review to help legal professionals and businesses save time and reduce errors. `Freemium` `Web`
- **[AI Lawyer Lab](https://ailawyerlab.com/)** — AI-driven platform that helps legal professionals draft, review, and automate legal documents efficiently using customizable templates and natural language processing. `Freemium` `Web`
- **[Ain Finance](https://ain.finance/)** — Decentralized finance platform that allows users to earn rewards through yield farming, token staking, and liquidity mining, with governance features for token holders. `Free` `Web`
- **[AI PDF bank statement parser](https://aibankparser.com/)** — Web-based tool that uses AI and OCR to automatically extract transaction and account data from PDF bank statements, enabling faster financial data processing and integration. `Paid` `Free Trial` `Web`
- **[AiPrice](https://aiprice.dev/)** — AI-driven dynamic pricing tool that helps e-commerce businesses optimize product prices in real-time by analyzing market demand, competitor pricing, and inventory data. `Freemium` `Web`
- **[AI Product Shot](https://www.aiproductshot.com/)** — Web-based AI tool that generates customizable, high-quality product images for e-commerce businesses, eliminating the need for traditional photography. `Paid` `Free Trial` `Web`
- **[AI Profile For Slack](https://orgengage.com/)** — Slack integration by OrgEngage that automatically generates and updates detailed employee profiles within Slack to improve team collaboration and engagement. `Freemium` `Web`
- **[aiRight](https://airight.io/)** — AI-driven contract review platform that automates the analysis of legal documents to identify risks, obligations, and key clauses, helping legal teams speed up contract review processes. `Paid` `Free Trial` `Web`
- **[Aixpertrecruit](https://aixpertrecruit.com/)** — AI-driven recruitment platform that automates candidate sourcing, resume screening, interview scheduling, and talent pipeline management to help recruiters hire efficiently. `Paid` `Web`
- **[Akeneo](https://www.akeneo.com/)** — Product Information Management (PIM) platform that centralizes, enriches, and distributes product data to improve accuracy and consistency across sales channels. `Paid` `Free Trial` `Web`
- **[Algobash.com](https://www.algobash.com/en/)** — Coding assistant that helps generate code snippets, debug errors, and explain programming concepts through a web-based interface supporting multiple languages. `Freemium` `Web`
- **[AlgoDocs](https://algodocs.com/)** — AI-driven document automation platform designed to help legal and business teams automate contract drafting, collaborate efficiently, and streamline document workflows. `Paid` `Free Trial` `Web`
- **[AlgoVue](https://algovue.app/)** — AI-driven trading platform that enables users to build, backtest, and automate algorithmic trading strategies for cryptocurrencies and stocks without requiring advanced coding skills. `Freemium` `Web` `API`
- **[AliDropship](https://alidropship.com/)** — WordPress plugin that automates dropshipping by importing products from AliExpress, automating order fulfillment, and managing pricing and inventory for WooCommerce stores. `Paid` `Free Trial` `Web`
- **[AliExpress](https://ar.aliexpress.com/?gatewayAdapt=glo2ara)** — Global e-commerce platform owned by Alibaba Group that connects buyers and sellers worldwide, offering a wide range of products at competitive prices with buyer protection and international shipping. `Free` `Web` `iOS` `Android`
- **[AlphaSense](https://www.alpha-sense.com/)** — AI-driven market intelligence platform that helps businesses and investors quickly find and analyze financial documents, news, and research reports to make informed decisions. `Paid` `Web` `API`
- **[Alpha Vantage](https://www.alphavantage.co/)** — Financial data platform providing free and premium APIs for real-time and historical stock, forex, and cryptocurrency market data, including technical indicators, suitable for developers and analysts. `Freemium` `Web` `API`
- **[Anaplan](https://www.anaplan.com/)** — Cloud-based enterprise planning platform that enables connected planning across finance, sales, operations, and HR to improve decision-making and agility. `Paid` `Web` `API`
- **[Andela](https://www.andela.com/)** — Platform that connects companies with vetted remote software developers globally, offering flexible hiring models and ongoing support to scale engineering teams efficiently. `Paid` `Web`
- **[Anjuke](https://www.anjuke.com/)** — Chinese online real estate platform providing property listings, market data, and tools to help users buy, sell, or rent properties in China. `Free` `Web`
- **[Anonos](https://anonos.com/)** — Data privacy platform that uses patented privacy-enhancing technologies to protect sensitive data, enable secure sharing, and ensure compliance with regulations like GDPR and CCPA. `Paid` `Web` `API`
- **[Anyoneswap](https://www.anyoneswap.com/)** — Decentralized exchange platform that facilitates secure cross-chain token swaps without intermediaries, allowing users to trade cryptocurrencies across multiple blockchains while retaining control of their assets. `Free` `Web`
- **[ApplicantAI](https://applicantai.com/)** — Recruitment tool that automates resume screening and candidate matching to streamline hiring processes and improve candidate selection accuracy. `Paid` `Web`
- **[Apply AI](https://apply-ai.work/)** — AI-driven platform that automates job applications, optimizes resumes, and helps job seekers manage their job search efficiently. `Paid` `Free Trial` `Web`
- **[ApplyPass](https://www.applypass.com/)** — Web-based recruitment platform that streamlines job application management, applicant tracking, and team collaboration to simplify hiring processes. `Paid` `Free Trial` `Web`
- **[Apply Pro](https://applypro.ai/)** — AI-driven recruitment platform that automates candidate screening, tracks applicants, and facilitates interview scheduling to streamline hiring processes. `Paid` `Free Trial` `Web`
- **[ArguAI](https://arguai.co/)** — Tool that generates structured arguments and counterarguments to assist with debates, writing, and critical thinking. `Freemium` `Web`
- **[assess.com](https://assess.com/)** — Online platform providing customizable employee assessments including cognitive, personality, and skills tests to improve hiring decisions and employee development. `Paid` `Web`
- **[AstroStock AI](https://astrostock.ai/)** — Web-based platform that uses AI to analyze stock market data and provide predictive insights to help investors make informed decisions. `Freemium` `Web`
- **[Atlancer.ai](https://atlancer.ai/)** — AI-driven freelance platform that matches businesses with expert freelancers globally, streamlining hiring and project management. `Freemium` `Web`
- **[Aurum KuberX](https://aurumkuberx.com/)** — Indian digital investment platform offering portfolio management, personalized advisory, and mutual fund investments through web and mobile apps. `Paid` `Web`
- **[AutoApply](https://www.autoapply.us/)** — Web-based tool that automates job applications by filling out forms and submitting resumes across multiple job boards, helping job seekers save time and stay organized. `Paid` `Free Trial` `Web`
- **[Autodoc](https://autodocai.com/)** — Tool that automatically generates and maintains software documentation from source code, helping developers save time and improve clarity. `Freemium` `Web` `API`
- **[Auto Market Scanner](https://automarketscanner.com/)** — Web platform that automates stock market scanning using customizable technical filters to help traders identify potential trades quickly. `Paid` `Free Trial` `Web`
- **[Autoscreen](https://autoscreen.io/)** — AI-driven video interview platform that automates candidate screening through asynchronous interviews and AI analysis to help recruiters make faster, unbiased hiring decisions. `Paid` `Web`
- **[Avalara](https://www.avalara.com/us/en/index.html)** — Cloud-based tax compliance software that automates sales tax calculation, exemption certificate management, and tax filing to help businesses stay compliant across multiple jurisdictions. `Paid` `Web` `API`
- **[Ava PLS](https://avapls.com/)** — AI-driven platform that automates legal document review by extracting key contract clauses and identifying risks to accelerate legal workflows. `Paid` `Web`
- **[Ballotpedia](https://ballotpedia.org/)** — Free, nonpartisan digital encyclopedia providing detailed information on American elections, candidates, and government officials to help voters make informed decisions. `Free` `Web`
- **[BambooHR](https://www.bamboohr.com/)** — Cloud-based human resources software designed to help small and medium businesses manage employee data, recruitment, performance, and time-off tracking efficiently. `Paid` `Free Trial` `Web`
- **[Bank Statement Convert](https://bankstatementconvert.com/)** — Online tool that converts bank statements from PDFs or images into editable Excel spreadsheets or standardized PDFs, helping users manage financial data efficiently. `Freemium` `Web`
- **[Bank Statement Converter](https://bankstatementconverter.org/)** — Online tool that converts PDF bank statements into Excel and CSV formats, enabling easy data extraction and financial management. `Freemium` `Web`

## Health and lifestyle

Health, fitness, travel, food, and personal life.

- **[12min](https://12min.com/)** — Microlearning platform providing 12-minute text and audio summaries of nonfiction books to help users quickly grasp key concepts. `Freemium` `Web` `iOS` `Android`
- **[1440 - Time on Purpose](https://1440.ai/)** — AI-driven daily planner that helps users allocate their 1440 minutes each day intentionally to improve productivity, focus, and goal achievement through personalized scheduling. `Freemium` `Web`
- **[1Password](https://1password.com/)** — Secure password manager that stores and autofills passwords, manages two-factor authentication, and enables safe sharing for individuals and teams. `Paid` `Free Trial` `Web` `Windows` `macOS` `Linux` `iOS` `Android`
- **[3D Aim Trainer](https://www.3daimtrainer.com/)** — Web-based FPS aiming training tool that helps gamers improve accuracy, reaction time, and mouse control through customizable drills and performance tracking. `Freemium` `Web`
- **[3M Health Information Systems](https://3m.com/)** — 3M Health Information Systems offers healthcare IT solutions focused on clinical documentation improvement, automated medical coding, and health data analytics to improve patient care and revenue cycle management. `Paid` `Web` `API`
- **[7 Cups](https://www.7cups.com/)** — Online platform providing free anonymous emotional support via trained volunteer listeners and paid professional therapy sessions to help users manage mental health challenges. `Freemium` `Web` `iOS` `Android`
- **[Aaptiv](https://aaptiv.com/)** — Subscription-based fitness app providing AI-personalized audio workouts and training plans led by certified trainers, designed for flexible, screen-free exercise. `Paid` `Web` `iOS` `Android`
- **[Abide](https://abide.com/)** — AI-driven Christian meditation app providing personalized guided prayers, Bible readings, and mindfulness meditations to support spiritual growth and mental wellness. `Freemium` `Web` `iOS` `Android`
- **[Accountable2You](https://accountable2you.com/)** — Parental control and accountability software that helps families and individuals monitor device usage, receive alerts on risky content, and manage screen time across multiple platforms. `Paid` `Web` `Windows` `macOS` `iOS` `Android`
- **[ADDitude ADHD Test](https://additudemag.com/)** — Free online screening tool that helps adults and parents assess potential ADHD symptoms through clinically-informed questionnaires, providing immediate feedback and educational resources. `Free` `Web`
- **[ADHDtest.ai](https://adhdtest.ai/)** — Online platform offering a validated ADHD screening test for adults and children, providing quick preliminary results and optional detailed reports to help identify potential ADHD symptoms. `Free` `Web`
- **[ai4good.org](https://ai4good.org/)** — Nonprofit platform dedicated to promoting ethical artificial intelligence and facilitating AI projects that address social challenges through community collaboration and educational resources. `Free` `Web`
- **[AI Blood Test Analysis](https://blood-test.io/)** — Web service that reads uploaded blood test results and returns plain-language explanations, flagged risks, and follow-up suggestions. `Freemium` `Web`
- **[AI Cupid](https://www.aicupid.net/)** — Web tool that helps users generate and optimize dating profiles and messages to improve online dating success. `Freemium` `Web`
- **[AI Dating Bio Generator](https://aidating.bio/)** — Web tool that creates personalized dating bios using AI to help users craft engaging online profiles quickly. `Freemium` `Web`
- **[AI Dating Coach](https://www.dating-coach.ai/)** — Platform providing personalized advice to improve online dating profiles, messaging, and confidence for better dating outcomes. `Freemium` `Web`
- **[AI Diary](https://aidiary.io/)** — Personal journaling and mood tracking app that uses AI to assist with writing, analyze emotional patterns, and provide personalized prompts to support mental wellness. `Freemium` `Web` `iOS` `Android`
- **[Aidoc](https://www.aidoc.com/)** — AI-driven medical imaging software that helps radiologists detect abnormalities in CT and MRI scans, prioritize urgent cases, and improve diagnostic workflows. `Paid` `Web` `API`
- **[AI Dungeon](https://aidungeon.com/)** — AI-driven platform that generates interactive text-based stories and roleplaying adventures dynamically based on user input. `Freemium` `Web` `iOS` `Android`
- **[AI Flirting Helper](https://flirtypickuplines.com/)** — Free web tool that generates creative pickup lines and romantic messages to assist users in dating and social conversations. `Free` `Web`
- **[AI images for hospitality providers](https://colossis.io/blog/sub-015-lpips-cuts-time-to-contract-17-in-2026-mls-data.php)** — Colossis generates marketing photography for hotels and hospitality operators, producing customized visuals without a studio shoot. `Freemium` `Web`
- **[AI Meal Planner](https://ai-mealplan.com/)** — Web-based tool that uses artificial intelligence to generate personalized weekly meal plans and grocery lists based on your dietary preferences, restrictions, and nutritional goals. `Freemium` `Web`
- **[AI Minecraft](https://aiminecraft.ai/)** — Assistant and mod tool that enhances Minecraft gameplay by providing building assistance, strategic guidance, and creative content generation within the game. `Freemium` `Web`
- **[AI Pickup Lines](https://aipickuplines.com/)** — Free web tool that instantly generates creative and humorous pickup lines to help users start conversations in dating or social settings. `Free` `Web`
- **[AI Recipe Writer](https://airecipewriter.com/landing)** — Web-based tool that uses artificial intelligence to generate customized recipes based on user inputs like ingredients and dietary preferences. `Freemium` `Web`
- **[Airn - Your AI Personal Growth Coach](https://airn.ai/)** — Personal growth coach that provides tailored coaching, mindfulness guidance, and habit tracking to help users improve mental wellness and achieve personal goals. `Freemium` `Web`
- **[AiroMedical](https://airomedical.com/)** — AI-driven platform that assists radiologists by analyzing medical images such as X-rays and CT scans to detect abnormalities and support diagnostic decisions. `Paid` `Web` `API`
- **[AirTrackBot](https://airtrackbot.com/)** — Free tool that forecasts airfare trends from historical prices, so travelers can judge when to book. `Free` `Web`
- **[AI Santa Claus](https://santa.ac/)** — Web-based platform that generates personalized video messages featuring a virtual Santa Claus using AI voice and facial animation technology. `Free` `Web`
- **[AISOAP - AI SOAP Notes](https://aisoap.com/)** — Tool that generates structured SOAP notes from clinical inputs, streamlining medical documentation for healthcare professionals. `Paid` `Free Trial` `Web`
- **[AI Therapy](https://abby.gg/)** — Chatbot by Abby AI that provides anonymous, empathetic mental health support and emotional wellbeing assistance through conversational AI. `Freemium` `Web`
- **[aiTherapyCall: Mind-Blowing AI Therapy!](https://aitherapycall.com/)** — Mental health platform providing conversational therapy and emotional support through an empathetic chatbot accessible via web. `Freemium` `Web`
- **[AI Travel Selfies](https://itraveledthere.io/blog/stanford-2026-ai-detection-dead-search-volume-gates-roi.php)** — Web tool that lets users upload a photo and generate realistic selfies at famous travel destinations using AI image synthesis. `Free` `Web`
- **[AI Word Solver](https://www.aiwordsolver.com/)** — Free online tool that helps users solve word puzzles like crosswords and anagrams by generating possible word matches based on input letters or patterns. `Free` `Web`
- **[Ai Workout Generator](https://www.aiworkoutgenerator.com/)** — AI Workout Generator creates personalized workout plans using AI based on your fitness level, goals, and available equipment, helping you train effectively at home or gym. `Freemium` `Web`
- **[Allrecipes](https://allrecipes.com/)** — Free online platform offering a vast collection of user-generated recipes, meal planning tools, and a cooking community to help users discover, save, and share recipes. `Free` `Web` `iOS` `Android`
- **[AllTrails](https://www.alltrails.com/)** — App that helps users find, navigate, and track hiking and outdoor trails with GPS, offline maps, and community reviews. `Freemium` `Web` `iOS` `Android`
- **[Alya](https://alyatherapist.xyz/)** — Free wellbeing chatbot offering supportive conversation, mental-health screening questions, and coping strategies. `Free` `Web`
- **[Amadeus Travel API](https://developers.amadeus.com/)** — Developer platform offering RESTful APIs to access global flight, hotel, and travel data for building travel booking and itinerary management applications. `Freemium` `Web` `API`
- **[amara](https://amara.care/)** — Cloud-based home health software that helps agencies manage caregiver scheduling, patient care, billing, payroll, and compliance efficiently. `Paid` `Web`
- **[AMBLR - AI Travel Planner](https://amblr.xyz/)** — Travel planner that creates personalized trip itineraries based on your preferences, travel dates, and budget, helping you plan multi-destination trips with budget estimates and customizable plans. `Freemium` `Web`
- **[Any.do](https://www.any.do/)** — Task management and to-do list app that helps users organize tasks, set reminders, sync calendars, and collaborate with others across multiple platforms. `Freemium` `Web` `iOS` `Android` `Browser Extension`
- **[AnyList](https://www.anylist.com/)** — Grocery shopping and meal planning app that helps users create organized shopping lists, save and manage recipes, plan meals on a calendar, and share lists with others for collaborative shopping. `Freemium` `Web` `iOS` `Android`
- **[Apollo Health MD](https://apollohealth.ai/)** — Platform that analyzes medical images to assist radiologists and clinicians in diagnosing diseases more accurately and efficiently. `Paid` `Web` `API`
- **[AquaAdvisor-AI water tracker](https://www.fitboxlab.io/)** — Hydration monitoring tool that uses AI to provide personalized water intake recommendations and track hydration for improved health. `Freemium` `Web`
- **[Arterys](https://arterys.com/)** — Cloud-based AI medical imaging platform that provides FDA-cleared tools for automated analysis of MRI, CT, and ultrasound images to assist radiologists in diagnosis and treatment planning. `Paid` `Web` `API`
- **[artivatic.ai](https://artivatic.ai/)** — Platform specializing in automating insurance and healthcare processes like underwriting and fraud detection through machine learning. `Paid` `Web` `API`
- **[AsthmaMD](https://asthmamd.com/)** — Mobile and web app designed to help individuals with asthma track symptoms, manage medications, and create personalized asthma action plans to improve respiratory health. `Freemium` `Web` `iOS` `Android`
- **[Astra Health AI](https://astrahealth.ai/)** — Platform that analyzes medical images to assist healthcare professionals in diagnosing diseases more accurately and efficiently. `Paid` `Web` `API`
- **[Astro Gold](https://www.astrogold.io/)** — Professional astrology app for iOS and macOS that provides accurate natal charts, transit and progression analysis, and detailed astrological reports. `Paid` `macOS` `iOS`

## SEO and search

Keyword research, search visibility, technical SEO, and rank tracking.

- **[2 Weeks AI](https://2weeks.ai/)** — AI-driven platform that helps marketers and content creators generate marketing copy, blog posts, and SEO-friendly articles efficiently using customizable templates and advanced AI models. `Freemium` `Web`
- **[aabo](https://aabo.in/)** — Indian writing assistant that drafts search-oriented content from templates, with keyword targeting built into the editor. `Freemium` `Web`
- **[AIArion](https://aiarion.com/)** — Writing assistant that generates SEO-friendly content, including blog posts and marketing copy, to help users create high-quality text efficiently. `Paid` `Free Trial` `Web`
- **[AI Blog Articles](https://getaiblogarticles.com/)** — Web-based AI content generation tool that helps users create SEO-friendly blog posts efficiently by inputting topics or keywords and customizing tone and length. `Paid` `Free Trial` `Web`
- **[AiCogni](https://aicogni.com/)** — Writing assistant designed to generate SEO-friendly content, marketing copy, and blog posts efficiently for content creators and marketers. `Paid` `Free Trial` `Web`
- **[AI Collective](https://getaicollective.in/)** — AI-driven platform that helps marketers and businesses generate high-quality content such as blogs, social media posts, and ad copies quickly and efficiently. `Freemium` `Web`
- **[AIGIFY](https://www.aigify.com/)** — Content platform for marketers and search teams, producing optimized copy and blog drafts from templates. `Freemium` `Web`
- **[Aiglot](https://aiglot.com/)** — Writing assistant that generates SEO-friendly content, blog posts, and marketing copy with customizable tone and style. `Freemium` `Web`
- **[AI Keywords To Posts](https://aiktp.com/)** — Web tool that converts your keywords into full blog posts using AI, helping you automate content creation efficiently. `Paid` `Free Trial` `Web`
- **[AINIRO](https://ainiro.io/)** — Writing assistant designed to help marketers and content creators generate SEO-friendly content and marketing copy quickly and efficiently. `Paid` `Free Trial` `Web`
- **[AiPakistani](https://aipakistani.com/)** — Writing assistant platform from Pakistan that helps users generate SEO-friendly content in English and Urdu for blogs, social media, and marketing. `Freemium` `Web`
- **[AirASO - Easy App Store Optimization with AI](https://airaso.co/)** — AI-driven platform that helps mobile app developers and marketers optimize their app store listings through keyword research, competitor analysis, and metadata optimization to improve app visibility and downloads. `Freemium` `Web`
- **[AirFry.ai](https://www.airfry.ai/)** — Writing assistant designed to generate and optimize content such as blog posts, marketing copy, and SEO-friendly text through an easy-to-use web platform. `Freemium` `Web`
- **[AIrticle flow](https://airticle-flow.com/)** — Writing assistant that generates SEO-friendly articles and marketing content to help users create high-quality text efficiently. `Freemium` `Web`
- **[AiScribbler](https://aiscribbler.co/)** — Writing assistant that generates and optimizes content for blogs, marketing, and SEO purposes, helping users create quality text faster. `Freemium` `Web`
- **[AISEO](https://aiseo.ai/)** — Content generation platform designed to create SEO-optimized articles, blog posts, and meta descriptions, helping marketers and bloggers produce high-quality content efficiently. `Paid` `Free Trial` `Web`
- **[AI Stock Keywords](https://www.aistockkeywords.com/)** — AI-driven keyword research tool tailored for stock market and finance content creators to find relevant keywords and optimize SEO strategies. `Freemium` `Web`
- **[Aistro](https://www.aistro.io/)** — Writing assistant that generates and optimizes SEO-friendly content for blogs, marketing, and more through a user-friendly web platform. `Paid` `Free Trial` `Web`
- **[AI Suggests](https://ai-suggests.com/)** — AI-driven platform that provides marketers and content creators with relevant content ideas and SEO keyword suggestions to improve marketing effectiveness. `Freemium` `Web`
- **[Aiter.io](https://aiter.io/)** — Writing assistant that helps users generate SEO-optimized content, blog posts, and marketing copy through an easy-to-use web platform. `Freemium` `Web`
- **[AI Tool Hunt](https://aitoolhunt.com/)** — Free online platform that aggregates and categorizes thousands of AI software tools, helping users discover, compare, and select AI solutions for marketing, development, SEO, and other applications. `Free` `Web`
- **[AITorke](https://aitorke.com/)** — Writing assistant for drafting and editing content, with search-optimization suggestions alongside the editor. `Freemium` `Web`
- **[AIUpHouse](https://aiuphouse.com/)** — AI-driven content generation platform designed to help marketers and businesses create SEO-optimized marketing content, including blog posts, product descriptions, and email campaigns. `Paid` `Free Trial` `Web`
- **[AI Viggle](https://aiviggle.com/)** — AI-driven platform that helps businesses generate marketing content, automate workflows, and optimize SEO to improve content marketing efficiency. `Freemium` `Web`
- **[Aivocado](https://aivocado.online/)** — Writing assistant designed to help users create various types of content such as blog posts, marketing copy, and product descriptions with SEO optimization features. `Freemium` `Web`
- **[AI Web Page Analyzer (AI WPA)](https://www.aiwebpageanalyzer.com/)** — Tool that evaluates website SEO, performance, and technical issues to provide actionable recommendations for optimization. `Freemium` `Web`
- **[aiWritely](https://www.aiwritely.com/)** — Web-based AI writing assistant that generates SEO-friendly content, blog posts, and marketing copy to help users create quality text faster. `Freemium` `Web`
- **[AI Writer](https://ai-writer.com/)** — AI-based content generation tool that creates SEO-optimized articles and blog posts automatically from user-provided topics or keywords. `Paid` `Free Trial` `Web`
- **[Alchemi.ai](https://www.alchemi.ai/)** — Data annotation platform that automates and manages labeling of images, videos, text, and audio to prepare datasets for AI and machine learning models with human-in-the-loop quality control. `Paid` `Web`
- **[All Hashtag](https://all-hashtag.com/)** — Web-based tool that helps users generate relevant hashtags, analyze their popularity, and create custom hashtags to improve social media engagement on platforms like Instagram and Twitter. `Freemium` `Web`
- **[Alli AI](https://www.alliai.com/?lmref=yX_iIA)** — SEO automation platform that helps marketers automate keyword research, content optimization, and SEO campaign management to improve organic search performance efficiently. `Paid` `Free Trial` `Web`
- **[Alphapro](https://www.alphapro.ai/)** — Writing assistant designed to help marketers and content creators generate SEO-optimized content such as blog posts, marketing copy, and social media posts efficiently through an easy-to-use web platform. `Paid` `Free Trial` `Web`
- **[AlsoAsked](https://alsoasked.com/)** — SEO tool that visualizes related search questions from Google's 'People Also Ask' feature to help users uncover keyword opportunities and understand search intent. `Freemium` `Web`
- **[Amazy.uk](https://amazy.uk/)** — UK-based AI content generation platform that helps marketers and businesses create SEO-friendly articles, marketing copy, and product descriptions efficiently through an easy-to-use web interface. `Freemium` `Web`
- **[AmpUp](https://www.ampup.ai/)** — Writing assistant designed to help marketers and content creators generate high-quality, SEO-optimized content quickly and efficiently. `Freemium` `Web`
- **[AMZScout](https://amzscout.net/)** — Amazon product research tool that helps sellers find profitable products, estimate sales, perform keyword research, and analyze competitors to optimize their Amazon business. `Freemium` `Web` `Browser Extension`
- **[AnswerThePublic](https://answerthepublic.com/en)** — Keyword research tool that visualizes search queries and questions from users to help marketers and content creators generate SEO-friendly content ideas. `Freemium` `Web`
- **[Anvenssa.com](https://www.anvenssa.com/)** — Writing assistant designed to generate SEO-optimized content, blog posts, and marketing copy through an easy-to-use web platform. `Freemium` `Web`
- **[Anyword](https://www.anyword.com/)** — Copywriting tool that helps marketers and content creators generate optimized ad copy, blog posts, and marketing content with predictive performance scoring and multi-language support. `Paid` `Free Trial` `Web`
- **[AppTweak](https://www.apptweak.com/en)** — App store optimization platform that helps mobile marketers improve app visibility and downloads through keyword research, competitor analysis, and performance tracking on Apple and Google app stores. `Freemium` `Web`
- **[Article Fiesta](https://articlefiesta.com/?af=bunkmate-inferior)** — Writing assistant that generates SEO-optimized articles and marketing content to help users create high-quality text efficiently. `Paid` `Free Trial` `Web`
- **[Article Idea Generator](https://www.articleideagenerator.com/)** — Free web tool that helps users generate multiple article or blog post ideas based on a keyword input, ideal for content creators and marketers seeking inspiration. `Free` `Web`
- **[ArtiScribe AI](https://artiscribeai.com/)** — AI-driven writing assistant that helps users generate, edit, and optimize English content with features like grammar correction and SEO suggestions. `Paid` `Free Trial` `Web`
- **[Ascn.ai](https://ascn.ai/)** — AI-driven content generation platform that helps marketers and SEO professionals create optimized written content quickly using customizable templates and SEO keyword integration. `Freemium` `Web`

## Productivity and workflow

Meetings, notes, tasks, calendars, and everyday knowledge work.

- **[1440.io](https://www.1440.io/)** — Writing assistant that helps users generate, edit, and improve written content efficiently through advanced AI features. `Freemium` `Web`
- **[Abun](https://abun.com/)** — Writing assistant that helps users generate and improve content efficiently across multiple formats including blogs, emails, and social media posts. `Freemium` `Web`
- **[Ace It](https://aceit.works/)** — Writing assistant that provides real-time grammar and style corrections along with content suggestions to help users create and edit text efficiently. `Freemium` `Web`
- **[Acuity Scheduling](https://acuityscheduling.com/)** — Online appointment booking software that enables businesses to automate scheduling, send reminders, accept payments, and sync calendars to streamline client bookings. `Paid` `Free Trial` `Web` `iOS` `Android`
- **[ADAM](https://interval-ai.com/)** — Meeting assistant that transcribes meetings, generates summaries, and extracts action items to improve team productivity. `Paid` `Free Trial` `Web` `API`
- **[AI Chief Strategy Officer](https://chatthing.ai/)** — AI-driven virtual assistant that helps businesses with strategic planning, market analysis, and decision making through conversational AI and data insights. `Freemium` `Web` `API`
- **[AI Code Mentor](https://code-mentor.ai/)** — Web-based AI coding assistant that provides real-time code review, debugging help, code generation, and programming explanations to developers and learners. `Freemium` `Web`
- **[AI Coder Buddy](https://aicoderbuddy.com/)** — AI-driven tool that assists developers by generating code snippets, debugging code, and providing programming explanations to improve productivity. `Freemium` `Web` `API`
- **[AI Coffee Club](https://aicoffee.club/)** — Web-based platform that combines AI writing assistance with collaborative tools to help teams create, brainstorm, and manage content projects efficiently. `Freemium` `Web`
- **[AICommit - Your Best Commit Generator](https://aicommit.app/)** — Tool that automatically generates clear and consistent git commit messages by analyzing your code changes, available as a VS Code extension and CLI tool. `Freemium` `Web` `CLI` `VS Code`
- **[Ai Gallery](https://aigallery.app/)** — Text-to-image generator with a public gallery, where creations can be shared with other users or downloaded. `Freemium` `Web`
- **[AiGenda](https://aigenda.tech/en)** — Meeting assistant that schedules from your calendar, transcribes the call, and turns it into notes and action items. `Freemium` `Web` `Browser Extension`
- **[AI Listify](https://www.ailistify.com/)** — AI-driven tool that generates structured lists for content marketing, SEO, and idea organization, helping users create engaging and readable lists quickly. `Freemium` `Web`
- **[AIMailman](https://aimailman.com/)** — Email assistant that streamlines email drafting, management, and automation through a Chrome extension and web app, primarily supporting Gmail users. `Freemium` `Web` `Browser Extension`
- **[AIScriptReader](https://aiscriptreader.com/)** — Tool that analyzes and summarizes scripts to help content creators improve clarity and engagement. `Freemium` `Web`
- **[AI Summarizer best](https://summarizer.best/)** — Free web-based tool that automatically creates concise summaries from longer English texts, helping users save time by extracting key information quickly. `Free` `Web`
- **[AI Text Summarizer](https://textsummarizer.net/)** — Free web-based tool that automatically condenses long text into brief summaries, helping users save time and understand content faster. `Free` `Web`
- **[AI Writer: Essay Email Writing(APP)](https://ai-writer.app/)** — Web-based AI writing assistant that helps users generate essays and emails efficiently by providing AI-generated drafts based on user prompts. `Freemium` `Web`
- **[Aleah AI](https://aleahai.com/)** — AI-driven writing assistant that helps users create, edit, and customize written content efficiently using advanced natural language processing. `Paid` `Free Trial` `Web`
- **[Andi](https://andisearch.com/)** — Search assistant that provides fast, conversational answers and summaries by leveraging real-time web data, designed to enhance traditional search engines. `Freemium` `Web` `Browser Extension`
- **[Angry Email Translator](https://angryemailtranslator.com/)** — Free web tool that transforms angry or harsh emails into calm, polite, and professional messages to improve communication. `Free` `Web`
- **[Any Summary](https://anysummary.app/)** — AI-based web tool that condenses long text into brief summaries to help users quickly grasp key information. `Freemium` `Web`
- **[Appdron ChatGPT Dashboard](https://appdron.com/)** — Web-based platform that centralizes management of multiple ChatGPT sessions, offering organized chat history and a user-friendly interface to enhance productivity. `Freemium` `Web`
- **[ArchitectGPT](https://architectgpt.io/)** — Tool that automates architectural design by generating concepts, drafts, and presentations based on user inputs, streamlining the design process for architects and planners. `Freemium` `Web`
- **[Aria](https://ariapp.me/)** — Writing assistant that helps users generate and improve written content efficiently through AI-generated suggestions and templates. `Freemium` `Web` `Browser Extension`
- **[AskCodi](https://www.askcodi.com/)** — Coding assistant that helps developers write, debug, and understand code by converting natural language queries into code snippets and explanations. `Freemium` `Web`
- **[AskingTips](https://askingtips.com/)** — Writing assistant that improves your writing by offering real-time suggestions for grammar, tone, and clarity to help you communicate more effectively. `Freemium` `Web`
- **[Audeus: Text to Speech Reader](https://www.audeus.com/)** — Web-based text to speech reader that converts written text into natural, human-like audio in multiple languages, designed for accessibility and content consumption. `Freemium` `Web`
- **[AudioBriefs](https://audiobriefs.app/)** — App that lets users quickly record, edit, and share short audio summaries or briefs across multiple platforms. `Freemium` `Web` `iOS` `Android`
- **[AutoDraft](https://autodraft.in/)** — Writing assistant that helps users quickly generate and improve written content through drafting, rewriting, and editing features. `Freemium` `Web`
- **[Avanty](https://avanty.app/)** — Writing assistant that helps users generate, edit, and optimize English content efficiently through a web platform and Chrome extension. `Freemium` `Web` `Browser Extension`
- **[Awesome Prompts](https://awesomeprompts.cc/)** — Free web-based library offering a wide range of categorized AI prompts to help users generate creative content and improve productivity with AI chatbots. `Free` `Web`
- **[Ayoa](https://www.ayoa.com/)** — Combines mind mapping, task management, and brainstorming prompts so teams can move from idea to assigned work. `Freemium` `Web` `iOS` `Android`
- **[Azna AI](https://aznaai.com/)** — Writing assistant that helps users generate various types of written content such as articles, marketing copy, and creative writing through an easy-to-use web platform with multiple templates and editing tools. `Freemium` `Web`
- **[Backlsh - Time Tracking](https://backlsh.com/)** — Time tracking software that helps freelancers and teams track work hours, manage projects, and generate reports for billing and productivity. `Freemium` `Web` `Browser Extension`
- **[Backtrack 2.0](https://usebacktrack.com/)** — AI-driven platform that transcribes and analyzes interviews by converting audio into searchable text with speaker identification and keyword tagging. `Paid` `Free Trial` `Web`
- **[BannsAi](https://banns.ai/)** — AI-driven writing assistant that generates high-quality content such as blog posts, marketing copy, and SEO-optimized articles through an easy-to-use web platform. `Freemium` `Web`
- **[Based](https://based.so/)** — Writing assistant that helps users generate creative and professional content efficiently by providing AI-driven text completion and idea generation. `Freemium` `Web`
- **[Beam](https://www.getbeam.ai/)** — Writing assistant that integrates with your browser to provide real-time writing suggestions, grammar corrections, and creative prompts to help you write faster and better. `Freemium` `Web` `Browser Extension`
- **[Benki](https://www.ben-ki.com/)** — Writing assistant that improves your writing by providing real-time grammar corrections, style suggestions, and content generation tools. `Freemium` `Web`
- **[Berrycast Transcripts (Powered by AI)](https://www.berrycast.com/)** — AI-driven tool that automatically transcribes meetings and video messages, enabling teams to capture accurate notes and share recordings with synchronized transcripts for improved communication. `Freemium` `Web` `macOS`

## Marketing and advertising

Campaign work, advertising, social media, and brand content.

- **[30characters](https://30chars.com/)** — Writing assistant that helps users create concise and effective short-form content such as headlines, taglines, and social media posts, optimized for character limits and marketing needs. `Freemium` `Web`
- **[500px](https://500px.com/)** — Photography platform that allows photographers to share, showcase, and license their photos globally, offering portfolio tools and community engagement. `Freemium` `Web` `iOS` `Android`
- **[About.me](https://about.me/)** — Web-based platform that lets individuals create a simple, customizable personal profile page to showcase their biography, social media links, and contact information, serving as a digital business card or portfolio. `Freemium` `Web`
- **[Acrolinx](https://www.acrolinx.com/)** — AI-driven content governance platform that helps enterprises create consistent, clear, and compliant content by analyzing and guiding writing according to brand and linguistic rules. `Paid` `Web` `API`
- **[Action Network](https://actionnetwork.org/)** — Free digital organizing platform designed for progressive activists and nonprofits to manage petitions, fundraising, email and SMS outreach, and events. `Free` `Web`
- **[ad:personam Self Serve DSP](https://www.adpersonam.io/)** — Programmatic advertising platform that enables advertisers to independently create and optimize real-time bidding campaigns across multiple ad exchanges with granular audience targeting and performance analytics. `Paid` `Web`
- **[AdPlugg](https://www.adplugg.com/)** — Cloud-based platform that enables users to create, schedule, and manage advertisements across digital signage and online channels with features like multi-location management and campaign analytics. `Freemium` `Web` `API`
- **[Adstra](https://adstra.ai/)** — AI-driven platform that automates the creation, management, and optimization of digital advertising campaigns across multiple platforms to improve efficiency and ROI. `Freemium` `Web`
- **[AI2image](https://www.ai2image.com/)** — Web-based AI tool that generates unique images from text prompts, ideal for marketers and creators needing quick, custom visuals. `Freemium` `Web`
- **[AI Art Weekly](https://aiartweekly.com/)** — Free weekly newsletter delivering curated news, tools, and creative projects related to AI-generated art. `Free` `Web`
- **[AI Kungfu Video Generator](https://aikungfu.app/)** — Web-based tool that uses AI to convert text scripts into videos quickly and easily, ideal for marketers and content creators. `Paid` `Free Trial` `Web`
- **[AI Landing Page Generator](https://www.ailandingpagegenerator.com/)** — Web tool that uses AI to create customizable, mobile-friendly landing pages quickly without coding skills, ideal for marketers and businesses. `Freemium` `Web`
- **[AimindCrafter](https://aimindcrafter.com/)** — Content generation platform that helps users create creative writing, marketing copy, and blog posts through customizable prompts and templates. `Freemium` `Web`
- **[AI Profile Picture Maker](https://pfpmaker.com/)** — Web-based tool that uses AI to generate custom profile pictures and avatars from user photos, offering multiple styles and background options for social media and professional use. `Freemium` `Web`
- **[Airmeet](https://www.airmeet.com/)** — Web-based virtual event platform that enables hosting interactive online conferences, webinars, and networking sessions with features like virtual stages, breakout rooms, and live engagement tools. `Freemium` `Web`
- **[AI RoastBot](https://www.airoastbot.com/)** — Web tool that generates witty and humorous roasts based on user input, ideal for social media and entertainment. `Freemium` `Web`
- **[AI Social Bio](https://aisocialbio.com/)** — Web-based AI tool that generates personalized social media bios tailored to various platforms, helping users create engaging profiles quickly. `Freemium` `Web`
- **[AI VYX](https://aivyx.com/)** — AI-driven video creation platform that automates script generation and video assembly to help marketers and content creators produce professional videos quickly and easily. `Paid` `Free Trial` `Web`
- **[Amuse](https://www.amuse.io/en/)** — Music distribution platform that enables independent artists and record labels to distribute their music to major streaming services worldwide, offering free and subscription plans with royalty management and analytics. `Freemium` `Web` `iOS` `Android`
- **[Animate AI](https://animateai.pro/)** — AI-driven animation platform that enables users to create professional animated videos using customizable templates and an easy drag-and-drop editor. `Freemium` `Web`
- **[Animood](https://animood.lirena.in/)** — Video creation tool that transforms text into animated videos using customizable templates, ideal for marketers and educators. `Freemium` `Web`
- **[Anythingyou.AI](https://anythingyou.ai/)** — AI-driven platform that helps users generate creative and marketing content efficiently through customizable templates and advanced text generation models. `Paid` `Free Trial` `Web`
- **[Aperty | Professional Portrait Editor](https://aperty.ai/)** — Online portrait editor that automatically retouches photos by smoothing skin, removing blemishes, and adjusting lighting to produce professional-quality portraits quickly and easily. `Freemium` `Web`
- **[ArtBinder](https://artbinder.com/)** — Art management software that helps galleries and artists organize inventory, manage client relationships, and present artwork digitally via web and mobile apps. `Paid` `Web` `iOS` `Android`
- **[Artlogic](https://artlogic.net/)** — Cloud-based platform that helps artists, galleries, and dealers manage art inventory, sales, and create professional websites with e-commerce capabilities. `Paid` `Web`
- **[Artwork Archive](https://www.artworkarchive.com/)** — Art inventory and management software designed for artists, collectors, and galleries to organize artwork, track sales, and manage exhibitions efficiently. `Paid` `Free Trial` `Web` `iOS` `Android`
- **[Audiomack](https://audiomack.com/)** — Free music streaming platform that allows artists to upload music and fans to stream and download songs with options for offline listening via premium subscription. `Freemium` `Web` `iOS` `Android`
- **[AutoMemes.ai](https://www.automemes.ai/)** — AI-driven platform that automates meme creation by generating captions and images based on user input, ideal for social media marketing and content creation. `Freemium` `Web`
- **[Avatoon](https://avatoon.me/)** — Avatar generator that creates personalized cartoon avatars from photos or manual customization, available on web and mobile platforms. `Freemium` `Web` `iOS` `Android`
- **[AZLyrics](https://b.azlyrics.com/?u=/)** — Free online platform providing a large searchable database of song lyrics organized by artist and album. `Free` `Web`
- **[Bandzoogle](https://bandzoogle.com/)** — Website builder designed specifically for musicians to create professional sites with integrated ecommerce for selling music, merchandise, and tickets, plus marketing tools to engage fans. `Paid` `Free Trial` `Web`
- **[Battlefy](https://battlefy.com/)** — Esports tournament platform that enables organizers to create and manage competitive gaming events with automated brackets, player registration, and real-time score updates. `Freemium` `Web`
- **[Beacon](https://beacon.com/)** — Content generation platform that helps marketers create professional lead magnets and marketing materials quickly using customizable templates and AI assistance. `Freemium` `Web`
- **[Beckett Grading Services](https://beckett.com/)** — Professional company that authenticates and grades sports trading cards to determine their condition and value, providing encapsulation and online verification for collectors. `Paid` `Web`
- **[Beehiiv](https://www.beehiiv.com/)** — Newsletter platform that helps creators build, grow, and monetize their email audiences with features like referral programs, paid subscriptions, and analytics. `Freemium` `Web`
- **[Be.Live](https://be.live/)** — Web-based platform that enables users to create interactive live streams with multiple guests, screen sharing, and direct social media integration for Facebook and YouTube. `Freemium` `Web`
- **[Bertha AI](https://bertha.ai/)** — Content generation tool that integrates with WordPress to help users create SEO-optimized blog posts, marketing copy, and product descriptions efficiently. `Freemium` `Web`

## Coding and development

Tools used while writing, reviewing, testing, or shipping software.

- **[42Crunch API Security](https://42crunch.com/)** — API security platform that automates vulnerability detection, OpenAPI validation, and continuous monitoring to protect APIs throughout their lifecycle. `Paid` `Free Trial` `Web` `API`
- **[60sec.site](https://60sec.site/)** — Web tool that enables users to create and publish minimalist websites or landing pages in about 60 seconds without any coding skills. `Freemium` `Web`
- **[Abstract](https://www.abstract.com/)** — Design collaboration platform that provides version control and workflow management tailored for design teams, integrating with tools like Sketch and Adobe XD. `Freemium` `Web`
- **[AccuWeather API](https://developer.accuweather.com/home)** — AccuWeather API provides developers with accurate, real-time and forecast weather data globally via RESTful endpoints, supporting JSON and XML formats for easy integration. `Freemium` `Web` `API`
- **[Acronis Cyber Backup](https://www.acronis.com/en/)** — Data protection platform offering automated backups, AI-based ransomware protection, and disaster recovery for physical, virtual, and cloud environments. `Paid` `Free Trial` `Web` `Windows` `macOS` `Linux`
- **[Adalo](https://www.adalo.com/)** — No-code platform that lets you create mobile and web applications visually without programming, supporting native app publishing and database integration. `Freemium` `Web`
- **[AGM: AI Game Maker](https://madegamewithai.com/)** — Web-based no-code platform that uses artificial intelligence to help users create 2D video games by generating assets, levels, and narratives without programming skills. `Freemium` `Web`
- **[AICodeConvert](https://aicodeconvert.com/)** — AI-driven web tool that converts source code from one programming language to another, supporting multiple languages and providing real-time, accurate translations to assist developers and programmers. `Freemium` `Web`
- **[AI Code Translator](https://ai-code-translator.com/)** — Web-based tool that uses artificial intelligence to automatically translate source code between multiple programming languages, helping developers save time and reduce errors. `Freemium` `Web`
- **[AI CSS Animations](https://www.aicssanimations.com/)** — Free online tool that helps web designers and developers generate customizable CSS animation code quickly without manual coding. `Free` `Web`
- **[AI Love Code](https://ailovecode.com/)** — AI-driven platform that assists developers by generating code snippets, reviewing existing code, and providing debugging suggestions to enhance productivity. `Freemium` `Web`
- **[AI Music API, Free Cheap AI Music](https://udioapi.pro/)** — AI Music API by UdioAPI provides developers with a free and affordable way to generate royalty-free AI-composed music tracks via an easy-to-use API supporting multiple genres and moods. `Freemium` `Web` `API`
- **[AI QR Codes](https://aiqrcodes.app/)** — Web platform that uses artificial intelligence to generate customizable and visually appealing QR codes suitable for marketing and branding. `Freemium` `Web`
- **[AIQRHub](https://aiqrhub.com/)** — Platform that creates dynamic and customizable QR codes for marketing, business, and event use, offering real-time analytics and multiple QR code types. `Freemium` `Web`
- **[AI Superior GPT](https://aisuperior.com/)** — Web-based AI chatbot powered by GPT technology that helps users generate content, code, and customer support responses with multi-turn conversational capabilities. `Freemium` `Web`
- **[Akismet](https://akismet.com/)** — WordPress plugin developed by Automattic that automatically detects and blocks spam comments and form submissions using machine learning and a global spam database. `Freemium` `Web` `API`
- **[Alchemy](https://www.alchemy.com/)** — Blockchain developer platform providing APIs and scalable node infrastructure to build, monitor, and scale decentralized applications on Ethereum and other blockchains. `Freemium` `Web` `API`
- **[Algolia](https://www.algolia.com/)** — Hosted search API platform that provides instant, relevant, and typo-tolerant search experiences for websites and applications through easy-to-use APIs and SDKs. `Freemium` `Web` `API`
- **[Anima](https://www.animaapp.com/)** — Tool that converts UI/UX designs from Figma, Sketch, or Adobe XD into clean React, HTML, or Vue code, enabling interactive prototypes and faster developer handoff. `Freemium` `Web` `API`
- **[Animate.css](https://animate.style/)** — Free CSS library that provides ready-made animation classes to easily add animations to web elements without JavaScript. `Free` `Web`
- **[Animista](https://animista.net/)** — Free online CSS animation library that lets users customize and export animations for web projects without coding from scratch. `Free` `Web`
- **[Ant Design](https://ant.design/)** — Open-source React UI framework providing a comprehensive set of reusable components and design guidelines to build enterprise-level web applications with consistent and customizable user interfaces. `Free` `Open Source` `Web`
- **[Anvil](https://anvil.works/)** — Low-code platform that enables users to build full-stack web applications using Python with a drag-and-drop interface, eliminating the need for JavaScript or HTML knowledge. `Freemium` `Web`
- **[API Layer](https://apilayer.com/)** — Platform that provides developers and businesses with easy access to a wide range of APIs for data validation, real-time information, and automation through a unified interface. `Freemium` `Web` `API`
- **[Apollo Auto](https://www.apollo.auto/)** — Open-source autonomous driving software platform providing a full software stack for self-driving vehicles, including perception, planning, control, and simulation tools. `Free` `Open Source` `Web` `Linux` `API`
- **[Appcues](https://www.appcues.com/)** — No-code user onboarding platform that helps businesses create personalized in-app experiences to improve product adoption and user engagement without coding. `Paid` `Free Trial` `Web` `API`
- **[Appkina.com](https://appkina.com/)** — No-code platform that lets you create custom mobile and web apps using a drag-and-drop interface without any programming skills. `Freemium` `Web`
- **[Apployal: AI-Powered app localization](https://apployal.io/)** — Platform that automates and manages mobile app localization, enabling developers to efficiently translate and maintain multilingual apps with collaboration and API support. `Paid` `Free Trial` `Web` `API`
- **[Appsmith](https://www.appsmith.com/)** — Open-source low-code platform that enables developers and businesses to build custom internal applications quickly using drag-and-drop UI components and integrations with databases and APIs. `Freemium` `Web`
- **[AppSumo](https://appsumo.com/)** — Online marketplace offering curated lifetime and discounted deals on SaaS software, helping entrepreneurs and small businesses save money on essential digital tools. `Free` `Web`
- **[Appwrite](https://appwrite.io/)** — Open-source backend-as-a-service platform that provides developers with APIs and SDKs to manage authentication, databases, storage, and serverless functions, enabling faster app development without managing backend infrastructure. `Free` `Web` `API`
- **[Aqua Security](https://www.aquasec.com/)** — Cloud native security platform that protects containerized applications and Kubernetes environments by providing vulnerability scanning, runtime threat detection, and compliance management integrated into DevOps workflows. `Paid` `Free Trial` `Web` `API`
- **[Arcade](https://www.arcade.dev/)** — No-code platform that allows users to visually build, deploy, and host web applications without writing code, featuring drag-and-drop design, API integrations, and cloud hosting. `Freemium` `Web`
- **[ArchitectAI](https://architectai.app/)** — Web-based AI tool that helps software architects design, visualize, and document software system architectures with automated diagram generation and collaboration features. `Paid` `Free Trial` `Web`
- **[A.V. Mapping](https://avmapping.co/)** — Software platform that enables users to create and manage complex audio-visual projection mapping projects with real-time synchronization and interactive features. `Freemium` `Web`

## Data and analytics

Analysis, dashboards, extraction, and business intelligence.

- **[Accenture](https://www.accenture.com/de-de)** — Global professional services company offering consulting, technology, and digital transformation services to help businesses innovate and improve operations. `Paid` `Web` `API`
- **[Actility ThingPark](https://www.actility.com/)** — Enterprise-grade IoT platform that enables large-scale deployment and management of LoRaWAN networks for industrial and smart city applications. `Paid` `Web` `API`
- **[AdIntell](https://adintelli.ai/)** — AI-driven advertising intelligence platform that helps marketers monitor competitor ads, analyze creatives, and gain actionable insights to improve their own campaigns. `Freemium` `Web`
- **[Adjust](https://www.adjust.com/)** — Mobile measurement platform that provides marketers with attribution analytics, fraud prevention, audience segmentation, and cost aggregation to optimize app marketing campaigns. `Paid` `Web` `API`
- **[Adminer](https://adminer.pro/)** — Lightweight, single PHP file database management tool supporting multiple SQL databases, designed for easy deployment and efficient database administration. `Free` `Web`
- **[AdMob](https://admob.google.com/home/)** — Mobile advertising platform for monetising Android and iOS apps, with several ad formats, mediation across multiple ad networks, and performance reporting. `Free` `Web` `iOS` `Android`
- **[AdRoll](https://www.adroll.com/)** — Digital marketing platform specializing in AI-driven retargeting and cross-channel advertising to help e-commerce and other businesses increase conversions and revenue. `Freemium` `Web` `API`
- **[AdScan.ai](https://adscan.ai/)** — Platform that provides marketers with competitive ad intelligence by aggregating and analyzing digital ads across platforms to optimize campaigns. `Freemium` `Web`
- **[AdSpy](https://www.adspy.com/)** — Ad intelligence platform that helps marketers analyze competitor ads, monitor campaigns in real-time, and gain insights to optimize their own advertising strategies. `Paid` `Web`
- **[Adswizz](https://www.adswizz.com/)** — Programmatic digital audio advertising platform that enables advertisers and publishers to buy, sell, and manage audio ads across streaming music, podcasts, and internet radio with dynamic ad insertion and audience targeting. `Paid` `Web` `API`
- **[Advacheck](https://advacheck.com/)** — AI-driven platform that analyzes Facebook and Instagram ads to help marketers optimize campaigns through competitor insights and creative analysis. `Freemium` `Web`
- **[Affectiva](https://www.affectiva.com/)** — Emotion AI platform that analyzes facial expressions and emotions using artificial intelligence to provide insights for marketing, automotive safety, and media engagement. `Paid` `Web` `API`
- **[AgriWebb](https://www.agriwebb.com/)** — Farm management software that helps farmers track livestock, plan operations, analyze data, and collaborate with teams through mobile and web apps. `Paid` `Web` `iOS` `Android`
- **[Ai2sql](https://ai2sql.io/)** — Web tool that uses AI to convert natural language questions into SQL queries, simplifying database querying for users without SQL expertise. `Freemium` `Web`
- **[AI graph maker](https://aigraphmaker.net/)** — Free web-based tool that uses AI to help users quickly create and customize various types of graphs and charts from their data without needing advanced skills. `Free` `Web`
- **[AI Query 2.0](https://aiquery.co/)** — AI-driven platform that enables users to query and analyze data using natural language, eliminating the need for SQL and simplifying data exploration. `Freemium` `Web`
- **[Airbyte](https://airbyte.com/)** — Open-source data integration platform that enables building and managing ETL and ELT pipelines with a large catalog of connectors and customizable options. `Freemium` `Web` `API`
- **[Aispect](https://aispect.io/)** — AI-based video analytics platform that provides real-time object detection and anomaly detection to enhance security and operational efficiency across industries. `Paid` `Web` `API`
- **[Alation](https://www.alation.com/)** — Enterprise data catalog platform that centralizes metadata, enabling data discovery, governance, and collaboration to improve analytics and compliance. `Paid` `Web` `API`
- **[Amplitude](https://amplitude.com/)** — Product analytics platform that helps businesses track and analyze user behavior to improve product engagement and growth. `Freemium` `Web` `API`
- **[Analyzr](https://analyzr.ai/)** — AI-driven data analytics platform that helps businesses automate data processing, generate real-time reports, and leverage predictive analytics for better decision-making. `Freemium` `Web`
- **[Anania AI](https://anania.ai/)** — Web-based platform that allows users to query databases and spreadsheets using natural language, providing instant answers and visualizations without requiring SQL knowledge. `Freemium` `Web`
- **[anchain.ai](https://www.anchain.ai/)** — Blockchain analytics platform that helps enterprises detect fraud, ensure AML compliance, and manage crypto risks through real-time monitoring and advanced analytics. `Paid` `Web` `API`
- **[AntV](https://antv.vision/)** — Open-source JavaScript data visualization library developed by Alibaba that enables developers to create interactive, customizable charts and graphs for web applications. `Free` `Open Source` `Web` `API`
- **[AnyClip, The Genius Platform](https://anyclip.com/)** — AnyClip Genius Platform is an AI-driven video content intelligence solution that analyzes, tags, and manages video assets to improve search, personalization, and monetization for media companies and brands. `Paid` `Web` `API`
- **[AnyLogic](https://www.anylogic.com/)** — Professional simulation software platform that supports multiple modeling methods including system dynamics, agent-based, and discrete event simulation, used for analyzing and optimizing complex systems across industries. `Paid` `Free Trial` `macOS` `Linux`
- **[Apache NiFi](https://nifi.apache.org/)** — Open-source data integration tool that automates and manages real-time dataflows using a visual interface, supporting data routing, transformation, and provenance tracking. `Free` `Web`
- **[AppLovin](https://applovin.com/en)** — Mobile marketing platform that helps app developers acquire users, monetize apps, and optimize ad campaigns through advanced targeting, ad mediation, and analytics tools. `Paid` `Web` `API`
- **[Apptrop](https://apptrop.com/)** — Web-based app store optimization tool that enables mobile app developers and marketers to track keywords, analyze competitors, and optimize app metadata to improve app store rankings and downloads. `Freemium` `Web`
- **[Aquatic Informatics](https://aquaticinformatics.com/)** — Software platform designed to manage, analyze, and report water and environmental data, helping organizations ensure data quality and regulatory compliance. `Paid` `Web`
- **[ArcGIS](https://www.esri.com/en-us/home)** — Cloud-based GIS platform by Esri that enables users to create, analyze, and share interactive maps and spatial data for location intelligence and decision-making. `Freemium` `Web`
- **[AskCSV](https://askcsv.com/)** — AI-driven web tool that allows users to upload CSV files and ask natural language questions to analyze and visualize data without coding. `Freemium` `Web`
- **[Ask On Data](https://askondata.com/)** — Platform that enables users to ask questions about their data in natural language and receive instant visual insights without needing technical skills. `Paid` `Free Trial` `Web`
- **[Ataccama](https://www.ataccama.com/)** — AI-driven data management platform that integrates data governance, master data management, and data quality automation to help enterprises manage and improve their data assets efficiently. `Paid` `Web`
- **[Athina AI](https://www.athina.ai/)** — Web-based platform that uses artificial intelligence to analyze business data, generate predictive insights, and provide customizable dashboards for better decision-making. `Freemium` `Web`

## Audio, music, and voice

Speech synthesis, transcription, music generation, and audio editing.

- **[Acapella Extractor](https://www.acapella-extractor.com/en/)** — AI-based web tool that isolates vocals and instrumentals from audio tracks, enabling users to create acapellas, instrumentals, and karaoke versions quickly and easily. `Freemium` `Web`
- **[Accha FM](https://acchafm.com/)** — Online platform that enables users to broadcast live radio shows and host podcasts with multilingual support and community features. `Freemium` `Web`
- **[AccurateScribe.ai](https://accuratescribe.ai/)** — Transcription tool that converts audio and video files into accurate text transcripts quickly, featuring speaker identification and easy editing. `Freemium` `Web`
- **[Acon Digital DeNoise](https://acondigital.com/)** — Professional audio noise reduction tool that removes unwanted background noise from recordings using adaptive algorithms, available as standalone software and plugins for Windows and macOS. `Paid` `Free Trial` `Windows` `macOS`
- **[Adobe Podcast](https://podcast.adobe.com/)** — Free web-based AI audio editing tool by Adobe that enhances podcast audio quality with noise reduction, voice enhancement, and automatic transcription. `Free` `Web`
- **[Afroverse](https://afroversemusicgroup.dorik.io/)** — Web-based music platform focused on promoting African music artists, providing artist management, music distribution, and fan engagement services. `Free` `Web`
- **[AI audio transcription](https://transcribethis.io/)** — TranscribeThis is an AI-based audio transcription tool that converts audio files into accurate text transcripts quickly and securely. `Paid` `Free Trial` `Web`
- **[AI based live captioning system](https://live-captions.com/)** — The AI Based Live Captioning System provides real-time, accurate speech-to-text captions via a web platform, enhancing accessibility for live events and meetings. `Freemium` `Web`
- **[AI Clone Voice Free](https://aiclonevoicefree.com/)** — Free web-based platform that lets you clone voices using AI and generate natural-sounding speech from text. `Free` `Web`
- **[AI Drum Generator](https://aidrumgenerator.com/)** — Free web-based tool that uses artificial intelligence to create custom drum patterns quickly and easily without requiring advanced skills. `Free` `Web`
- **[AI Hits](https://aihits.co/)** — AI-driven music generation platform that creates royalty-free, customizable music tracks for content creators, marketers, and developers via a simple web interface. `Freemium` `Web`
- **[AI Lyrics Generator](https://lyricsgenerator.com/)** — Web-based tool that uses artificial intelligence to create original song lyrics based on user inputs like themes and moods, helping songwriters generate creative content efficiently. `Freemium` `Web`
- **[aimages AI](https://aimages.ai/)** — Web-based tool that creates images from text prompts using artificial intelligence, ideal for creative and design projects. `Freemium` `Web`
- **[AIMakeSong](https://www.aimakesong.com/)** — AI-driven online tool that generates custom songs by composing melodies based on user-inputted lyrics and selected music styles. `Freemium` `Web`
- **[AI Mastering](https://aimastering.com/)** — Online service that uses artificial intelligence to automatically master audio tracks, providing musicians and podcasters with professional-quality sound quickly and affordably. `Paid` `Web`
- **[AI Music (Free)](https://aimusiclab.co/)** — Free web-based tool that generates original music tracks using artificial intelligence, allowing users to customize styles and moods and download royalty-free songs without any cost or account registration. `Free` `Web`
- **[aimusicgen](https://aimusicgen.ai/)** — Web-based AI platform that generates original, royalty-free music tracks in various genres and moods, ideal for content creators and professionals needing quick custom audio. `Freemium` `Web`
- **[Ai Musician - AI Music Generator](https://aimusician.ai/)** — Web platform that generates original, royalty-free music tracks customized by genre, mood, and length for creators without musical expertise. `Freemium` `Web`
- **[aimusic.one](https://aimusic.one/)** — AI-driven online platform that generates original, royalty-free music tracks customized by style, mood, and tempo, suitable for content creators and hobbyists. `Freemium` `Web`
- **[AIRadio.Host](https://airadio.host/)** — AI-driven online radio automation platform that enables broadcasters to create, schedule, and manage internet radio stations with ease, supporting both automated playlists and live streaming. `Paid` `Free Trial` `Web`
- **[AI Singing](https://aisinging.ai/)** — Web-based platform that uses AI to generate realistic singing voices from user-provided melodies and lyrics, supporting multiple languages and vocal styles for music production and content creation. `Paid` `Free Trial` `Web`
- **[AISong.ai](https://aisong.ai/)** — AI-driven online platform that generates original songs and melodies based on user inputs like mood and theme, enabling easy music creation without musical expertise. `Freemium` `Web`
- **[AI Song Generator](https://aisonggenerator.net/)** — Free web tool that creates original songs by generating melodies and lyrics based on user input, requiring no musical experience. `Free` `Web`
- **[AI Song Generator-Make Song](https://www.makesong.com/)** — Online tool that uses artificial intelligence to create original songs by generating melodies and lyrics based on user inputs such as themes or moods. `Freemium` `Web`
- **[AI Song ING](https://aisong.ing/)** — Web-based AI tool that assists musicians and songwriters by generating original lyrics, melodies, and music arrangements based on user inputs, helping to accelerate the creative process. `Freemium` `Web`
- **[AITalk](https://aitalk.im/)** — Text-to-speech tool from Japan that converts text into natural, expressive speech with multiple voice options and API support. `Paid` `Free Trial` `Web` `API`
- **[AIVocal](https://aivocal.io/)** — Voice synthesis platform that converts text into natural, human-like speech with multi-language support and custom voice cloning options. `Freemium` `Web` `API`
- **[AI Voice Generator Bot](https://texttospeech.orbitpages.online/)** — Free web-based tool that converts text into natural-sounding speech using AI technology, allowing instant playback and audio download without registration. `Free` `Web`
- **[AiVOOV - Text to Speech Solution](https://aivoov.com/)** — AI-driven text to speech platform that converts written text into natural, human-like audio in multiple languages, suitable for voiceovers, audiobooks, and accessibility. `Freemium` `Web`
- **[AI Wedding Toast](https://aiweddingtoast.com/)** — Web-based tool that generates personalized wedding speeches by using AI to tailor content based on your input about the couple and your relationship. `Freemium` `Web`
- **[Algoriddim djay](https://www.algoriddim.com/)** — Cross-platform DJ software that enables live music mixing with automatic beat detection, streaming service integration, and a variety of audio effects suitable for beginners and professionals. `Freemium` `Windows` `macOS` `iOS` `Android`
- **[All Voice Lab](https://allvoicelab.com/)** — Text-to-speech platform that creates realistic, customizable voiceovers in multiple languages, suitable for content creation, marketing, and accessibility. `Paid` `Free Trial` `Web`
- **[Altered](https://www.altered.ai/)** — AI-driven voice changer software that enables real-time voice modulation, voice cloning, and customizable AI voices primarily for English speakers, suitable for content creators, streamers, and voice actors. `Freemium` `Web` `macOS`
- **[> godcast](https://usegodcast.com/)** — Platform that converts text scripts into natural-sounding podcast episodes, enabling fast and easy audio content creation without recording equipment. `Paid` `Free Trial` `Web`

## Sales and CRM

Prospecting, outreach, pipeline management, and revenue operations.

- **[17hats](https://17hats.com/)** — Cloud-based business management software designed for freelancers and small businesses to manage clients, projects, invoicing, and automate workflows. `Paid` `Free Trial` `Web` `iOS` `Android`
- **[5-Out](https://www.5out.io/)** — AI-driven sales assistant that automates cold email outreach, follow-ups, and lead qualification to help sales teams increase efficiency and conversion rates. `Paid` `Free Trial` `Web`
- **[accent-technologies.com](https://accent-technologies.com/)** — Accent Technologies provides AI-driven business automation and analytics solutions tailored to enterprise needs, enabling process automation, data insights, and predictive modeling. `Paid` `Web`
- **[Actionize AI](https://actionize.ai/)** — Sales automation platform that automates personalized outreach, lead qualification, and customer engagement to help sales teams increase efficiency and close deals faster. `Paid` `Web` `API`
- **[Activazon](https://activazon.com/)** — Amazon product research tool that helps sellers discover profitable products, analyze competitors, and track sales trends to optimize their Amazon business. `Paid` `Free Trial` `Web`
- **[ActiveCampaign AI](https://www.activecampaign.com/)** — Marketing automation platform combining email campaigns, CRM, and sales workflows, with segmentation and send timing handled automatically. `Paid` `Free Trial` `Web` `API`
- **[Advomate](https://advomate.cz/)** — Czech cloud-based CRM and practice management software tailored for law firms, offering client management, task tracking, document storage, and billing features. `Paid` `Web`
- **[Agendor CRM](https://www.agendor.com.br/)** — Cloud-based platform that helps sales teams manage their sales pipeline, customer relationships, and team collaboration with customizable features and mobile access. `Freemium` `Web`
- **[Agent Crop](https://agentcrop.com/)** — AI-driven marketing platform designed for real estate professionals to generate and nurture leads through automated social media ads and follow-up sequences integrated with CRM systems. `Paid` `Free Trial` `Web`
- **[agentmaxx](https://www.agentmaxx.ai/)** — AI-driven assistant designed for real estate professionals to automate lead generation, CRM automation, and client engagement through AI chatbots and scheduling tools. `Freemium` `Web`
- **[AIndLeads - AI finds Leads](https://aindleads.com/)** — Lead generation tool that automates finding and verifying business contacts to improve sales prospecting. `Paid` `Free Trial` `Web`
- **[AI powered SPM Platform](https://www.forma.ai/)** — Forma.ai handles sales performance management for enterprises: incentive compensation calculation, sales analytics, and plan modeling. `Paid` `Web` `API`
- **[AI Soft Mart](https://www.aisoftmart.com/)** — Online marketplace where users can discover, compare, and purchase AI software solutions tailored for various industries and use cases. `Freemium` `Web`
- **[AI Store Manager](https://aistoremanager.com/)** — AI-driven platform that helps e-commerce businesses optimize inventory, forecast sales, automate orders, and adjust pricing dynamically to improve profitability. `Freemium` `Web`
- **[AlayaCare](https://alayacare.com/)** — Cloud-based home healthcare software platform that helps agencies manage care plans, scheduling, telehealth, and electronic visit verification to improve patient outcomes and operational efficiency. `Paid` `Web` `iOS` `Android`
- **[Albacross](https://www.albacross.com/)** — B2B lead generation platform that identifies anonymous website visitors, provides detailed company insights, and integrates with CRM systems to help businesses convert visitors into qualified leads. `Freemium` `Web` `API`
- **[ALIagents.ai](https://aliagents.ai/)** — Platform that helps real estate professionals generate, qualify, and manage property leads using chatbots and an integrated CRM system. `Paid` `Free Trial` `Web` `API`
- **[AMCS Waste Management Software](https://www.amcsgroup.com/)** — Platform for waste and recycling companies offering fleet management, route optimization, customer service, and compliance reporting to streamline operations. `Paid` `Web`
- **[Amplemarket AI](https://www.amplemarket.com/)** — Sales automation platform that leverages artificial intelligence to automate lead generation, personalize email outreach, and integrate with CRM systems to enhance sales productivity. `Freemium` `Web` `API`
- **[Apollo.io](https://www.apollo.io/)** — Sales engagement platform that combines a large contact database, email automation, and CRM tools to help businesses find leads, automate outreach, and manage customer relationships efficiently. `Freemium` `Web` `API`
- **[Aravo](https://aravo.com/)** — Cloud-based platform that automates third-party risk and compliance management, helping enterprises assess and mitigate supplier and vendor risks efficiently. `Paid` `Web` `API`
- **[Arnold](https://www.networkwitharnold.com/)** — Networking assistant that generates personalized outreach messages to help professionals build and maintain business relationships effectively. `Paid` `Free Trial` `Web`
- **[Athena Global](https://athena.global/)** — Web-based platform providing international trade data, market intelligence, compliance tracking, and risk analysis to help businesses make informed global trade decisions. `Paid` `Web`
- **[Atomic Inputs](https://atomicinputs.com/)** — Writing assistant that helps users generate, edit, and improve written content efficiently through AI-driven suggestions and customizable tones. `Freemium` `Web`
- **[Attentionkart](https://attentionkart.com/)** — Marketing automation platform that streamlines lead generation, sales automation, and email marketing with CRM integration and analytics. `Freemium` `Web`
- **[AutoAgentX](https://www.autoagentx.com/)** — AI-driven assistant designed for real estate professionals to automate lead engagement, tenant communication, and property management tasks, improving efficiency and conversion rates. `Paid` `Free Trial` `Web`
- **[AutoBiz](https://autobiz.ai/)** — AI-driven business automation tool that helps companies automate workflows, integrate multiple apps, and improve productivity through intelligent task management and analytics. `Paid` `Free Trial` `Web` `API`
- **[Auto Mailer](https://automailer.ai/)** — AI-driven email automation tool designed to help marketing and sales teams automate personalized email campaigns, follow-ups, and analytics to improve engagement and conversions. `Paid` `Free Trial` `Web` `API`
- **[Automaticall](https://automaticall.io/)** — Meeting assistant that automatically transcribes and summarizes video conference calls to save time and improve team productivity. `Freemium` `Web` `Browser Extension`
- **[Automi AI](https://automi.ai/)** — AI-driven marketing automation platform that helps businesses automate lead generation, email outreach, and sales workflows with CRM integration. `Paid` `Free Trial` `Web`

## Presentations and documents

Slides, documents, PDFs, contracts, and structured paperwork.

- **[1MillionResume](https://1millionresume.com/)** — Online tool that helps users create professional resumes and cover letters through customizable templates and an easy-to-use interface. `Freemium` `Web`
- **[1Page](https://get1page.com/)** — Online resume builder that helps users create professional, ATS-optimized resumes quickly using customizable templates and AI content suggestions. `Freemium` `Web`
- **[ABBYY FineReader](https://www.abbyy.com/)** — Desktop OCR and PDF editing software that converts scanned documents and images into editable and searchable formats, supporting over 190 languages and offering features like document comparison and batch processing. `Paid` `Windows` `macOS`
- **[Able2Extract](https://www.investintech.com/)** — PDF converter and editor software that enables accurate conversion of PDFs to editable formats, direct PDF editing, batch processing, and secure form filling, available on Windows, Mac, and Linux. `Paid` `Free Trial` `Windows` `macOS` `Linux`
- **[AiBucket](https://aibucket.io/)** — Generates marketing copy, creative writing, and search-oriented content from customizable templates. `Freemium` `Web`
- **[AI Career Dreamer](https://careerdreamer.help/)** — AI-driven career coaching platform that provides personalized advice, resume and cover letter assistance, interview preparation, and job search guidance to help users achieve their career goals. `Freemium` `Web`
- **[AI ChatDocs](https://aichatdocs.com/)** — Chatbot platform that enables users to upload documents and interact with them conversationally to get instant, context-aware answers. `Freemium` `Web`
- **[AI Cover Letter Creator](https://aicoverlettercreator.com/)** — Online tool that uses artificial intelligence to generate customized cover letters based on your job details and skills, helping you apply faster and more effectively. `Freemium` `Web`
- **[AI Parabellum](https://aiparabellum.com/)** — AI-driven content generation tool designed to help users create various types of written content quickly and efficiently using advanced natural language processing. `Freemium` `Web`
- **[aiPDF](https://aipdf.ai/)** — AI-driven platform that allows users to upload PDF files and interact with their content through a chatbot interface, enabling quick answers and summaries from documents. `Freemium` `Web`
- **[AI PDF redaction tool App](https://ai-redact.com/)** — Web-based solution that uses AI to identify and permanently remove sensitive data from PDF documents, ensuring privacy and compliance. `Paid` `Free Trial` `Web`
- **[AIPDFs](https://aipdfs.com/)** — Web-based AI tool that reads, summarizes, and allows interactive querying of PDF documents to help users quickly extract key information. `Freemium` `Web`
- **[AI PDF Summarizer by PDF Guru](https://pdfguru.com/)** — Web-based tool that uses artificial intelligence to create concise summaries of PDF documents, helping users quickly understand key points without reading the entire file. `Freemium` `Web`
- **[AiPPT](https://www.aippt.com/)** — AI-driven web tool that helps users create professional presentations quickly by generating slide content and designs automatically. `Freemium` `Web`
- **[AI PPT Maker](https://aipptmaker.ai/)** — Online tool that uses artificial intelligence to automatically generate and design PowerPoint presentations based on your input, helping you create professional slides quickly and easily. `Freemium` `Web`
- **[AI Resume Checker](https://www.resumechecker.ai/)** — Online tool that uses artificial intelligence to analyze resumes for formatting, keyword optimization, and ATS compatibility to help job seekers improve their chances of getting hired. `Freemium` `Web`
- **[AI Slide Studio](https://www.aislidestudio.com/)** — Web-based tool that uses artificial intelligence to automatically generate and design presentation slides from text input, helping users create professional slide decks quickly and easily. `Freemium` `Web`
- **[AI TranslateDocs](https://aitranslatedocs.com/)** — Web-based AI tool that translates documents across multiple languages while preserving formatting and ensuring data privacy. `Paid` `Free Trial` `Web`
- **[Alphy](https://alphy.app/)** — Chatbot that allows users to upload documents and ask questions to get instant, accurate answers extracted directly from the content. `Freemium` `Web`
- **[Amplifiles](https://www.amplifiles.ai/)** — Document management platform that enables teams to collaborate in real-time, securely share files, and automate workflows with intelligent search and version control. `Freemium` `Web` `API`
- **[applai.me](https://applai.me/)** — AI-driven platform that helps users generate innovative app ideas and validate them with market insights, supporting entrepreneurs and developers in early-stage concept development. `Freemium` `Web`
- **[AskYourPdf](https://askyourpdf.com/)** — AI-driven web tool that allows users to upload PDF documents and ask natural language questions to extract information quickly and accurately from the document content. `Freemium` `Web`
- **[AutoPPT](https://autoppt.com/)** — Tool that automates the creation of professional presentations by generating slides from text inputs, allowing users to customize and export decks quickly. `Freemium` `Web`
- **[Bamble AI CV Creator](https://bamble.io/)** — Online platform that uses artificial intelligence to help users build professional resumes quickly by providing tailored templates and content optimization. `Freemium` `Web`
- **[Bard PDF](https://aibardpdf.com/)** — AI-driven web tool that summarizes PDFs and allows interactive Q&A to help users efficiently extract information from documents. `Freemium` `Web`
- **[Beautiful.ai](https://www.beautiful.ai/)** — Presentation software that automates slide design using smart templates and data visualization tools, enabling users to create professional presentations quickly without design skills. `Freemium` `Web`
- **[Bewerbung2Go](https://www.bewerbung2go.de/)** — AI-driven platform that helps German-speaking users generate customized cover letters and optimize job applications efficiently. `Freemium` `Web`
- **[Bluebeam Revu](https://www.bluebeam.com/)** — PDF-based collaboration and markup software tailored for the architecture, engineering, and construction industries, enabling efficient document management and real-time team collaboration. `Paid` `Web` `Windows` `iOS`

## Design and creative

Interface design, prototyping, and visual creative work.

- **[3DAiLY](https://3daily.ai/)** — Web-based AI platform that helps users generate and customize 3D models quickly without advanced skills, suitable for designers, game developers, and content creators. `Freemium` `Web`
- **[3DF Zephyr](https://www.3dflow.net/)** — Windows-based photogrammetry software that automatically reconstructs 3D models from photos, supporting drone mapping and detailed 3D mesh creation. `Freemium` `Windows`
- **[3dlogoai](https://www.3dlogoai.com/)** — Web platform that generates customizable 3D logos for businesses and individuals, enabling quick and professional branding solutions without design experience. `Paid` `Free Trial` `Web`
- **[3Dthis](https://3dthis.com/)** — Web-based platform that allows users to create, animate, and customize 3D avatars and models from photos or templates without software installation. `Freemium` `Web`
- **[3D Viewer by ModelViewer](https://modelviewer.dev/)** — Open-source web component that allows developers to embed interactive 3D models on websites with support for glTF files, built-in controls, and augmented reality features. `Free` `Web`
- **[99designs](https://99designs.com/)** — Online platform that allows businesses to run design contests or hire freelance designers directly to create custom logos, branding, websites, and marketing materials. `Freemium` `Web`
- **[Accio](https://www.accio.com/)** — Writing assistant that helps users generate, edit, and improve written content efficiently through a web-based platform. `Paid` `Free Trial` `Web`
- **[Ad Mocker](https://admocker.com/)** — Free web-based tool that helps marketers and designers create realistic ad mockups quickly without needing advanced design software. `Free` `Web`
- **[Adstronaut](https://www.adstronaut.net/)** — Ad spy tool that helps marketers research and analyze competitor ads on Facebook and Instagram to improve their own campaigns. `Freemium` `Web`
- **[ai action figure gen...](https://aiactionfiguregenerator.online/)** — Free web tool that creates custom 3D action figure models from user descriptions using AI technology. `Free` `Web`
- **[AI App Icon](https://www.aiappicon.com/)** — Web-based tool that uses artificial intelligence to generate custom, high-quality app icons quickly and easily for mobile applications. `Freemium` `Web`
- **[AI Avatar Generator](https://www.aiavatar.cc/)** — Online tool that uses artificial intelligence to create personalized digital avatars from photos or text prompts, offering multiple styles and high-resolution downloads. `Freemium` `Web`
- **[AI Cover](https://aicover.fun/)** — Online tool that uses artificial intelligence to generate custom cover art for music, books, and other creative projects quickly and easily. `Freemium` `Web`
- **[AI Design](https://aidesigns.top/)** — Web platform that uses artificial intelligence to automate graphic design, enabling users to create logos, posters, and marketing visuals quickly with customizable AI-generated templates. `Freemium` `Web`
- **[AI Geometric](https://www.aigeometric.com/)** — Web-based 3D modeling software that uses AI to help users create complex geometric designs quickly and intuitively, suitable for designers, educators, and creatives. `Freemium` `Web`
- **[AIGraphics](https://aigraphics.io/)** — Web platform that generates custom images from text prompts, offering customizable styles and high-resolution downloads for creative projects. `Freemium` `Web`
- **[AI HomeDesign](https://aihomedesign.com/)** — Web-based interior design tool that uses artificial intelligence to help users create, customize, and visualize home layouts and floor plans with 3D visualization and furniture placement features. `Freemium` `Web`
- **[AI Icon Generator](https://themebutler.com/)** — Web-based tool that uses AI to create custom icons from user keywords, offering quick, scalable icon designs for various projects. `Freemium` `Web`
- **[aiinteriordesign.io](https://aiinteriordesign.io/)** — Web-based AI tool that helps users generate interior design layouts, style recommendations, and virtual staging for residential and commercial spaces without prior design experience. `Freemium` `Web`
- **[AI Interior Room Planner](https://aiinteriorplanner.com/)** — Web-based tool that uses artificial intelligence to help users design and visualize interior room layouts with optimized furniture placement and 3D visualization. `Paid` `Free Trial` `Web`
- **[Aikiu Studio](https://aikiustudio.com/)** — Web-based AI art generation platform that transforms text prompts into unique digital artwork with customizable styles and high-resolution downloads. `Freemium` `Web`
- **[AI LinkedIn Banners](https://www.ailinkedinbanners.com/)** — Web tool that uses AI to generate and customize LinkedIn banner images, helping users create professional profile headers quickly without design skills. `Freemium` `Web`
- **[AI Logo Generator](https://ailogogenerator.net/)** — Online tool that uses artificial intelligence to create custom logos quickly, offering multiple design options and customization features with pay-per-download pricing. `Freemium` `Web`
- **[Ai Movie Poster Generator](https://movieaiposter.com/)** — Web tool that creates custom movie posters using AI based on user input, ideal for filmmakers and marketers. `Freemium` `Web`
- **[AI Poster Maker](https://ai-poster-maker.com/)** — Online tool that uses AI to help users create custom posters quickly by providing templates, design suggestions, and easy editing features. `Freemium` `Web`
- **[AI Space of Design](https://aispaceofdesign.com/)** — Web-based graphic design tool that uses AI to help users create logos, branding, and marketing materials quickly and easily without advanced design skills. `Freemium` `Web`
- **[AI t-shirt design generator](https://www.pietrastudio.com/)** — Free web tool that creates custom t-shirt graphics using AI based on user prompts, ideal for quick and easy apparel design. `Free` `Web`
- **[AI YouTube Thumbnails](https://aiyoutubethumbnails.com/)** — AI-driven web tool that helps YouTube creators generate custom, optimized thumbnails quickly without design skills. `Freemium` `Web`

## Image generation and editing

Generating, editing, upscaling, and retouching still images.

- **[123Colorize](https://123colorize.com/)** — Web tool that automatically adds color to black and white photos, enabling quick and realistic photo restoration online. `Freemium` `Web`
- **[1photoai](https://1photoai.com/)** — AI-driven web platform that automates photo retouching, background removal, and image upscaling, designed for professionals and content creators seeking fast, high-quality photo enhancements. `Freemium` `Web`
- **[A1 Art](https://a1.art/)** — Web-based AI image generator that creates digital artwork from text prompts, offering free and subscription plans for users. `Freemium` `Web`
- **[Adobe](https://www.adobe.com/)** — Adobe offers AI tools including Firefly (image generation), Generative Fill in Photoshop, Generative Recolor in Illustrator, and AI editing in Premiere Pro. All outputs are commercially safe and trained on licensed content. `Freemium` `Web` `Windows` `macOS` `iOS` `Android` `API`
- **[Adobe Firefly](https://firefly.adobe.com/)** — Art generator by Adobe that creates images from text prompts, integrated with Creative Cloud for professional design workflows. `Freemium` `Web`
- **[Aftershoot](https://aftershoot.com/)** — Desktop culling tool that rates photos on sharpness, exposure, and facial expression so photographers can shortlist a shoot quickly. `Paid` `Free Trial` `macOS`
- **[AI Anime Generator](https://ai-anime-generator.com/)** — Web-based tool that creates anime-style character images from text prompts or style selections using artificial intelligence. `Freemium` `Web`
- **[AI Art Generator | 100% Free](https://aiartfree.online/)** — Web-based tool that allows users to create unique digital artwork instantly using AI technology without any cost or registration. `Free` `Web`
- **[AI Avatar Maker](https://www.avatarstyle.net/)** — Web-based tool that uses AI to generate custom avatars from photos or descriptions, offering multiple styles and easy downloads. `Freemium` `Web`
- **[AI Clothes Remover](https://anieraser.media.io/)** — Online tool that uses artificial intelligence to automatically remove clothes from photos, helping users anonymize images or create artistic edits. `Freemium` `Web`
- **[AI Describe Picture](https://describepicture.org/)** — Free web tool that uses AI to generate descriptive captions for images, enhancing accessibility and SEO by providing automatic alt text. `Free` `Web`
- **[ai drawing generator](https://ai-drawing-generator.com/)** — Web-based tool that creates digital drawings from text prompts using AI, offering multiple art styles and easy downloads. `Freemium` `Web`
- **[AI Gahaku](https://ai-art.tokyo/)** — Free web-based AI art generator that converts photos into classical portrait paintings using deep learning. `Free` `Web`
- **[AI Headshot Generators](https://aiheadshotgenerators.com/)** — Web-based platform that uses artificial intelligence to create realistic and customizable professional headshots quickly and easily without the need for traditional photography. `Freemium` `Web`
- **[AI Headshots](https://ai-headshots.net/)** — Web service that generates realistic professional headshot photos using AI from user-uploaded selfies, offering multiple styles and high-resolution downloads. `Free` `Web`
- **[AI headshots and selfies](https://kahma.io/)** — Kahma AI offers a web-based tool that generates realistic AI headshots and selfies from user photos, ideal for professional profiles and social media. `Freemium` `Web`
- **[AI image extender](https://aiimageextender.com/)** — Online tool that uses artificial intelligence to seamlessly extend images by generating new content around the original photo, enabling natural background expansion and image resizing without cropping. `Freemium` `Web`
- **[AI Image Generator/Search](https://www.ai-img-gen.com/)** — Web platform that allows users to generate images from text prompts and search a database of AI-created images for creative and commercial use. `Freemium` `Web`
- **[AI Majic](https://aimajic.com/)** — Web-based AI art generator that creates unique images from text prompts, offering multiple art styles and easy customization for digital artists and creators. `Freemium` `Web`
- **[AI OTAKU LABO](https://ai-otaku-labo.com/)** — Web-based AI art generator focused on creating anime-style images using text prompts and style customization, suitable for anime fans and creators. `Freemium` `Web`
- **[AI Photo Robot](https://aiphotorobot.com/)** — Browser photo editor that removes backgrounds, retouches portraits, and enhances images without manual masking. `Freemium` `Web`
- **[AI Pixar Posters](https://aipixarposters.com/)** — Web-based tool that uses AI to create custom movie posters in the Pixar animation style based on user text prompts. `Freemium` `Web`
- **[AI Portrait Gen](https://aiportraitgen.com/)** — Web-based tool that uses artificial intelligence to generate unique digital portraits from user inputs, offering multiple styles and easy downloads. `Freemium` `Web`
- **[AI Shots](https://aishots.com/)** — Web platform that uses AI to generate and edit images from text prompts or existing photos, designed for creatives and marketers. `Freemium` `Web`
- **[AI Tattoo Creator](https://tattooai.net/)** — Web-based tool that uses artificial intelligence to generate custom tattoo designs based on user input, offering multiple styles and easy downloads. `Freemium` `Web`
- **[AI Twin: Your Digital Self](https://aitwin.us/)** — Builds a digital avatar that imitates your appearance and manner, for use in virtual interactions. `Freemium` `Web`
- **[@imagetotext.me](https://imagetotext.me/)** — Free web-based OCR tool that extracts text from images quickly and without registration, supporting common image formats like JPG and PNG. `Free` `Web`

## Writing and content

Drafting, rewriting, editing, summarising, and translating text.

- **[20Paths](https://20paths.com/)** — Writing assistant that generates multiple creative story paths and content suggestions to help writers overcome writer's block and enhance storytelling. `Freemium` `Web`
- **[750 Words](https://750words.com/)** — Web-based platform that encourages users to write 750 words daily to build a consistent writing habit, offering a distraction-free interface and progress tracking. `Paid` `Free Trial` `Web`
- **[AI21 Studio](https://www.ai21.com/)** — Writing platform by AI21 Labs that provides advanced language models for generating, editing, and understanding text, suitable for content creation, coding help, and creative writing. `Freemium` `Web` `API`
- **[AI Detector & Plagiarism Scan](https://textdetector.ai/)** — Web tool that identifies AI-generated text and checks for plagiarism to ensure content originality. `Freemium` `Web`
- **[AI Detector Writer](https://aidetectorwriter.com/)** — Free online tool that analyzes text to determine if it was generated by AI, providing a confidence score and detailed report to help users verify content authenticity. `Free` `Web`
- **[AI Game Master- Dungeon RPG](https://www.aigamemaster.app/)** — Web-based AI tool that helps tabletop RPG players and Dungeon Masters generate dynamic storylines, quests, and characters, supporting both solo and group play. `Freemium` `Web`
- **[AIHumanize.com](https://aihumanize.com/)** — Online tool that detects AI-generated text and checks for plagiarism to help users verify content authenticity. `Freemium` `Web`
- **[AI News Daily](https://weekdays.ai/)** — Web platform that delivers automated, curated daily summaries of the latest artificial intelligence news, helping users stay informed efficiently. `Freemium` `Web`
- **[AI-Novel](https://ai-novel.com/)** — Web-based AI writing assistant designed to help authors generate novels and stories by providing AI-driven content creation tools and customizable writing styles. `Freemium` `Web`
- **[AI or Not](https://www.aiornot.com/)** — Free online tool that detects whether text is generated by AI or written by a human by analyzing linguistic patterns and providing a confidence score. `Free` `Web`
- **[AI Screenwriter](https://aiscreenwriter.com/)** — Web platform that uses artificial intelligence to help users create, format, and refine professional screenplays and scripts quickly and efficiently. `Paid` `Free Trial` `Web`
- **[AIStoryBuilders](https://aistorybuilders.com/)** — Writing assistant that generates creative stories and content based on user prompts, designed to help writers and marketers produce engaging narratives efficiently. `Paid` `Free Trial` `Web`
- **[AI Story Generator free unlimited](https://www.story321.org/)** — Story321's AI Story Generator free unlimited is a web-based tool that allows users to generate unlimited original stories for free by entering prompts, without requiring an account. `Free` `Web`
- **[AI Storyteller](https://www.ai-storyteller.org/)** — Free web tool that uses AI to generate original stories from user prompts without requiring registration. `Free` `Web`
- **[AI Text Detector](https://aitextdetector.online/)** — Free online tool that analyzes text to estimate the likelihood it was generated by artificial intelligence, helping users verify content authenticity quickly and easily. `Free` `Web`
- **[AI-Text-Humanizer.com](https://ai-text-humanizer.com/)** — Online tool that converts AI-generated text into natural, human-like writing by rephrasing sentences to improve readability without changing the original meaning. `Freemium` `Web`
- **[Aithenticate](https://aithenticate.org/)** — Web-based tool that detects AI-generated text and plagiarism to ensure content originality for academic and professional use. `Paid` `Free Trial` `Web`
- **[AI UNDETECT](https://aiundetect.com/)** — Web-based tool that analyzes text to determine the likelihood it was generated by artificial intelligence, helping users verify content authenticity. `Freemium` `Web`

## Video

Video generation, editing, captioning, dubbing, and animation.

- **[123kanfang.com](https://123kanfang.com/)** — Free Chinese streaming website offering a wide range of TV shows and movies without requiring registration. `Free` `Web`
- **[4K AI Upscaler - Free AI image tool](https://upscale-image.com/)** — Free web-based tool that uses AI to increase image resolution up to 4K, improving clarity and detail without quality loss. `Free` `Web`
- **[8i](https://8i.com/)** — Platform that creates photorealistic 3D holograms and avatars using volumetric video technology for VR and AR experiences. `Paid` `Web`
- **[AI Animate Image](https://www.aianimateimage.org/)** — Free online tool that uses AI to animate static photos, especially faces, creating realistic motion effects like blinking and smiling without needing software installation. `Free` `Web`
- **[AI Art Generator by Enhance AI](https://enhanceai.art/)** — Enhance AI's AI Art Generator is a web-based tool that creates unique digital artworks from text prompts using artificial intelligence, suitable for artists and content creators. `Freemium` `Web`
- **[AI Coach Amotions](https://amotionsinc.com/)** — AI-driven platform that provides personalized emotional intelligence and leadership coaching to individuals and organizations, helping improve emotional awareness, empathy, and interpersonal skills. `Paid` `Web`
- **[AI HD Anime](https://aihdanime.com/)** — Online AI tool that upscales and enhances anime videos by increasing resolution, reducing noise, and sharpening details to produce high-definition outputs. `Freemium` `Web`
- **[AI Hug Video Generator, Hug Video Studio](https://aihug.app/)** — Web-based tool that creates videos from text using AI avatars and text-to-speech technology, enabling fast and easy video production without filming. `Freemium` `Web`
- **[AI Image and Video Generators](https://aiimageandvideogenerators.xyz/)** — Web platform that allows users to create images and videos using AI technology by inputting text prompts or other instructions, enabling fast and creative media production. `Freemium` `Web`
- **[AI Images Editor](https://aiimageeditor.ai/)** — Web-based tool that uses artificial intelligence to enhance photos, remove backgrounds, and upscale images quickly and easily without requiring advanced skills. `Freemium` `Web`
- **[AI Image to Video Online](https://imagetovideoai.io/)** — Web-based tool that converts static images into animated videos using AI technology, offering easy video creation without editing skills. `Freemium` `Web`
- **[AI Kissing Video Generator Free](https://www.aikissingvideogenerator.org/)** — Web-based tool that creates realistic kissing videos by synthesizing uploaded facial photos using AI technology. It is free and easy to use for entertainment and creative purposes. `Free` `Web`
- **[AI Localizer](https://www.wideanglesoftware.com/)** — Tool that automates software and website localization by translating content into multiple languages with quality assurance and collaboration features. `Paid` `Free Trial` `Web`
- **[AI Picasso - AI dance](https://aipicasso.app/)** — Web-based tool that uses artificial intelligence to generate unique dance videos and motion art, enabling users to create creative animations without video editing skills. `Freemium` `Web`
- **[AI Powered Image Upscaler](https://www.aiimageupscale.com/)** — Web-based tool that uses artificial intelligence to enlarge and enhance images, improving resolution and reducing noise without quality loss. `Freemium` `Web`
- **[AI STUDIOS](https://www.aistudios.com/)** — Web platform that generates videos from text scripts using AI avatars and text-to-speech technology, enabling quick and easy video creation without filming. `Freemium` `Web`
- **[AI Subtitle Image Generator](https://easyaicaption.com/)** — Web tool that creates subtitle images by generating and overlaying captions on pictures, enhancing content accessibility and engagement. `Freemium` `Web`

## Developer infrastructure and models

Model hosting, training, inference, and machine-learning infrastructure.

- **[16x Prompt](https://prompt.16x.engineer/)** — Web tool that automates the generation and optimization of prompts to improve AI language model responses, boosting productivity for developers and content creators. `Freemium` `Web`
- **[4oImageAPI.io: Affordable and Reliable 4o Image API](https://4oimageapi.io/)** — Cloud-based image processing API that provides affordable and reliable image optimization, resizing, cropping, and format conversion services for developers and businesses. `Freemium` `Web` `API`
- **[AI-Prompt Lab](https://ai-promptlab.com/)** — Web platform that enables users to create, test, and optimize AI prompts across various models with collaboration and version control features. `Freemium` `Web`
- **[AI Prompt Studio](https://aipromptstudio.com/)** — Web platform for creating, managing, and automating AI prompts and workflows, designed to improve AI content generation and prompt engineering efficiency. `Freemium` `Web`
- **[Ardor Ã¢â‚¬â€ Prompt in. Product out.](https://ardor.cloud/)** — Writing assistant that converts user prompts into complete written content, helping users create marketing copy, creative writing, and other text efficiently. `Freemium` `Web`
- **[awesome claude prompts](https://awesomeclaudeprompts.com/)** — Free online resource offering curated prompt templates to improve and inspire conversations with Claude AI. `Free` `Web`
- **[Backmesh](https://backmesh.com/)** — Platform that helps enterprises integrate multiple data sources, automate workflows, and deploy AI models to improve operational efficiency. `Paid` `Web`
- **[BuildPrompt](https://buildprompt.ai/)** — Web platform that enables users to design, automate, and optimize AI prompts through a visual interface and workflow automation, integrating with AI APIs like OpenAI. `Paid` `Free Trial` `Web`
- **[Chat Prompt Genius](https://chatpromptgenius.com/)** — Web platform that provides curated prompt templates and customization tools to help users craft effective prompts for ChatGPT and other AI chatbots, improving response quality and saving time. `Freemium` `Web`
- **[ChatWizard: 1-Click ChatGPT Prompts](https://chatwizard.online/)** — Web tool that provides one-click prompt templates to quickly generate effective ChatGPT prompts, enhancing AI content creation and productivity. `Freemium` `Web`
- **[Deep Dream Generator](https://deepdreamgenerator.com/)** — Online AI tool that uses neural networks to create surreal and artistic images from user photos by applying various AI styles and effects. `Freemium` `Web`
- **[Dumpling AI](https://www.dumplingai.com/)** — Writing assistant that helps users generate, rewrite, and enhance written content efficiently, primarily supporting English language content creation. `Freemium` `Web`
- **[FineCodeX](https://finecodex.com/)** — Coding assistant that helps developers write, debug, and optimize code with intelligent suggestions and automated code generation. `Freemium` `Web`
- **[Gemini & Gemini Advanced](https://gemini.google.com/)** — Gemini and Gemini Advanced are GoogleÃ¢â‚¬â„¢s advanced AI language models designed for conversational AI, content generation, and coding assistance, supporting multiple languages and accessible via web and API. `Freemium` `Web` `API`
- **[hostyAi](https://hostyai.com/)** — Platform that automates web hosting management tasks including server provisioning, optimization, security updates, and multi-cloud hosting management. `Freemium` `Web`

## Chatbots and assistants

General-purpose assistants, answer engines, and conversational products.

- **[Ace Interview - AI Interview Assistant](https://aceinterview.co/)** — AI-driven platform that helps job seekers practice mock interviews, receive personalized feedback, and improve their interview skills to increase their chances of landing a job. `Freemium` `Web`
- **[AskJesus](https://www.askjesus.me/)** — Free AI chatbot that answers questions about the Bible and Christian faith, offering scripture-based spiritual guidance through a conversational web interface. `Free` `Web`
- **[Chatbot Arena](https://chatbotarena.com/)** — Free web platform that lets users compare multiple AI chatbots side-by-side by interacting with them simultaneously and rating their responses, helping developers and enthusiasts evaluate chatbot performance. `Free` `Web`
- **[chatglm.cn](https://chatglm.cn/)** — Open-source AI chatbot platform developed by Tsinghua University's KEG Lab, featuring a bilingual Chinese-English large language model for conversational AI accessible via web and API. `Free` `Web` `API`
- **[ChatGPT FranÃƒÂ§ais (French)](https://chatgptfrench.org/)** — Free web-based AI chatbot designed specifically for French language users to practice conversations, generate content, and support French communication needs. `Free` `Web`
- **[Chat With Anime](https://chat-with-anime.com/)** — Free web-based AI chatbot platform that lets users interact with virtual anime characters through realistic conversations and roleplay. `Free` `Web`
- **[Coachchat](https://coachchat.me/)** — AI-driven coaching platform that provides personalized life and career guidance through interactive chat conversations, helping users set goals, stay motivated, and develop professionally. `Freemium` `Web`
- **[Dreammate](https://dreammate.ai/)** — Virtual companion that provides personalized, empathetic chat experiences to support emotional well-being and reduce loneliness. `Freemium` `Web` `iOS` `Android`
- **[FileGPT](https://filegpt.app/)** — Web-based AI assistant that allows users to upload documents and interact with their content via chat, enabling quick understanding, summarization, and data extraction from files. `Freemium` `Web`
- **[FileZen](https://filezen.top/)** — Secure file sharing and cloud storage platform that provides end-to-end encryption for safe file transfer and storage across multiple devices. `Freemium` `Web`
- **[hkgpt.io](https://hkgpt.io/)** — Hong Kong-based AI chatbot platform powered by GPT technology that supports multilingual conversations in English and Chinese, designed for customer support, language learning, and general AI chat interactions. `Freemium` `Web`
- **[InterviewPal](https://www.interviewpal.com/)** — AI-driven platform that helps job seekers practice interviews by providing tailored questions and detailed feedback to improve their performance. `Freemium` `Web`
- **[Interview Prep Now](https://interviewprepnow.com/)** — Online subscription-based platform offering extensive interview practice questions, answer frameworks, and coaching strategies tailored to various industries to help job seekers prepare effectively for interviews. `Paid` `Web`

<!-- records:end -->

## المخطط

عشرة حقول، متطابقة في كل سجل.

| الحقل | النوع | مطلوب | الوصف |
|---|---|---|---|
| `name` | نص | نعم | اسم المنتج، بالهجاء الذي يكتبه به المورّد |
| `official_url` | نص | نعم | موقع المنتج نفسه. HTTPS، أساسي، بلا معاملات تتبع أو إحالة |
| `primary_category` | نص | نعم | واحد من التصنيفات العشرين في `categories.csv` |
| `secondary_category` | نص أو null | لا | تصنيف ثانٍ حيث ينطبق بوضوح |
| `pricing_model` | مصفوفة نصوص | نعم | واحد أو اثنان من `Free` و`Freemium` و`Paid` و`Open Source` و`Free Trial` |
| `platform` | مصفوفة نصوص | لا | صفر أو أكثر من `Web` و`Windows` و`macOS` و`Linux` و`iOS` و`Android` و`API` و`CLI` و`Browser Extension` و`VS Code` و`JetBrains` و`Discord` |
| `short_description` | نص | نعم | جملة أو جملتان، حتى 240 محرفًا، تنتهي بنقطة |
| `open_source` | منطقي | نعم | هل صدر المنتج برخصة مفتوحة المصدر |
| `api_available` | منطقي | نعم | هل يعرض المنتج واجهة برمجية عامة |
| `last_verified` | نص | نعم | بصيغة ISO `YYYY-MM-DD`، تاريخ آخر فحص للسجل |

في ملف CSV تُوصل المصفوفات بفاصل `; ` وتكون القيم المنطقية النصين `true` و`false`. والخانة
الفارغة هي مقابل `null` في JSON.

### المفردات

`pricing_model` و`platform` مجموعتان مغلقتان. والقيمة خارجهما عيب لا تنويع، وفحص الإصدار يسقط
عليها.

و`Open Source` تعني رخصة معتمدة من OSI. والمنتجات متاحة المصدر ذات القيود التجارية لا تحملها،
وقيمة `open_source` فيها `false`.

### ما ليس في المخطط عن قصد

لا معرّفات داخلية، ولا درجات تحريرية، ولا أعداد مشاهدات، ولا بيانات ترتيب، ولا سجلات تقديم،
ولا بيانات اتصال، ولا محتوى مسوّدة، ولا بيانات إحالة، ولا معرّفات قواعد بيانات أو تصنيفات.
فلا شيء من ذلك يعني شيئًا خارج أنظمة TiorAI، وأكثره ينبغي ألا يغادرها.

### التحقق مقابل المخطط

[`data/schema.json`](data/schema.json) مخطط JSON (مسودة 2020-12) يغطي كل حقل، والمفردتين
المغلقتين، وقائمة التصنيفات، وصيغة التاريخ. والسجلات الـ٧٤٨ المنشورة كلها تجتازه، وهو يرفض
الأخطاء التي تستحق الالتقاط: وسم تسعير خارج المفردات، ورابط غير HTTPS، وحقلًا مطلوبًا ناقصًا.

```python
import json, jsonschema

records = json.load(open("data/ai-tools.json", encoding="utf-8"))
schema  = json.load(open("data/schema.json", encoding="utf-8"))
jsonschema.validate(records, schema)          # يرفع استثناءً عند أول مشكلة
```

استعمله لفحص إضافاتك قبل فتح طلب دمج، ولالتقاط تغيير كاسر قبل أن يصل إلى مسارك.

### الإصدارات

يتبع المخطط الإصدار الدلالي عبر [CHANGELOG.md](CHANGELOG.md). **وإضافة حقل أو حذفه أو إعادة
تسميته أو تغيير نوعه رفعٌ للإصدار الرئيس**، فتستطيع تثبيت إصدار رئيس والوثوق بالأعمدة.
وملف `data/schema.json` هو موضع كتابة ذلك العقد، ففرق ذلك الملف هو فرق العقد.

## كيف تتحقق السجلات

تأتي السجلات من فهرس أدوات الذكاء الاصطناعي العام عند TiorAI ثم تُفحص مستقلة. وقد اجتاز كل
واحد من السجلات الـ٧٤٨ المنشورة كل ما يلي.

**١. أُعيدت كتابة الرابط ولم يُورَث.** فكل رابط مخزَّن في الفهرس يحمل تتبّع إحالة من TiorAI،
وحمل عدد صغير منها معاملات إحالة من أطراف أخرى. وكل رابط هنا أُعيد اشتقاقه: فُرض عليه HTTPS،
وحُذف الجزء المرجعي، وجُرّدت واحد وعشرون صنفًا من معاملات التتبع والإحالة بالاسم، وحُفظت
المسارات ذات المعنى.

**٢. فُتح الرابط عبر HTTP.** بوكيل متصفح، وباتباع التحويلات إلى عمق ثمانية، وبمهلة اتصال ١٢
ثانية ومهلة كلية ٣٠ ثانية، وبفاصل ٤٠٠ جزء من الثانية على الأقل بين الطلبات إلى المضيف نفسه.
وعُوملت الرموز `403` و`405` و`429` و`999` على أنها حماية من الروبوتات لا موت، وأُعيد فحصها
بطريق ثانٍ قبل أي حكم.

**٣. فُحصت وجهة التحويل لا رمز الحالة وحده.** وهذا التقط نمط الفشل الأهم في مجموعة بيانات
أدوات: نطاق منتهٍ ما زال يعيد `200` لأنه صار يقدّم صفحة بيع نطاقات. وقد حُذفت أربعة سجلات
لهذا. وحُذف ثلاثة وتسعون آخر لتحويلها إلى نطاق مسجَّل مختلف، وذلك يعني عادةً إعادة تسمية أو
استحواذًا تعذّر حسمه آليًا.

**٤. حُذفت المكررات بأربع طرق.** الاسم المعياري، والرابط الأساسي، والمضيف الكامل، والنطاق
المسجَّل. وكل ما وسمه البناء الداخلي مطابقة غير مؤكدة أُسقط بدل دمجه.

**٥. فُحص كل حقل مقابل المخطط.** المفردات والأنواع وشكل الرابط وصيغة التاريخ وطول الوصف
والتطابق بين CSV وJSON، في كل سجل.

### ما لا يقوله التحقق

كون الرابط يُفتح لا يعني أن المنتج ما زال يعمل، ولا أن وسم التسعير حالي، ولا أن الوصف دقيق
اليوم. وحقل `last_verified` يسجّل متى فُحص السجل، وقراءته الصادقة «كان هذا صحيحًا في ذلك
التاريخ».

والتسعير أسرع الحقول هنا حركةً وأول ما سيتقادم.

## استعمال البيانات

```python
import json

with open("data/ai-tools.json", encoding="utf-8") as f:
    tools = json.load(f)

free = [t for t in tools if "Free" in t["pricing_model"] or "Freemium" in t["pricing_model"]]
with_api = [t for t in tools if t["api_available"]]
print(len(tools), len(free), len(with_api))
```

```python
import csv

with open("data/ai-tools.csv", encoding="utf-8", newline="") as f:
    rows = list(csv.DictReader(f))

# المصفوفات موصولة بفاصل "; " في ملف CSV
for r in rows[:3]:
    print(r["name"], r["pricing_model"].split("; "))
```

```bash
# التصنيفات العشرون بأعدادها، دون تحميل أي شيء
column -s, -t data/categories.csv
```

ملف CSV بترميز UTF-8 بصف ترويسة، ونهايات أسطر `\n`، وتنصيص RFC 4180. وهو يفتح صحيحًا في
Excel وNumbers وLibreOffice وpandas وDuckDB دون معالجة مسبقة.

### التحديث

لا يوجد اتصال حي بأي نظام من أنظمة TiorAI، وإعادة إنتاج تحديث لا تتطلب وصولًا إلى واحد.
والعملية هي:

1. استخراج سجلات المرشحين العامة.
2. تعيير الروابط وربط التصنيفات والتسعير والمنصات بالمفردات المنشورة.
3. التحقق من كل رابط عبر HTTP، بما في ذلك وجهة التحويل.
4. التحقق من المخطط والمفردات والمكررات والتطابق بين CSV وJSON.
5. المقارنة بالإصدار السابق ومراجعة ما تغيّر.
6. النشر، وتسجيل التغيير في سجل التغييرات.

والخطوتان ٣ و٤ هما المهمّتان. فأي شيء يستطيع توليد جدول كبير من الأدوات؛ وما يجعل هذا الجدول
صالحًا للاستعمال أن صفوفه فُحصت وأن الراسب منها حُذف.

## حدود معروفة

مذكورة صراحةً، لأن مجموعة البيانات التي تخفيها أصعب في الاستعمال لا أسهل.

- **هذه ليست عيّنة من سوق الذكاء الاصطناعي.** بل هي ما نجا من التحقق من فهرس واحد. ونسب
  التصنيفات تعكس ذلك المرشِّح لا الميدان.
- **الأوصاف تأتي من فهرس TiorAI نفسه.** وقد عُيّرت وحُدّد طولها لهذا الإصدار، وقُصّت العبارة
  الافتتاحية النمطية حيث كانت تعيد اسم المنتج وحسب. وهي نص تحريري من الطرف الأول، لا نثر
  أُعيدت كتابته مستقلًا، وليست نصًا تسويقيًا من المورّد.
- **أوسمة التسعير تصنيفية وتتقادم.** ولا تُنشر مبالغ، لأن المبالغ تصير خاطئة خلال أسابيع.
  والأوسمة تدوم أطول، لا إلى الأبد.
- **حقل `open_source` متحفّظ.** فهو `true` حيث ثبتت رخصة معتمدة من OSI فقط. وبعض المنتجات
  متاحة المصدر قيمتها `false` بحق وقد تبدو أخطاءً.
- **انحياز إلى الإنجليزية.** فالفهرس الذي سُحبت منه إنجليزي أولًا.
- **التغطية متفاوتة.** فبعض التصنيفات رقيق لأن التحقق حذف منها أكثر، لا لأن أدواتها أقل.
- **لا إشارة جودة.** فلا درجة ولا تقييم ولا ترتيب، ولا شيء من ذلك مخطط له. والإدراج يعني أن
  السجل تُحقق منه، لا أن المنتج جيد.

## اقتراح تصحيح

- [اقترح سجلًا](../../issues/new?template=suggest-a-record.yml)
- [أبلغ عن رابط معطّل](../../issues/new?template=report-a-broken-link.yml)

وأثمن بلاغ هنا سجل خاطئ لا سجل ناقص: منتج أُغلق، أو وسم تسعير تغيّر، أو قيمة `open_source`
لا تطابق الرخصة. فتلك أخطاء لا يستطيع مستعمل البيانات رؤيتها.

## المساهمة

اقرأ [CONTRIBUTING.md](CONTRIBUTING.md). التصحيحات أثمن من الإضافات في هذا المستودع، وكلاهما
يمرّ بفحوص المخطط نفسها قبل الإصدار.

ولا تفتح طلب دمج يحرّر مجلد `data/` مباشرة. فتلك الملفات يولّدها مسار تحقق، والتحرير اليدوي
يُطمس عند الإصدار التالي دون أن يلحظ أحد. افتح مشكلة بالتصحيح بدلًا من ذلك.

## إخلاء مسؤولية

كل منتج موصوف هنا تبنيه وتشغّله جهة أخرى، لا TiorAI. وبيانات المنتجات تتغيّر باستمرار: فالأدوات
تُغلق وتُشترى وتغيّر أسماءها وأسعارها دون إشعار. والسجلات كانت دقيقة بقدر ما أمكن إثباته في
التاريخ المذكور في `last_verified` ولا تحمل ضمانًا بعده. تحقّق من كل ما تنوي الاعتماد عليه.

والإدراج ليس تزكية، ولا يُعبَّر عن ترتيب أو حكم جودة ولا يُلمَّح إليهما. وأسماء المنتجات
وعلاماتها التجارية تخصّ أصحابها وتُستعمل هنا للتعريف فقط.

## الرخصة

[CC BY 4.0](LICENSE). انسخ هذه المجموعة وعدّلها وأعد نشرها، تجاريًا أيضًا، بشرط نسبتها إلى
TiorAI وبيان ما غيّرته.

تغطي الرخصة التجميع: اختيار السجلات، وتصنيف الفئات، وتعريفات الحقول، والأوصاف. ولا تغطي اسم
TiorAI ولا شعارها، ولا تغطي المنتجات المدرجة ولا علاماتها التجارية ولا محتواها.

ولا تغطي كذلك الوقائع نفسها. فاسم منتج وعنوانه وهل له خطة مجانية أشياء لا يملكها أحد، والنسبة
مستحقة على عمل جمعها والتحقق منها ووصفها لا على الوقائع ذاتها.

## عن TiorAI

[TiorAI](https://tiorai.com/) دليل لأدوات الذكاء الاصطناعي. وهذه المجموعة مجموعة فرعية مُتحقق
منها من فهرسه العام، منشورة في صيغة تنفع من يريد البيانات لا الموقع.

- [دليل أدوات الذكاء الاصطناعي](https://tiorai.com/tools/)
