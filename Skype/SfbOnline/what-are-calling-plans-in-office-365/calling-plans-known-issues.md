---
title: Problemas conhecidos dos planos de chamadas
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: baa3645a-0518-472e-942e-971c63ba4ca0
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: 'Learn known issues with the calling plan for Office 365 (PSTN Calling) and what you can do about them. '
ms.openlocfilehash: 01a49749f472b6a3e591295cff7184dc26fd564a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32233221"
---
# <a name="calling-plans-known-issues"></a>Problemas conhecidos dos planos de chamadas

Planos de chamadas no Office 365 são um novo recurso, encontrado no Skype para Business Online. A seguir estão os problemas atuais que estão sendo rastreados e ativamente investigados. Eles serão potencialmente resolvidos quando o recurso for atualizado em compilações futuras no Office 365 e Skype para Business Online.
  
## <a name="calling-plans-known-issues"></a>Problemas conhecidos dos planos de chamadas

|**Problema conhecido**|**Comentários**|
|:-----|:-----|
|Transição do Tech Preview licenças para licenças de produção para planos de chamada não atualizar automaticamente a licença.  <br/> |Primeiramente, compre suas novas licenças para que estejam prontas para serem atribuídas aos seus usuários. Remova a licença de promoção (Tech Preview) de um usuário e atribuir **imediatamente** as novas licenças **Domésticas chamar planejar** e/ou **nacionais e internacionais chamar planejar** ao usuário. <br/> Se você estiver removendo e adicionando licenças para vários usuários, é extremamente importante remover as licenças de todos os usuários usando o Windows PowerShell e depois atribuir **IMEDIATAMENTE** as licenças a todos os usuários também usando o Windows PowerShell. Isso garantirá que não há nenhuma interrupção do serviço quando lidar com grandes volumes de atribuições de licença de usuário. Para scripts do PowerShell de amostra, consulte [Atribuir Skype para licenças de negócios e equipes da Microsoft](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).  <br/> **Observação:** Se você estiver usando a conectividade de PSTN local para usuários de híbrido, você *só* precisará atribuir uma licença de **Sistema telefônico** . Você **não** deve também atribuir uma chamada plano de voz. No entanto, se você estiver habilitando chamar planos no Office 365 para usuários que estão no Office 365, você precisa atribuir ainda um **Domésticas chamar planejar** ou uma licença **nacionais e internacionais chamar planejar** para esses usuários. Consulte [Atribuir Skype para licenças de negócios e equipes da Microsoft](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).

> [!NOTE]
> Se você precisar fazer mais números de telefone que isso, por favor, [contate o suporte para produtos de negócios - ajuda de Admin](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |
   
## <a name="related-topics"></a>Tópicos relacionados
[Perguntas comuns sobre a transferência de números de telefone](/microsoftteams/transferring-phone-numbers-common-questions)

[Diferentes tipos de números de telefone usados para Planos de Chamadas](/MicrosoftTeams/different-kinds-of-phone-numbers-used-for-calling-plans)

[Gerenciar os números de telefone de sua organização](/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)

[Termos e condições das Chamadas de Emergência](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype for Business Online: etiqueta de aviso de isenção de responsabilidade por Chamadas de Emergência](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 