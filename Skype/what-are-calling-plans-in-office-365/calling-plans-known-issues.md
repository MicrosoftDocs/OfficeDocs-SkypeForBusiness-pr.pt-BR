---
title: Problemas conhecidos de planos de chamada
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: baa3645a-0518-472e-942e-971c63ba4ca0
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: Calling Plans
description: 'Learn known issues with the calling plan for Office 365 (PSTN Calling) and what you can do about them. '
ms.openlocfilehash: 42b282bce7ba65dc4e053020970a02e71c98b5bd
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/15/2017
---
# <a name="calling-plans-known-issues"></a>Problemas conhecidos de planos de chamada

Planos de chamadas no Office 365 são um novo recurso, encontrado no Skype para Business Online. A seguir estão os problemas atuais que estão sendo rastreados e ativamente investigados. Eles serão potencialmente resolvidos quando o recurso for atualizado em compilações futuras no Office 365 e Skype para Business Online.
  
## <a name="calling-plans-known-issues"></a>Problemas conhecidos de planos de chamada

|**Problema conhecido**|**Comentários**|
|:-----|:-----|
|Transição do Tech Preview licenças para licenças de produção para planos de chamada não atualizar automaticamente a licença.  <br/> |Adquira o seus novas licenças primeiro para que sejam prontos para ser atribuído aos seus usuários. Remova a licença de promoção (Tech Preview) de um usuário e atribuir **imediatamente** as novas licenças **Domésticas chamar planejar** e/ou **nacionais e internacionais chamar planejar** ao usuário. <br/> Se você estiver removendo e adicionando licenças para vários usuários, é extremamente importante que você remover as licenças de todos os usuários usando o Windows PowerShell e, em seguida, atribuir **imediatamente** as licenças para todos os usuários também usando o Windows PowerShell. Isso garantirá que não há nenhuma interrupção do serviço quando lidar com grandes volumes de atribuições de licença de usuário. Para scripts do PowerShell de amostra, consulte [Atribuir Skype para licenças de negócios e equipes da Microsoft](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).  <br/> **Observação:** Se você estiver usando a conectividade de PSTN local para usuários de híbrido, você *só* precisará atribuir uma licença de **Sistema telefônico** . Você **não** deve também atribuir uma chamada plano de voz. No entanto, se você estiver habilitando chamar planos no Office 365 para usuários que estão no Office 365, você precisa atribuir ainda um **Domésticas chamar planejar** ou uma licença **nacionais e internacionais chamar planejar** para esses usuários. Consulte [Atribuir Skype para licenças de negócios e equipes da Microsoft](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).

> [!NOTE]
> Se você precisar fazer mais números de telefone que isso, por favor, [contate o suporte para produtos de negócios - ajuda de Admin](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |
   
## <a name="related-topics"></a>Tópicos relacionados
[Transferindo perguntas comuns de números de telefone](transferring-phone-numbers-common-questions.md)

[Diferentes tipos de números de telefone usados para planos de chamada](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Gerenciar números de telefone para sua organização](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[Termos e condições para chamadas de emergência](emergency-calling-terms-and-conditions.md)

[Skype for Business Online: Rótulo de aviso de isenção de responsabilidade de chamadas de emergência](https://go.microsoft.com/fwlink/?LinkID=692099)
