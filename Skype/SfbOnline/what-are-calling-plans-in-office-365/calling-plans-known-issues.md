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
f1.keywords:
- NOCSH
ms.custom:
- Calling Plans
description: Conheça problemas conhecidos com o plano de chamada para Chamada PSTN e o que você pode fazer sobre eles.
ms.openlocfilehash: 3a97057f61c154ded83b85becbfcf53dc2b4bc78
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220731"
---
# <a name="calling-plans-known-issues"></a>Problemas conhecidos dos planos de chamadas

Planos de Chamadas são um novo recurso encontrado no Skype for Business Online. A seguir estão os problemas atuais que estão sendo acompanhados e investigados ativamente. Eles serão potencialmente resolvidos quando o recurso for atualizado em builds futuras.
  
## <a name="calling-plans-known-issues"></a>Problemas conhecidos dos planos de chamadas

|**Problema conhecido**|**Comentários**|
|:-----|:-----|
|A transição de licenças do Tech Preview para licenças de produção para Planos de Chamada não atualiza automaticamente a licença.  <br/> |Primeiramente, compre suas novas licenças para que estejam prontas para serem atribuídas aos seus usuários. Remova a licença promocional (Tech Preview)  de um  usuário e atribua imediatamente as novas licenças do Plano de Chamadas Domésticas e/ou Domésticas e Internacionais ao usuário.  <br/> Se você estiver removendo e adicionando licenças para vários usuários, é extremamente importante remover as licenças de todos os usuários usando o Windows PowerShell e depois atribuir **IMEDIATAMENTE** as licenças a todos os usuários também usando o Windows PowerShell. Isso garantirá que não haja interrupção no serviço ao lidar com grandes volumes de atribuições de licenças de usuário. Para ver exemplos de scripts do PowerShell, consulte [Atribuir licenças do Skype for Business e do Microsoft Teams.](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)  <br/> **Observação:** Se estiver usando a conectividade PSTN local para  usuários híbridos, você só precisará atribuir uma licença do **Sistema de** Telefonia. VOCÊ TAMBÉM **NÃO deve** atribuir um Plano de Chamada de Voz. No entanto, se você estiver habilitando planos de chamada no Microsoft 365 ou no Office 365 para  usuários que estão  no Microsoft 365 ou no Office 365, ainda precisará atribuir um Plano de Chamada Doméstica ou uma licença de Plano de Chamada Doméstica e Internacional para esses usuários. Consulte [Atribuir licenças do Skype for Business e do Microsoft Teams.](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)

> [!NOTE]
> Se você precisar obter mais números de telefone do que esse, entre em contato com o suporte para produtos [de negócios – Ajuda para Administradores](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)         |
   
## <a name="related-topics"></a>Tópicos relacionados
[Perguntas comuns sobre a transferência de números de telefone](/microsoftteams/transferring-phone-numbers-common-questions)

[Diferentes tipos de números de telefone usados para Planos de Chamadas](/MicrosoftTeams/different-kinds-of-phone-numbers-used-for-calling-plans)

[Gerenciar os números de telefone de sua organização](/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)

[Termos e condições das Chamadas de Emergência](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype for Business Online: etiqueta de aviso de isenção de responsabilidade por Chamadas de Emergência](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 
