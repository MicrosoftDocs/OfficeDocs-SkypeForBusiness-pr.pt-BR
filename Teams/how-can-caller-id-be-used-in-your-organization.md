---
title: Como a identificação de chamadas pode ser usada em sua organização
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.assetid: 5a0bd8ba-3334-46ee-becf-1025597737f6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
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
- ms.teamsadmincenter.voice.callerid.overview
description: A ID do chamador pode ser controlada para chamadas de entrada e de saída para usuários do Sistema de Telefonia usando uma política chamada CallingLineIdentity.
ms.openlocfilehash: e723311b2780dd1d43bad4874b72133e09ff4fc3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120672"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a>Como a identificação de chamadas pode ser usada em sua organização

A ID do chamador pode ser controlada para chamadas de entrada e de saída para usuários do Sistema de Telefonia usando uma política chamada CallingLineIdentity.
  
A funcionalidade de ID do chamador está disponível para todos os usuários do Sistema de Telefonia, independentemente da conectividade PSTN:

- Planos de Chamada da Microsoft 

- Roteamento Direto do Sistema de Telefonia 
  
- Conectividade PSTN Online
    
- Conectividade PSTN local com o Skype for Business Cloud Connector Edition (exige o Cloud Connector Edition 1.4.2 e posterior)
    
- Conectividade PSTN local com o Skype for Business Server (exige o Skype for Business Server 2015 CU5 e posterior)
    
> [!NOTE]
> [!OBSERVAçãO] Esta política não está disponível no Skype for Business 2015 Server. 
  
## <a name="outbound-caller-id"></a>Identificação de chamada de saída

Há três opções disponíveis para a ID do chamador PSTN de saída:
  
- O número de telefone atribuído ao usuário, que é o padrão.
    
- Um número de telefone que é classificado como um *número de* *serviço* e de chamada gratuita no inventário de números de telefone de Planos de Chamadas. Geralmente é atribuído a um atendente automático da organização ou a uma fila de chamadas.
    
- Definido como anônimo.
    
No entanto, você não pode atribuir esses tipos de números de telefone para identificação de chamada de saída:
  
- Todos os números de telefone que são classificados como um  *usuário no*  inventário de números de telefone de Planos de Chamadas
    
- Um número de telefone local do Skype for Business Server
    
Para definir a identificação de chamada de saída, consulte [Definir a identificação de chamadas para um usuário](./set-the-caller-id-for-a-user.md).
  
### <a name="end-user-control-of-outbound-caller-id"></a>Controle do usuário final da ID do chamador de saída

O atributo EnableUserOverride permite que usuários individuais ou múltiplos alterem a configuração de ID do chamador para **Anonymous**. Isso é aplicável apenas quando uma política CallingLineIdentity é configurada com um parâmetro CallingIDSubstitute da LineURI ou Substitute. O valor padrão do EnableUserOverride é False.
  
Os usuários finais podem definir a ID  do chamador como **Anônimo** usando a guia Configurações no cliente da área de trabalho do Skype for Business, selecione Chamar um Usuário **Final** (se habilitado pelo administrador) e selecione **Ocultar** meu número de telefone e informações de perfil para todas as chamadas . No Teams, os usuários podem ir para a imagem de perfil no canto superior direito, selecionar Configurações Chamadas e, em Seguida, em  >   **ID** do Chamador, selecione Ocultar meu número de telefone e informações de perfil para todas as **chamadas**.
  
||||
|:-----|:-----|:-----|
|**Windows** <br/> |**Versão** <br/> |**Compatível** <br/> |
|Clique para Executar  <br/> |CC (Current Channel) lançado em 6 de dezembro de 2016 - versão 1611 (Compilação 7571.2072)  <br/> |Sim  <br/> |
|Clique para Executar  <br/> |CC (Current Channel) lançado em 22 de fevereiro de 2017 - versão 1701 (Compilação 7766.2060)  <br/> |Sim  <br/> |
|Clique para Executar  <br/> |Canal Adiado lançado em 13 de junho de 2017 - versão 1701 (Compilação 7766.2092)  <br/> |Sim  <br/> |
|MSI  <br/> |Skype for Business  <br/> |Não  <br/> |
|Mac  <br/> |Skype for Business  <br/> |Não  <br/> |
   
## <a name="inbound-caller-id"></a>ID do chamador de entrada

O Sistema de Telefonia mostrará a ID chamada para um número de telefone externo se o número estiver associado a um usuário no Azure AD. Se o número de telefone não estiver no Azure AD, o nome de exibição fornecido por telco será mostrado se ele estiver disponível.

O atributo BlockIncomingCallerID permite o bloqueio da identificação de chamada nas chamadas PSTN de entrada. Você pode definir esse atributo, mas ele não está disponível para os usuários finais na página de configurações do usuário. E ele está disponível atualmente apenas com a conectividade PSTN Online.
  
Para definir a identificação de chamada de saída, consulte [Definir a identificação de chamadas para um usuário](./set-the-caller-id-for-a-user.md).
  
## <a name="related-topics"></a>Tópicos relacionados
[Perguntas comuns sobre a transferência de números de telefone](./phone-number-calling-plans/port-order-overview.md)

[Diferentes tipos de números de telefone usados para Planos de Chamadas](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Gerenciar os números de telefone de sua organização](/microsoftteams/manage-phone-numbers-for-your-organization)

[Termos e condições das Chamadas de Emergência](./emergency-calling-terms-and-conditions.md)

[Skype for Business Online: etiqueta de aviso de isenção de responsabilidade por Chamadas de Emergência](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
