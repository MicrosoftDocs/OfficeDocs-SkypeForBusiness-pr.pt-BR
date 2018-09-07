---
title: Como a identificação de chamadas pode ser usada em sua organização
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.assetid: 5a0bd8ba-3334-46ee-becf-1025597737f6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Calling Plans
description: A identificação de chamadas pode ser controlada para chamadas de entrada e saída para usuários do Sistema de Telefonia usando uma política chamada CallingLineIdentity.
ms.openlocfilehash: 410712a8fd0a6f28b0bc2821daae8143b38ceb63
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23854221"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a>Como a identificação de chamadas pode ser usada em sua organização

A identificação de chamadas pode ser controlada para chamadas de entrada e saída para usuários do Sistema de Telefonia usando uma política chamada CallingLineIdentity.
  
A funcionalidade de identificação de chamadas está disponível para todos os usuários do Sistema de Telefonia, independentemente da conectividade PSTN:
  
- Conectividade PSTN Online
    
- Conectividade PSTN local com o Skype for Business Cloud Connector Edition (exige o Cloud Connector Edition 1.4.2 e posterior)
    
- Conectividade PSTN local com o Skype for Business Server (exige o Skype for Business Server 2015 CU5 e posterior)
    
> [!NOTE]
> [!OBSERVAçãO] Esta política não está disponível no Skype for Business 2015 Server. 
  
## <a name="outbound-caller-id"></a>Identificação de chamada de saída

Existem três opções disponíveis para a identificação de chamada PSTN de saída:
  
- O número de telefone atribuído ao usuário, que é o padrão.
    
- Um número de telefone que é classificado como um *serviço* e número de *chamada gratuita* em seus Planos de Chamada no inventário de números de telefono do Office 365. Geralmente é atribuído a um atendente automático da organização ou a uma fila de chamadas.
    
- Definido como anônimo.
    
No entanto, você não pode atribuir esses tipos de números de telefone para identificação de chamadas de saída:
  
- Quaisquer números de telefone que são classificados como um  *usuário*  em seu estoque de números de telefone de Planos de Chamada.
    
- Um número de telefone local do Skype for Business Server
    
Para definir a identificação de chamada de saída, consulte [Definir a identificação de chamadas para um usuário](set-the-caller-id-for-a-user.md).
  
### <a name="end-user-control-of-outbound-caller-id"></a>Controle de usuário final de identificação de chamada de saída

O atributo EnableUserOverride permite que um único ou vários usuários alterem a configuração da identificação de chamadas para **Anônimo**. Isso é aplicável apenas quando uma política CallingLineIdentity é configurada com um parâmetro CallingIDSubstitute da LineURI ou Substitute. O valor padrão do EnableUserOverride é False.
  
Os usuários finais podem definir a identificação de chamada como **Anônimo** usando a guia **Configurações de Encaminhamento de Chamadas** no cliente desktop do Skype for Business.
  
||||
|:-----|:-----|:-----|
|**Windows** <br/> |**Versão** <br/> |**Compatível** <br/> |
|Clique para Executar  <br/> |CC (Current Channel) lançado em 6 de dezembro de 2016 - versão 1611 (Compilação 7571.2072)  <br/> |Sim  <br/> |
|Clique para Executar  <br/> |CC (Current Channel) lançado em 22 de fevereiro de 2017 - versão 1701 (Compilação 7766.2060)  <br/> |Sim  <br/> |
|Click-to-Run  <br/> |Canal Adiado lançado em 13 de junho de 2017 - versão 1701 (Compilação 7766.2092)  <br/> |Sim  <br/> |
|MSI  <br/> |Skype for Business  <br/> |Não  <br/> |
|Mac  <br/> |Skype for Business  <br/> |Não  <br/> |
   
## <a name="inbound-caller-id"></a>Identificação de chamadas de entrada

O atributo BlockIncomingCallerID permite o bloqueio da identificação de chamadas nas chamadas de entrada PSTN. Você pode definir esse atributo, mas ele não está disponível para seus usuários finais na página de configurações do usuário. E está atualmente disponível apenas com conectividade PSTN Online.
  
Para definir a identificação de chamadas de saída, consulte [Definir a identificação de chamadas para um usuário](set-the-caller-id-for-a-user.md).
  
## <a name="related-topics"></a>Tópicos relacionados
[Perguntas comuns sobre a transferência de números de telefone](/microsoftteams/transferring-phone-numbers-common-questions)

[Diferentes tipos de números de telefone usados para Planos de Chamadas](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[Gerenciar os números de telefone de sua organização](/microsoftteams/manage-phone-numbers-for-your-organization)

[Termos e condições das Chamadas de Emergência](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype for Business Online: etiqueta de aviso de isenção de responsabilidade por Chamadas de Emergência](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 