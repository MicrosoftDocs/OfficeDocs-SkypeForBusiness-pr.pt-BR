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
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: 'Learn known issues with the calling plan for Office 365 (PSTN Calling) and what you can do about them. '
ms.openlocfilehash: 9a6f97a93aa6c7b4e847ba1cb3280a21c473db0c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34299520"
---
# <a name="calling-plans-known-issues"></a>Problemas conhecidos dos planos de chamadas

Os planos de chamada no Office 365 são um novo recurso encontrado no Skype for Business online. Estes são os problemas atuais que estão sendo controlados e ativamente investigados. Eles serão potencialmente resolvidos quando o recurso for atualizado em futuras versões do Office 365 e do Skype for Business online.
  
## <a name="calling-plans-known-issues"></a>Problemas conhecidos dos planos de chamadas

|**Problema conhecido**|**Comentários**|
|:-----|:-----|
|A transição de licenças do Tech Preview para licenças de produção para planos de chamada não atualiza automaticamente a licença.  <br/> |Primeiramente, compre suas novas licenças para que estejam prontas para serem atribuídas aos seus usuários. Remova a licença promocional (visualização técnica) de um usuário e, em seguida, atribua **imediatamente** o novo **plano de chamadas domésticas** e/ou licenças de plano de **chamada domésticas e internacionais** ao usuário. <br/> Se você estiver removendo e adicionando licenças para vários usuários, é extremamente importante remover as licenças de todos os usuários usando o Windows PowerShell e depois atribuir **IMEDIATAMENTE** as licenças a todos os usuários também usando o Windows PowerShell. Isso garantirá que não haja interrupção no serviço ao manipular grandes volumes de atribuições de licença de usuário. Para os scripts de exemplo do PowerShell, consulte [atribuir licenças do Skype for Business e do Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).  <br/> **Observação:** Se você estiver usando a conectividade PSTN local para usuários híbridos, *só* precisará atribuir uma licença do **sistema telefônico** . Você também **não** deve atribuir um plano de chamada de voz. No entanto, se você estiver habilitando planos de chamada no Office 365 para usuários que estão no Office 365, você ainda precisará atribuir um **plano de chamadas domésticas** ou uma licença de **plano de chamadas doméstica e internacional** para esses usuários. Consulte [atribuir licenças do Skype for Business e do Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).

> [!NOTE]
> Se precisar de mais números de telefone, [entre em contato com o suporte para produtos de negócios-ajuda para administradores](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |
   
## <a name="related-topics"></a>Tópicos relacionados
[Perguntas comuns sobre a transferência de números de telefone](/microsoftteams/transferring-phone-numbers-common-questions)

[Diferentes tipos de números de telefone usados para Planos de Chamadas](/MicrosoftTeams/different-kinds-of-phone-numbers-used-for-calling-plans)

[Gerenciar os números de telefone de sua organização](/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)

[Termos e condições das Chamadas de Emergência](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype for Business Online: etiqueta de aviso de isenção de responsabilidade por Chamadas de Emergência](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 