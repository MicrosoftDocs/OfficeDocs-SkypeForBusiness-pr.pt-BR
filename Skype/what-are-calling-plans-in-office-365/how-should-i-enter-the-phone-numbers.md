---
title: "Como devo inserir os números de telefone?"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/13/2017
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- ms.lync.lac.PortOrderNumbers
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom: Adm_O365_FullSet
ms.assetid: 28aa24b4-8c81-4327-9752-989ea7540db2
description: "Learn how to set up phone numbers when you port them to Skype for Business. "
---

# Como devo inserir os números de telefone?

> [!IMPORTANT]
> Este artigo foi traduzido por um sistema de tradução automática, leia o [aviso de isenção de responsabilidade](28aa24b4-8c81-4327-9752-989ea7540db2.md#MT_Footer). Para sua referência, veja a versão em inglês deste artigo [aqui](https://support.office.com/en-us/article/28aa24b4-8c81-4327-9752-989ea7540db2). 
  
Quando você estiver transferindo números de telefone, você deverá inseri-los no formato correto.
  
> [!NOTE]
> Cada número ou intervalo de números de telefone deve ser inserido separadamente em cada linha. 
  
- Ao inserir números de telefone únicos:
    
  - Todos os caracteres especiais serão ignorados (incluindo o traço "-"). Por exemplo:
    
  - Para um número de 10 dígitos: **&amp;*(425*()(*&amp;4&amp;*())(*250649** será corrigido para **+14255550649**.
    
  - Para um número de 11 dígitos: **1*()(*&amp;42&amp;*()(*&amp;55550649** será corrigido para **+14255550649**.
    
  - Todas as marcações serão ignoradas no caso de haver 10 ou 11 dígitos. Por exemplo, **<div> 4255551234</div>** será **+14255551234**.
    
  - "-", espaço e parênteses serão ignorados. Por exemplo:
    
  - Para um número de 10 dígitos: **(425) 555-6776** será corrigido para **+14255556776**.
    
  - Para um número de 11 dígitos: **1(425) 555-6776** será corrigido para **+14255556776**.
    
  - Todas as letras serão tratadas como caracteres especiais e ignoradas se há um número de telefone de 10 ou 11 dígitos. Por exemplo:
    
  - Para um número de 10 dígitos: **14jaosia2reoij05jof55506ajfoj49isdjf** será corrigido para **+14255550649**.
    
  - Para um número de 11 dígitos: **1ade4jaoda2rfoij05ojof55506dsfoj49if** será corrigido para **+14255550649**.
    
  - Qualquer combinação de caracteres especiais, até mesmo em outros idiomas, será corrigida. Por exemplo: 
    
  - Para um número de 10 dígitos: **中文4中文2ajj5*（）（*（5()...551345** será corrigido para **+14555551345**.
    
  - Para um número de 11 dígitos: **中文4中文2$a5*（）（*（5()...55(.1345** será corrigido para **+14555551345**.
    
  - Se qualquer outro número contiver menos de 10 dígitos ou mais de 11 dígitos, ele serão realçados para o usuário corrigir:
    
  - ** 5551245** será realçado e precisará ser corrigido.
    
  - **1234567891011** será realçado e precisará ser corrigido.
    
  - Quaisquer números que são menos de 10 dígitos ou mais de 11 dígitos, com caracteres especiais, serão realçados sem ser corrigido automaticamente.
    
  - Para um número de 7 dígitos sem caracteres especiais que é inserido: **123456abcdefg7** será realçado e precisam ser corrigidos, mas as letras não ser ignoradas.
    
  - Para um número de 7 dígitos com caracteres especiais que é inserido: **12345!@#$%^ &amp; * ()-@# $% ^ &amp; * () 7** será realçada para ser corrigidos. Os caracteres especiais não ser ignorados.
    
- Quando você estiver inserindo um intervalo de números de telefone.
    
  - Apenas dois números de telefone são permitidos. O número menor deve ser o primeiro número do intervalo de números.
    
  - Todos os caracteres especiais (exceto para o traço "-") são tratados da mesma como números único. Por exemplo, **(425) 555 0 &amp; * (123-(1425) 5557899nm** será corrigido para **+14255550123 - +13202040659**.
    
  - O "-" é usado para separar apenas os dois números. Ele não tem suporte para incluir vários "-" no intervalo de número. Por exemplo:, **(425) 555-0649-(425) 555-1115** devem ser inseridas como **(425) 5550649 - (425) 5551115**.
    
 **Para instruções passo a passo, consulte [Transferir números de telefone para o Office 365](transfer-phone-numbers-to-office-365.md).**
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Aviso de Isenção de Tradução Automática**: Este artigo foi traduzido por computador, sem intervenção humana. A Microsoft oferece essas traduções automáticas para ajudar as pessoas que não falam inglês a aproveitar os textos escritos sobre produtos, serviços e tecnologias da Microsoft. Como este artigo foi traduzido automaticamente, é possível que contenha erros de vocabulário, sintaxe ou gramática. 
  
## Consulte Também
<a name="MT_Footer"> </a>

#### 

[Termos e condições para chamadas de emergência](emergency-calling-terms-and-conditions.md)
  
[Áudio período discar complementar de conferência](../accessibility-and-regulatory/audio-conferencing-complimentary-dial-out-period.md)

