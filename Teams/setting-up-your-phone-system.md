---
title: Configurar o Sistema de Telefonia na sua organização
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: makolomi
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-apr2020
description: Guia passo a passo detalhando como configurar o sistema de telefonia (Cloud PBX) para sua organização no Microsoft 365 ou no Office 365.
ms.openlocfilehash: 14a2fa971d32aeb7c0dca8200a72ad4895be4d44
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031377"
---
# <a name="set-up-phone-system-in-your-organization"></a>Configurar o sistema telefônico em sua organização

Veja a seguir um guia passo a passo para configurar o sistema telefônico no Microsoft 365 ou no Office 365. Links para informações adicionais e detalhadas estão disponíveis no final de cada etapa.

## <a name="step-1-make-sure-that-phone-system-is-available-in-your-country-or-region"></a>Etapa 1: Certifique-se de que o Sistema de Telefonia está disponível em seu país ou região

1.    Primeiro, acesse [Disponibilidade de Audioconferência e Planos de Chamadas por país e região](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) e selecione seu país ou região na lista na parte superior da página. 
2.    Em **Sistema de Telefonia** , examine a lista de recursos e detalhes. 
3.    Se o Sistema de Telefonia estiver disponível, vá para a etapa 2. 

## <a name="step-2-buy-and-assign-phone-system-and-calling-plan-licenses"></a>Etapa 2: Comprar e atribuir licenças do Sistema de Telefonia e Planos de Chamadas

Para atribuir uma licença do sistema telefônico e do plano de chamada a um único usuário, as etapas são as mesmas que atribuir uma licença do Microsoft 365 ou do Office 365.  Você também pode atribuir licenças a vários usuários em massa. Para obter mais informações, consulte [atribuir licenças de Complementos do Microsoft Teams](teams-add-on-licensing/assign-teams-add-on-licenses.md).

Se os planos de chamada não estiverem disponíveis para seu país ou região, considere o uso do roteamento direto para conectar sua infraestrutura de telefonia local ao sistema telefônico.  Para obter mais informações, consulte [Roteamento direto do sistema telefônico](direct-routing-landing-page.md).

## <a name="step-3-get-phone-numbers-for-your-users"></a>Etapa 3: obter números de telefone para seus usuários

Antes de configurar os usuários em sua organização para fazer e receber chamadas telefônicas, você deve obter números de telefone para eles.

Você tem três maneiras de obter números para seus usuários:
- Obter novos números usando o centro de administração do teams.
- Obter novos números que não estão disponíveis no centro de administração do teams.
- Portar ou transferir os números existentes de seu provedor de serviços atual ou da operadora de telefone para o Microsoft 365 ou o Office 365.

Você deve usar a página **Adicionar números** para ver, Pesquisar, adquirir e reservar esses números. Você pode pesquisar por país/região, estado e cidade e, em seguida, digitar o número de números de telefone necessários para seus usuários.

### <a name="get-new-user-phone-numbers-using-the-teams-admin-center"></a>Obter novos números de telefone de usuário usando o centro de administração do teams

1. Entre no Microsoft 365 com sua conta corporativa ou de estudante.

2. Vá para o **centro de administração do teams**.
    
3. No painel de navegação esquerdo, **Voice** vá para  >  **números de telefone** de voz, clique em **Adicionar** e siga os prompts.
    
### <a name="get-new-numbers-that-arent-available-in-the-teams-admin-center"></a>Obter novos números que não estão disponíveis no centro de administração do teams
  
Às vezes (dependendo do seu país/região) você não poderá obter seus novos números usando o centro de administração do teams. Nesse caso, você precisará baixar um formulário e enviá-lo de volta para nós. Para saber como solicitar novos números de usuário, consulte [gerenciar números de telefone de sua organização](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).   
  
### <a name="port-or-transfer-phone-numbers-from-your-service-provider-or-phone-carrier"></a>Fazer a portabilidade ou transferir os números de telefone de seu provedor de serviços ou de sua operadora de telefonia
  
- Se precisar de um 999 ou menos números de telefone para seus usuários, você pode usar o assistente **novo pedido de portabilidade de número local** no centro de administração do teams. Siga as etapas encontradas em [transferir números de telefone para o Microsoft Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) para transferir seus números de telefone.
    
