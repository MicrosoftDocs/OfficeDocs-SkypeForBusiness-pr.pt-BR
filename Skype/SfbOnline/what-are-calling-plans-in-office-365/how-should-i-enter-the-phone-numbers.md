---
title: "Como deve inserir os números de telefone?"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 28aa24b4-8c81-4327-9752-989ea7540db2
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords: ms.lync.lac.PortOrderNumbers
ms.custom:
- Calling Plans
description: "Saiba como configurar os números de telefone quando transportá-las para Skype para negócios. "
ms.openlocfilehash: c68a42838021c9f8a564b55dbac078af07d9031b
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2018
---
# <a name="how-should-i-enter-the-phone-numbers"></a>Como deve inserir os números de telefone?

Quando você estiver portar números de telefone, você deverá inseri-los no formato correto. 
  
> [!NOTE]
> Cada número de telefone ou o intervalo de número de telefone deve ser inserido separadamente em cada linha. 
  
- Quando você estiver inserindo números de telefone único:
    
  - Todos os caracteres especiais serão ignorados (incluindo o traço "-"). Por exemplo:
    
  - Para um número de 10 dígitos: ** &amp; \*(425\*() (\*&amp;4&amp;\*()) (\*250649** será corrigido para **+14255550649**.
    
  - Para um número de 11 dígitos: **1\*() (\*&amp;42&amp;\*() (\*&amp;55550649** será corrigido para **+14255550649**.
    
  - Todas as marcas serão ignoradas se houver 10 ou 11 dígitos. Por exemplo, ** \<div > 4255551234\</div >** será **+ 14255551234**.
    
  - "-", espaço e parêntese serão ignorada. Por exemplo:
    
  - Para um número de 10 dígitos: **(425) 555-6776** será corrigido para **+14255556776**.
    
  - Para um número de 11 dígitos: **555-6776 1(425)** será corrigido para **+14255556776**.
    
  - Todas as letras serão tratadas como caracteres especiais e ignoradas se não houver um número de telefone de 10 ou 11 dígitos. Por exemplo:
    
  - Para um número de 10 dígitos: **14jaosia2reoij05jof55506ajfoj49isdjf** será corrigido para **+14255550649**.
    
  - Para um número de 11 dígitos: **1ade4jaoda2rfoij05ojof55506dsfoj49if** será corrigido para **+14255550649**.
    
  - Qualquer combinação dos caracteres especiais, mesmo em outros idiomas, será corrigida. Por exemplo: 
    
  - Para um número de 10 dígitos:**中文4中文2ajj5\*() (\*(5() … 551345** será corrigido para **+14555551345**.
    
  - Para um número de 11 dígitos:**中文4中文2$ a5\*() (\*(5() … 55 (.1345** será corrigido para **+14555551345**.
    
  - Se qualquer números contiverem menos de 10 ou mais de 11 dígitos, eles serão realçados para o usuário corrigir:
    
  - \*\*5551245\* \* serão realçadas e precisa ser corrigido.
    
  - **1234567891011** será realçada e precisa ser corrigido.
    
  - Quaisquer números que são menos de 10 ou mais de 11 dígitos, com nenhum dos caracteres especiais serão realçados sem sendo corrigidas automaticamente.
    
  - Para um número de 7 dígitos sem caracteres especiais que é inserido: **123456abcdefg7** será realçada e precisa ser corrigido, mas as letras não ser ignoradas.
    
  - Para um número de 7 dígitos com caracteres especiais que é inserido: **12345!@#$%^&amp;\*() – @# $% ^&amp;\*() 7** será realçado para ser corrigido. Os caracteres especiais não ser ignorados.
    
- Quando você estiver inserindo um intervalo de números de telefone.
    
  - Apenas dois números de telefone são permitidos. O menor número deve ser o primeiro número no intervalo.
    
  - Todos os caracteres especiais (exceto o traço "-") são tratados da mesma como números único. Por exemplo, **(425) 555 0&amp;\*(123-(1425) 5557899nm** será corrigido para **+ 14255550123 - +13202040659**.
    
  - O "-" é usado para separar apenas dois números. Isso não é suportado para incluir vários "-" no intervalo de números. Por exemplo, **(425) 555-0649-(425) 555-1115** deve ser inserido como **(425) 5550649 - for (425) 5551115**.
    
 **Para instruções passo a passo, consulte [transferir os números de telefone para o Office 365](transfer-phone-numbers-to-office-365.md).**

 > [!NOTE]
> Se precisar de mais números de telefone, veja [Contatar o suporte de produtos para empresas - Ajuda para administradores](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).

  
## <a name="related-topics"></a>Tópicos relacionados
[Perguntas comuns sobre a transferência de números de telefone](transferring-phone-numbers-common-questions.md)

[Diferentes tipos de números de telefone usados para Planos de Chamadas](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Gerenciar os números de telefone de sua organização](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[Termos e condições das Chamadas de Emergência](emergency-calling-terms-and-conditions.md)

[Skype for Business Online: etiqueta de aviso de isenção de responsabilidade por Chamadas de Emergência](https://go.microsoft.com/fwlink/?LinkID=692099)