---
title: Como a identificação de chamadas pode ser usada em sua organização
author: CarolynRowe
ms.author: crowe
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
description: A identificação de chamadas pode ser controlada para chamadas de entrada e de saída para usuários do sistema telefônico usando uma política chamada CallingLineIdentity.
ms.openlocfilehash: 2547e6ca3aed10d112897aa1b24900a479c5c8ef
ms.sourcegitcommit: a7c823f61d9ab88424bad924113d780ce11e509f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44224204"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a>Como a identificação de chamadas pode ser usada em sua organização

A identificação de chamadas pode ser controlada para chamadas de entrada e de saída para usuários do sistema telefônico usando uma política chamada CallingLineIdentity.
  
A funcionalidade de identificação de chamadas está disponível para todos os usuários do sistema telefônico independentemente da conectividade PSTN:
  
- Conectividade PSTN Online
    
- Conectividade PSTN local com o Skype for Business Cloud Connector Edition (exige o Cloud Connector Edition 1.4.2 e posterior)
    
- Conectividade PSTN local com o Skype for Business Server (exige o Skype for Business Server 2015 CU5 e posterior)
    
> [!NOTE]
> [!OBSERVAçãO] Esta política não está disponível no Skype for Business 2015 Server. 
  
## <a name="outbound-caller-id"></a>Identificação de chamada de saída

Há três opções disponíveis para a identificação de chamadas PSTN de saída:
  
- O número de telefone atribuído ao usuário, que é o padrão.
    
- A telephone number that is classified as a *service* and *toll-free* number in your Calling Plans in Office 365 telephone number inventory. It is usually assigned to an organizational auto attendant or call queue.
    
- Definido como anônimo.
    
No entanto, você não pode atribuir esses tipos de números de telefone para identificação de chamada de saída:
  
- Qualquer número de telefone classificado como um *usuário* em seu plano de número de telefone de planos de chamadas
    
- Um número de telefone local do Skype for Business Server
    
Para definir a identificação de chamada de saída, consulte [Definir a identificação de chamadas para um usuário](/microsoftteams/set-the-caller-id-for-a-user).
  
### <a name="end-user-control-of-outbound-caller-id"></a>Controle do usuário final da identificação de chamadas de saída

O atributo EnableUserOverride permite que um ou vários usuários alterem a configuração de identificação de chamadas para **anônima**. Isso só se aplica quando uma política CallingLineIdentity é configurada com um parâmetro CallingIDSubstitute de LineURI ou substituto. O valor padrão de EnableUserOverride é false.
  
Seus usuários finais podem definir a identificação de chamadas como **anônimas** usando a guia **configurações** no cliente da área de trabalho do Skype for Business, selecione **chamadas para um usuário final** (se habilitada por administrador) e selecione **ocultar meu número de telefone e informações de perfil para todas as chamadas**. No Teams, os usuários podem acessar a imagem do perfil no canto superior direito, selecionar **configurações**  >  de**chamadas**e, em seguida, em **identificação de chamadas**, selecionar **ocultar meu número de telefone e informações de perfil para todas as chamadas**.
  
||||
|:-----|:-----|:-----|
|**Windows** <br/> |**Versão** <br/> |**Compatível** <br/> |
|Clique para Executar  <br/> |CC (Current Channel) lançado em 6 de dezembro de 2016 - versão 1611 (Compilação 7571.2072)  <br/> |Sim  <br/> |
|Clique para Executar  <br/> |CC (Current Channel) lançado em 22 de fevereiro de 2017 - versão 1701 (Compilação 7766.2060)  <br/> |Sim  <br/> |
|Clique para Executar  <br/> |Canal Adiado lançado em 13 de junho de 2017 - versão 1701 (Compilação 7766.2092)  <br/> |Sim  <br/> |
|MSI  <br/> |Skype for Business  <br/> |Não  <br/> |
|Mac  <br/> |Skype for Business  <br/> |Não  <br/> |
   
## <a name="inbound-caller-id"></a>IDENTIFICAÇÃO de chamada de entrada

O sistema de telefonia mostrará a ID chamada para um número de telefone externo se o número estiver associado a um usuário no Azure AD. Se o número de telefone não estiver no Azure AD, o nome de exibição fornecido pela Telco será exibido se estiver disponível.

O atributo BlockIncomingCallerID permite o bloqueio da identificação de chamada nas chamadas PSTN de entrada. Você pode definir esse atributo, mas ele não está disponível para os usuários finais na página Configurações do usuário. E ele está disponível atualmente apenas com a conectividade PSTN Online.
  
Para definir a identificação de chamada de saída, consulte [Definir a identificação de chamadas para um usuário](/microsoftteams/set-the-caller-id-for-a-user).
  
## <a name="related-topics"></a>Tópicos relacionados
[Perguntas comuns sobre a transferência de números de telefone](/microsoftteams/transferring-phone-numbers-common-questions)

[Diferentes tipos de números de telefone usados para Planos de Chamadas](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[Gerenciar os números de telefone de sua organização](/microsoftteams/manage-phone-numbers-for-your-organization)

[Termos e condições das Chamadas de Emergência](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype for Business Online: etiqueta de aviso de isenção de responsabilidade por Chamadas de Emergência](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 
