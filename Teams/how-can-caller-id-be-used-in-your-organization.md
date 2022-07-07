---
title: Como a identificação de chamadas pode ser usada em sua organização
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: jens, roykuntz
ms.topic: article
ms.assetid: 5a0bd8ba-3334-46ee-becf-1025597737f6
ms.tgt.pltfrm: cloud
search.appverid: MET150
ms.collection:
- M365-voice
ms.service: msteams
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- ms.teamsadmincenter.voice.callerid.overview
description: A ID do chamador pode ser controlada para chamadas de entrada e saída para usuários do Sistema de Telefonia usando uma política chamada CallingLineIdentity.
ms.openlocfilehash: 250f8a1a516aec4c9941b0c6396e6d44771b4f53
ms.sourcegitcommit: f608811288c82a6348a6af1671246a93ed06e578
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2022
ms.locfileid: "66660957"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a>Como a identificação de chamadas pode ser usada em sua organização

A ID do chamador consiste em duas informações voltadas para o usuário:

- Um número de telefone (conhecido como CLID ou ID de linha de chamada). Este é o número PSTN (Rede Telefônica Pública Comunada) apresentado como a identificação do chamador.

- Um nome de parte de chamada (normalmente conhecido como CNAM). 
  
A funcionalidade de ID do chamador está disponível para todos os usuários do Sistema de Telefonia, independentemente da opção de conectividade [PSTN](pstn-connectivity.md): Plano de Chamada da Microsoft, Conexão de Operador ou Roteamento Direto. 
  
Você pode controlar a ID do Chamador para chamadas de entrada e saída usando uma política chamada CallingLineIdentity. Para obter mais informações, consulte [Mais sobre a ID de linha de chamada e o nome da parte de chamada](more-about-calling-line-id-and-calling-party-name.md).

  
## <a name="outbound-pstn-caller-id"></a>ID do chamador PSTN de saída

Para a ID do chamador PSTN de saída, as opções a seguir estão disponíveis. 
  
- O número de telefone atribuído ao usuário, que é o padrão.

- Anônimo, que está disponível removendo a apresentação do número PSTN do usuário. 

- Um número de telefone substituto, que pode ser:

  - Um número de telefone que é classificado como um serviço e número de chamada gratuita no inventário de números de telefone dos Planos de Chamadas. Ele é atribuído a um Atendedor Automático do Teams ou Fila de Chamadas.

  - Um número de telefone local por meio do Roteamento Direto atribuído a uma conta de recurso usada por um Atendedor Automático ou Fila de Chamadas do Teams. 

- O Nome da Parte de Chamada ou CNAM definido na chamada PSTN de saída.  
    
Para obter mais informações, consulte [Definir a ID do Chamador para um usuário](./set-the-caller-id-for-a-user.md).
  
### <a name="end-user-control-of-outbound-caller-id"></a>Controle do usuário final da ID do chamador de saída

Os usuários podem alterar a configuração de ID do chamador **para Anônimo** definindo o atributo EnableUserOverride. 

Se a ID do chamador de saída estiver definida como Anônima, EnableUserOverride não terá efeito e a ID do chamador sempre será definida como Anônima. O valor padrão do EnableUserOverride é False.

Os usuários finais podem definir a ID do chamador como Anônima acessando Configurações **> Chamadas** e, em Seguida, em **ID** do Chamador, selecione Ocultar meu número de telefone e informações de perfil para todas as **chamadas.** Leva alguns minutos para que essa alteração de configuração reflita em novas chamadas. 

### <a name="notes"></a>Observações

Considere o seguinte:

- Você não pode atribuir os seguintes tipos de números de telefone para a ID do chamador de saída:

  - Todos os números de telefone classificados como um usuário no inventário de números de telefone dos Planos de Chamadas.

  - Qualquer número de telefone local por meio do Roteamento Direto atribuído a um usuário.

  - Um Skype for Business Server número de telefone local.

- O uso da substituição de número de telefone da conta de recurso funciona para usuários do Teams. A substituição do número de telefone de serviço funciona para usuários do Teams.

- O Nome da Parte de Chamada é enviado em chamadas em que a ID do chamador é substituída por LineUri, um número de telefone de conta de serviço ou recurso e quando o chamador é um usuário do Teams.

- O Nome da Parte de Chamada pode ter no máximo 200 caracteres, mas os sistemas downstream podem dar suporte a menos caracteres.

- Para Roteamento Direto, a substituição de número de telefone e o Nome da Parte de Chamada são enviados no cabeçalho FROM SIP. Se o OnlinePstnGateway correspondente estiver configurado com ForwardPai = True, o cabeçalho SIP P-ASSERTED-IDENTITY conterá o usuário de chamada real.

- EnableUserOverride tem precedência sobre outras configurações na política, a menos que a substituição seja definida como Anônima. Por exemplo, suponha que a instância de política tenha substituição usando uma conta de recurso e EnableUserOverride seja definida e habilitada pelo usuário. Nesse caso, a ID do chamador de saída será bloqueada e Anônimo será usado. Se uma instância de política tiver a substituição definida como Anônima e EnableUserOverride estiver definida, a ID do chamador de saída sempre será Anônima, independentemente da configuração do usuário final.

   
## <a name="inbound-caller-id"></a>ID do chamador de entrada

O Sistema de Telefonia mostra o número de telefone externo de entrada como a ID do chamador. Se o número estiver associado a um usuário ou contato no Azure AD ou em um contato pessoal, os clientes do Skype for Business e do Teams mostrarão a ID do chamador com base nas informações. Se o número de telefone não estiver Azure AD ou um contato pessoal, o nome de exibição fornecido pelo telco será mostrado se ele estiver disponível.

O atributo BlockIncomingCallerID permite o bloqueio da identificação de chamada nas chamadas PSTN de entrada. Você pode definir esse atributo, mas ele não está disponível para os usuários finais na página de configurações do usuário. Quando essa configuração está habilitada, o chamador PSTN de entrada é exibido como proveniente de Anônimo.
  
Para bloquear a ID do chamador de entrada, consulte [Definir a ID do Chamador para um usuário](./set-the-caller-id-for-a-user.md).
  
## <a name="related-topics"></a>Tópicos relacionados
[Perguntas comuns sobre a transferência de números de telefone](./phone-number-calling-plans/port-order-overview.md)

[Diferentes tipos de números de telefone usados para Planos de Chamadas](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Gerenciar os números de telefone de sua organização](/microsoftteams/manage-phone-numbers-for-your-organization)

[Termos e condições das Chamadas de Emergência](./emergency-calling-terms-and-conditions.md)

[Skype for Business Online: Rótulo de aviso de isenção de responsabilidade de chamadas de emergência](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
