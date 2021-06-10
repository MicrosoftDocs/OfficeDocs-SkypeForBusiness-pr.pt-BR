---
title: Quantos números de telefone você consegue obter?
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: conceptual
ms.assetid: 61dfb27c-5bfa-4481-a930-9c026e73ff3a
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- ms.teamsadmincenter.voice.phonenumbers.searchacquire.tooltip.quantity
- seo-marvel-mar2020
description: Saiba mais sobre quantos números de telefone você pode obter Microsoft Teams com base no tipo de número e quantas licenças você tem.
ms.openlocfilehash: ecd3eacc978d81bddc67b64b9e2480bba950aa1f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092219"
---
# <a name="how-many-phone-numbers-can-you-get"></a>Quantos números de telefone você consegue obter?

Ao procurar e obter números de telefone para a sua organização, é possível obter mais números de telefone do que a quantidade de licenças atribuídas. Mas isso depende dos tipos de números de telefone e de licenças que você comprou e atribuiu. Você pode clicar [em Diferentes tipos](different-kinds-of-phone-numbers-used-for-calling-plans.md) de números de telefone usados para Planos de Chamadas para descobrir sobre os diferentes números de telefone usados em Microsoft Teams.
  
Você pode ver o número de números  de telefone que você pode obter na página Obter números de telefone no centro de administração Microsoft Teams ou pode executar o cmdlet [Get-CsOnlineTelephoneNumberAvailableCount.](/powershell/module/skype/Get-CsOnlineTelephoneNumberAvailableCount)
  
> [!IMPORTANT]
> [!IMPORTANTE] Os limites abaixo não incluem números de telefone que você fez portabilidade ou transferiu para a Microsoft. 
  
## <a name="how-many-phone-numbers-you-can-get"></a>Quantos números de telefone você pode obter?

||||
|:-----|:-----|:-----|
|**Para este tipo de número de telefone** <br/> |**Como calcular o total de números de telefone?** <br/> |**Veja um exemplo** <br/> |
|Número de usuário (assinante)  <br/> |O número de números de telefone  é igual ao  número total de licenças do Plano de Chamadas Domésticas e/ou do Plano de Chamadas Domésticos e Internacionais multiplicado por 1,1 + 10 números de telefone adicionais. <br/> |Se eu tiver 50 usuários no total com um Plano de Chamadas Domésticas e/ou Plano de Chamadas Domésticas e Internacionais, você poderá adquirir **65** números de telefone **(50 x 1,1 + 10)**. <br/> |
|Número do serviço de chamada tarifada  <br/> | O número de números de telefone  é igual ao número total de licenças de Sistema de Telefonia **e audioconferência** e usa o seguinte: <br/>  Se houver **1 a 25 licenças**, serão fornecidos **5** números de telefone. <br/>  Se houver **26 a 49 licenças**, serão fornecidos **10** números de telefone. <br/>  Se houver **50 a 99 licenças,** serão dados **20** números de telefone. <br/>  Se houver **100 a 149 licenças**, serão fornecidos **30** números de telefone. <br/>  Se houver **150 a 199 licenças**, serão fornecidos **40** números de telefone. <br/>  Se houver **200 a 499 licenças**, serão fornecidos **65** números de telefone. <br/>  Se houver **500 a 749 licenças**, serão fornecidos **90** números de telefone. <br/>  Se houver **750 a 999 licenças**, serão fornecidos **110** números de telefone. <br/>  Se houver **1.000 a 1.249 licenças**, serão fornecidos **125** números de telefone. <br/>  Se houver **1.250 a 1.499 licenças,** serão dados **135** números de telefone. <br/>  Se houver **1.500 a 1.999 licenças**, serão fornecidos **160** números de telefone. <br/>  Se houver **2.000 a 2.999 licenças**, serão fornecidos **210** números de telefone. <br/>  Se houver **3.000 a 6.999 licenças**, serão fornecidos **420** números de telefone. <br/>  Se houver **7.000 a 9.999 licenças**, serão fornecidos **500** números de telefone.%+% <br/>  Se houver **10.000 a 14.999 licenças**, serão fornecidos **600** números de telefone. <br/>  Se houver **15.000 a 19.999 licenças**, serão fornecidos **700** números de telefone.%+% <br/>  Se houver **20.000 a 49.999 licenças**, serão fornecidos **1.000** números de telefone. <br/>  Se houver **mais de 50.000 licenças**, serão fornecidos **1.500** números de telefone. <br/> |Se você tiver um total **de 51**  licenças de Sistema de Telefonia e **Audioconferência,** poderá obter **20** números de serviço de tarifação. <br/> |
|Número do serviço de chamada gratuita  <br/> | O número de números de telefone  é igual ao número total de licenças de Sistema de Telefonia **e audioconferência** e usa o seguinte: <br/>  Se houver **1 a 25 licenças**, serão fornecidos **5** números de telefone. <br/>  Se houver **26 a 49 licenças**, serão fornecidos **10** números de telefone. <br/>  Se houver **50 a 99 licenças,** serão dados **20** números de telefone. <br/>  Se houver **100 a 149 licenças**, serão fornecidos **30** números de telefone. <br/>  Se houver **150 a 199 licenças**, serão fornecidos **40** números de telefone. <br/>  Se houver **200 a 499 licenças**, serão fornecidos **65** números de telefone. <br/>  Se houver **500 a 749 licenças**, serão fornecidos **90** números de telefone. <br/>  Se houver **750 a 999 licenças**, serão fornecidos **110** números de telefone. <br/>  Se houver **1.000 a 1.249 licenças**, serão fornecidos **125** números de telefone. <br/>  Se houver **1.250 a 1.499 licenças,** serão dados **135** números de telefone. <br/>  Se houver **1.500 a 1.999 licenças**, serão fornecidos **160** números de telefone. <br/>  Se houver **2.000 a 2.999 licenças**, serão fornecidos **210** números de telefone. <br/>  Se houver **3.000 a 6.999 licenças**, serão fornecidos **420** números de telefone. <br/>  Se houver **7.000 a 9.999 licenças**, serão fornecidos **500** números de telefone.%+% <br/>  Se houver **10.000 a 14.999 licenças**, serão fornecidos **600** números de telefone. <br/>  Se houver **15.000 a 19.999 licenças**, serão fornecidos **700** números de telefone.%+% <br/>  Se houver **20.000 a 49.999 licenças**, serão fornecidos **1.000** números de telefone. <br/>  Se houver **mais de 50.000 licenças**, serão fornecidos **1.500** números de telefone. <br/> |Se você tiver um total de **1.001**  licenças de Sistema de Telefonia e **Audioconferência,** poderá obter **125** números de serviço gratuitos. <br/> <br/> **Importante:** [a cobrança de Créditos de](set-up-communications-credits-for-your-organization.md) Comunicações é necessária para reservar e usar números de telefone gratuitos.          |
   
> [!NOTE]
> Se precisar de mais números de telefone, veja [Contatar o suporte de produtos para empresas - Ajuda para administradores](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).
  
## <a name="related-topics"></a>Tópicos relacionados
[Perguntas comuns sobre a transferência de números de telefone](./phone-number-calling-plans/port-order-overview.md)

[Diferentes tipos de números de telefone usados para Planos de Chamadas](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Gerenciar os números de telefone de sua organização](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[Termos e condições das Chamadas de Emergência](emergency-calling-terms-and-conditions.md)

[Rótulo de aviso de isenção de responsabilidade de chamada de emergência](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