- Se você precisar portar mais de 999 números de telefone, consulte [gerenciar números de telefone para sua organização](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) para enviar uma solicitação ou um pedido de serviço de pedido de portabilidade. 

Para obter informações detalhadas sobre como obter novos números de telefone ou transferir números existentes, consulte [Gerenciar números de telefone da sua organização](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

## <a name="step-4-get-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a>Etapa 4: Obtenha números de telefone do serviço (audioconferência, filas de chamadas, atendedores automáticos)

Além de obter números de telefone para seus usuários do Microsoft 365 ou do Office 365, você pode pesquisar e adquirir números de telefone de chamada tarifada ou gratuita para serviços como videoconferências (para pontes de conferência), atendedores automáticos e filas de chamadas. Os números telefônicos de serviço têm uma capacidade de chamada simultânea maior do que números de usuários ou assinantes. Por exemplo, um número de serviço pode manipular centenas de chamadas simultaneamente, enquanto o número de telefone de um usuário pode manipular apenas algumas chamadas simultaneamente.

### <a name="get-new-service-numbers-using-the-teams-admin-center"></a>Obter novos números de serviço usando o centro de administração do teams


1. Entre com sua conta corporativa ou de estudante.

2. Vá para o **centro de administração do teams**.

3. No painel de navegação esquerdo, vá para números de telefone de **voz**  >  **Phone numbers**  >  **Add new number** e, em seguida, clique em **novos números de serviço**.

    > [!IMPORTANT]
    > Para ver a opção de **voz** no painel de navegação à esquerda no centro de administração do Teams, primeiro você deve comprar pelo menos uma **licença Enterprise E5** , uma licença complementar do **sistema de telefonia** ou uma licença do suplemento de **conferência de áudio** .

### <a name="get-new-numbers-that-arent-available-in-the-teams-admin-center"></a>Obter novos números que não estão disponíveis no centro de administração do teams
  
Às vezes (dependendo do seu país/região) você não poderá obter seus novos números usando o centro de administração do teams. Nesse caso, você precisará baixar um formulário e enviá-lo de volta para nós. Para saber como solicitar novos números, consulte [gerenciar números de telefone de sua organização](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md). 

### <a name="port-or-transfer-existing-service-numbers"></a>Fazer a portabilidade ou transfira números de serviço existentes

Se deseja transferir números de serviço do seu provedor de serviço ou operadora atuais, você precisa enviar manualmente um pedido de portabilidade para a Microsoft. Você precisa enviar pedidos de porta separados para cada tipo de número de serviço (chamada tarifada e gratuita) que você transferirá usando uma letra de autorização (LOA). Na Carta de Autorização (LOA), você deve selecionar o tipo de número de serviço correto. Ao entrar em contato com o suporte da Microsoft, especifique que você está transferindo um número de serviço ( *e não um número de usuário ou de assinante* ) ou a capacidade de chamadas simultâneas pode não ser suficiente para lidar com volumes de chamadas. Se você deseja transferir números de telefone ou fazer outras coisas com seus números, consulte [Gerenciar números de telefone da sua organização](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

## <a name="step-5-if-you-want-to-set-up-calling-plans"></a>Etapa 5: Se você quiser configurar Planos de Chamadas

Se você seguiu as etapas acima, então já comprou e atribuiu um Sistema de Telefonia, licenças e um Plano de Chamadas (etapa 2), também já adquiriu números de telefone para seus usuários (etapa 3), portanto, seu Plano de Chamadas já está parcialmente configurado. Para concluir os procedimentos para a configuração do plano de chamadas, consulte [configurar planos de chamada](set-up-calling-plans.md).


## <a name="step-6-if-you-want-to-set-up-audio-conferencing"></a>Etapa 6: Se você deseja configurar a Audioconferência

Às vezes, as pessoas da sua organização precisam usar um telefone para ligar para uma reunião. O Microsoft Teams inclui o recurso de audioconferência por apenas essa situação. As pessoas podem fazer chamadas para reuniões do teams usando um telefone, em vez de usar o aplicativo Teams em um dispositivo móvel ou computador.
Para obter informações sobre como configurar a videoconferência, consulte [Configurar a conferência de áudio para o Microsoft Teams](set-up-audio-conferencing-in-teams.md).

## <a name="step-7-if-you-want-to-set-up-a-cloud-call-queue"></a>Etapa 7: se você quiser configurar uma fila de chamadas em nuvem

As filas de chamadas na nuvem incluem Saudações que são usadas quando alguém liga para um número de telefone para sua organização, a capacidade de colocar automaticamente as chamadas em espera e a capacidade de Pesquisar o próximo agente de chamada disponível para manipular a chamada, enquanto as pessoas que ligam estão ouvindo música em espera. Você pode criar uma ou várias filas de chamadas para sua organização.

Para obter mais informações sobre filas de chamadas, consulte [criar uma fila de chamadas na nuvem](create-a-phone-system-call-queue.md).

## <a name="step-8-if-you-want-to-set-up-a-cloud-auto-attendant"></a>Etapa 8: se você quiser configurar um atendedor automático na nuvem

Os atendedores automáticos permitem que as pessoas liguem para sua organização e naveguem em um sistema de menus para obter o departamento certo, a fila de chamadas, a pessoa ou a operadora. Você pode criar um atendedor automático para sua organização usando o centro de administração do teams.

Para obter informações sobre a configuração de uma attendendant automática na nuvem, consulte [configurar um atendedor automático na nuvem](create-a-phone-system-auto-attendant.md).


## <a name="step-9-assign-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a>Etapa 9: Atribua números de telefone de serviço (audioconferência, filas de chamadas, atendedores automáticos)

Depois de seguir a **Etapa 4 acima** e conseguir seus números de serviço, você precisará atribuí-los a cada tipo de serviço que deseja. Por exemplo, se você quiser um número de telefone de serviço dedicado (chamada tarifada ou gratuita), será preciso atribuir o número à ponte de conferência.

- Para conferências de áudio, você pode atribuir um número exclusivo a uma ponte de conferência acessando o **Teams Center Teams Center**  >  **reuniões**  >  **Conference Bridges** e siga as instruções.  Para obter mais informações, consulte  [alterar os números de chamada tarifada ou gratuita na sua ponte de audioconferência](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).

- Para atendedores automáticos, você pode atribuir um número exclusivo a um atendedor automático acessando **Teams admin center**  >  **Voice**  >  **atendedores automáticos** do centro de administração do Teams e siga as instruções.  Para obter mais informações, consulte [configurar um atendedor automático na nuvem](create-a-phone-system-auto-attendant.md).

- Para filas de chamadas, você pode atribuir um número exclusivo a uma fila de chamadas acessando filas de chamadas de voz do **centro de administração do teams**  >  **Voice**  >  **Call queues** e siga as instruções. Para obter mais informações, consulte [criar uma fila de chamadas em nuvem](create-a-phone-system-call-queue.md).

Para obter informações detalhadas sobre como obter novos números de serviço e fazer a portabilidade de números de serviço existentes, consulte [Obter números de telefone de serviço](getting-service-phone-numbers.md).

## <a name="step-10-set-up-communications-credits-for-your-organization"></a>Etapa 10: configurar créditos de comunicações para sua organização

Se quiser usar números de chamada gratuita com o Microsoft Teams, você precisará configurar créditos de comunicações. A Microsoft recomenda que você configure créditos de comunicações para seus planos de chamadas (domésticos ou internacionais) e usuários de audioconferência que precisem da capacidade de discar para qualquer destino. Muitos países/regiões estão incluídos, mas alguns destinos podem não ser incluídos no seu plano de chamadas ou assinaturas de audioconferência. 

Se você não configurar a cobrança de créditos de comunicações e atribuir uma licença de **créditos de comunicações** aos seus usuários e estiver em minutos para a sua organização (dependendo do seu plano de chamadas ou plano de audioconferência em seu país/região), esses usuários não poderão fazer chamadas nem discar de reuniões de audioconferência. Para obter mais informações, incluindo os valores de financiamento recomendados, consulte [o que são créditos de comunicações?](what-are-communications-credits.md) e [Configurar créditos de comunicações para sua organização](set-up-communications-credits-for-your-organization.md).
  

## <a name="related-topics"></a>Tópicos relacionados
[Veja o que você obtém com o sistema telefônico no Microsoft 365 ou no Office 365](here-s-what-you-get-with-phone-system.md)

[Gerenciar números de telefone para sua organização](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[Obtendo números de telefone de serviço do Skype for Business e do Microsoft Teams](getting-service-phone-numbers.md)

[Disponibilidade de Audioconferência e Planos de Chamadas por país e região](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
    
  
 
