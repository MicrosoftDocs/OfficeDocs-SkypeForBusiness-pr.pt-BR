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
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Calling Plans
description: Saiba os problemas conhecidos com o plano de chamada para Chamada PSTN e o que você pode fazer sobre eles.
ms.openlocfilehash: f118f6107887dae00f640a15bcef625f91079bcc
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58624463"
---
# <a name="calling-plans-known-issues"></a>Problemas conhecidos dos planos de chamadas

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Planos de chamada são um novo recurso encontrado no Skype for Business Online. A seguir estão os problemas atuais que estão sendo acompanhados e investigados ativamente. Eles serão potencialmente resolvidos quando o recurso for atualizado em builds futuras.
  
## <a name="calling-plans-known-issues"></a>Problemas conhecidos dos planos de chamadas

|**Problema conhecido**|**Comentários**|
|:-----|:-----|
|A transição de licenças do Tech Preview para licenças de produção para Planos de Chamada não atualiza automaticamente a licença.  <br/> |Primeiramente, compre suas novas licenças para que estejam prontas para serem atribuídas aos seus usuários. Remova a licença promocional (Visualização técnica) de  um usuário e  atribua imediatamente as novas licenças do Plano de Chamadas Domésticas e/ou Domésticas e Internacionais ao usuário.  <br/> Se você estiver removendo e adicionando licenças para vários usuários, é extremamente importante remover as licenças de todos os usuários usando o Windows PowerShell e depois atribuir **IMEDIATAMENTE** as licenças a todos os usuários também usando o Windows PowerShell. Isso garantirá que não haja interrupção no serviço ao lidar com grandes volumes de atribuições de licença de usuário. Para exemplo de scripts do PowerShell, consulte [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).  <br/> **Observação:** Se você estiver usando a conectividade PSTN local  para usuários híbridos, só precisará atribuir uma licença Sistema de Telefonia **local.** VOCÊ TAMBÉM **NÃO deve** atribuir um Plano de Chamada de Voz. No entanto, se você estiver habilitando Planos de Chamada no Microsoft 365 ou Office 365 para usuários que estão  no Microsoft 365 ou  no Office 365, você ainda precisará atribuir um Plano de Chamada Doméstica ou uma licença de Plano de Chamada Doméstica e Internacional para esses usuários. Consulte [Atribuir Skype for Business e Microsoft Teams licenças](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).

> [!NOTE]
> Se você precisar obter mais números de telefone do que isso, entre em contato com o suporte para produtos de [negócios - Ajuda do administrador](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |
   
## <a name="related-topics"></a>Tópicos relacionados
[Perguntas comuns sobre a transferência de números de telefone](/microsoftteams/transferring-phone-numbers-common-questions)

[Diferentes tipos de números de telefone usados para Planos de Chamadas](/MicrosoftTeams/different-kinds-of-phone-numbers-used-for-calling-plans)

[Gerenciar os números de telefone de sua organização](/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)

[Termos e condições das Chamadas de Emergência](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype for Business Online: etiqueta de aviso de isenção de responsabilidade por Chamadas de Emergência](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 
