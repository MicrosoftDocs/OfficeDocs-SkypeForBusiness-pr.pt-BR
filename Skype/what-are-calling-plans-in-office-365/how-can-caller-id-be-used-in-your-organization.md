---
title: "Como a identificação de chamadas pode ser usada em sua organização"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 5a0bd8ba-3334-46ee-becf-1025597737f6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Calling Plans
- Strat_SB_PSTN
description: "ID do chamador pode ser controlado para chamadas de entrada e saídas dos usuários de sistema telefônico usando uma política denominada CallingLineIdentity."
ms.openlocfilehash: b9e889ae9d87277939e844eeb911834f466942c5
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/15/2017
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a>Como a identificação de chamadas pode ser usada em sua organização

ID do chamador pode ser controlado para chamadas de entrada e saídas dos usuários de sistema telefônico usando uma política denominada CallingLineIdentity.
  
A funcionalidade de ID do chamador está disponível para todos os usuários de sistema telefônico, independentemente de conectividade PSTN:
  
- Conectividade PSTN Online
    
- Conectividade PSTN local com o Skype for Business Cloud Connector Edition (exige o Cloud Connector Edition 1.4.2 e posterior)
    
- Conectividade PSTN local com o Skype for Business Server (exige o Skype for Business Server 2015 CU5 e posterior)
    
> [!NOTE]
> [!OBSERVAçãO] Esta política não está disponível no Skype for Business 2015 Server. 
  
## <a name="outbound-caller-id"></a>Identificação de chamada de saída

Existem três opções disponíveis para a identificação de chamada PSTN de saída:
  
- O número de telefone atribuído ao usuário, que é o padrão.
    
- Inventário de número em um número de telefone que é classificado como um *serviço* e número de *chamada gratuita* em seus planos chamar no telefone do Office 365. Geralmente, ela é atribuída a uma fila de chamada e atendente automático organizacional.
    
- Definido como anônimo.
    
No entanto, você não pode atribuir esses tipos de números de telefone para identificação de chamada de saída:
  
- Inventário de número de qualquer números de telefone que são classificados como um *usuário* no seu telefone de planos de chamada
    
- Um número de telefone local do Skype for Business Server
    
Para definir a identificação de chamada de saída, consulte [Definir a identificação de chamadas para um usuário](set-the-caller-id-for-a-user.md).
  
### <a name="end-user-control-of-outbound-caller-id"></a>Controle de usuário final de identificação de chamada de saída

O atributo EnableUserOverride permite que um ou vários usuários alterem sua configuração de ID de chamador como **anônimo**. Isso se aplica apenas quando uma política de CallingLineIdentity é configurada com um parâmetro de CallingIDSubstitute de LineURI ou substituto. O valor padrão de EnableUserOverride é False.
  
Os usuários finais pode definir sua ID de chamador como **anônimo** usando a guia **Chamada encaminhar configurações** no Skype para o cliente de desktop de negócios.
  
||||
|:-----|:-----|:-----|
|**Windows** <br/> |**Versão** <br/> |**Compatível** <br/> |
|Clique para Executar  <br/> |CC (Current Channel) lançado em 6 de dezembro de 2016 - versão 1611 (Compilação 7571.2072)  <br/> |Sim  <br/> |
|Clique para Executar  <br/> |CC (Current Channel) lançado em 22 de fevereiro de 2017 - versão 1701 (Compilação 7766.2060)  <br/> |Sim  <br/> |
|Clique para Executar  <br/> |Adiada canal lançada em 13 de junho de 2017 - versão 1701 (Build 7766.2092)  <br/> |Sim  <br/> |
|MSI  <br/> |Skype for Business  <br/> |Não  <br/> |
|Mac  <br/> |Skype for Business  <br/> |Não  <br/> |
   
## <a name="inbound-caller-id"></a>Identificação de chamada de entrada

O atributo BlockIncomingCallerID permite bloquear a ID de chamador nas chamadas PSTN de entrada. Você pode definir esse atributo, mas ele não está disponível para seus usuários finais na página de configurações do usuário. E está atualmente disponível apenas com conectividade PSTN Online.
  
Para definir a identificação de chamada de saída, consulte [Definir a identificação de chamadas para um usuário](set-the-caller-id-for-a-user.md).
  
## <a name="related-topics"></a>Tópicos relacionados
[Transferindo perguntas comuns de números de telefone](transferring-phone-numbers-common-questions.md)

[Diferentes tipos de números de telefone usados para planos de chamada](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Gerenciar números de telefone para sua organização](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[Termos e condições para chamadas de emergência](emergency-calling-terms-and-conditions.md)

[Skype for Business Online: Rótulo de aviso de isenção de responsabilidade de chamadas de emergência](https://go.microsoft.com/fwlink/?LinkID=692099)