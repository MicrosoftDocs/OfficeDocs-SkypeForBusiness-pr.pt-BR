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
- m365solution-voice
- m365solution-scenario
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
description: Guia passo a passo que detalha como configurar o Sistema de Telefonia (Cloud PBX) para sua organização no Microsoft 365 ou no Office 365.
ms.openlocfilehash: c00b628716a54adcb19c3dd1f00e8e9e2b6f4c40
ms.sourcegitcommit: 380a96f1ed2cefb429286854f06546bdb28d7d74
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701209"
---
# <a name="set-up-phone-system-in-your-organization"></a>Configurar o Sistema telefônico em sua organização

A seguir, um guia passo a passo para configurar o Sistema telefônico no Microsoft 365 ou no Office 365. Links para informações detalhadas adicionais estão disponíveis no final de cada etapa.

## <a name="step-1-make-sure-that-phone-system-is-available-in-your-country-or-region"></a>Etapa 1: Certifique-se de que o Sistema de Telefonia está disponível em seu país ou região

1.    Primeiro, acesse [Disponibilidade de Audioconferência e Planos de Chamadas por país e região](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) e selecione seu país ou região na lista na parte superior da página. 
2.    Em **Sistema de Telefonia**, examine a lista de recursos e detalhes. 
3.    Se o Sistema de Telefonia estiver disponível, vá para a etapa 2. 

## <a name="step-2-buy-and-assign-phone-system-and-calling-plan-licenses"></a>Etapa 2: Comprar e atribuir licenças do Sistema de Telefonia e Planos de Chamadas

Para atribuir uma licença do Sistema de Telefonia e do Plano de Chamada a um único usuário, as etapas são as mesmas que atribuir uma licença do Microsoft 365 ou do Office 365.  Você também pode atribuir licenças a vários usuários em massa. Para obter mais informações, consulte [Atribuir licenças de complemento do Microsoft Teams.](teams-add-on-licensing/assign-teams-add-on-licenses.md)

Se os Planos de Chamada não estão disponíveis para seu país ou região, considere usar o Roteamento Direto para conectar sua infraestrutura de telefonia local ao Sistema de Telefonia.  Para obter mais informações, consulte [Roteamento Direto do Sistema de Telefone.](direct-routing-landing-page.md)

## <a name="step-3-get-phone-numbers-for-your-users"></a>Etapa 3: obter números de telefone para seus usuários

Antes de configurar usuários em sua organização para fazer e receber chamadas telefônicas, você deve obter números de telefone para eles.

Você tem três maneiras de obter números para seus usuários:
- Obter novos números usando o Centro de administração do Teams.
- Obter novos números que não estão disponíveis no Centro de administração do Teams.
- Transfira ou transfira os números existentes do provedor de serviços ou da operadora de telefonia atual para o Microsoft 365 ou o Office 365.

Você deve usar **a página Adicionar números** para ver, pesquisar, adquirir e reservar esses números. Você pode pesquisar por País/Região, Estado e Cidade e inserir o número de números de telefone necessários para seus usuários.

### <a name="get-new-user-phone-numbers-using-the-teams-admin-center"></a>Obter novos números de telefone de usuário usando o Centro de administração do Teams

1. Entre no Microsoft 365 com sua conta do trabalho ou da escola.

2. Vá para o **Centro de administração do Teams.**
    
3. No painel de navegação esquerdo, vá para números **de Telefone** De Voz, clique em  >   **Adicionar** e siga as solicitações.
    
### <a name="get-new-numbers-that-arent-available-in-the-teams-admin-center"></a>Obter novos números que não estão disponíveis no Centro de administração do Teams
  
Às vezes (dependendo do seu país/região), você não poderá obter seus novos números usando o Centro de administração do Teams. Nesse caso, você precisará baixar um formulário e enviá-lo de volta para nós. Para saber como solicitar novos números de usuário, consulte [Gerenciar números de telefone para sua organização.](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)   
  
### <a name="port-or-transfer-phone-numbers-from-your-service-provider-or-phone-carrier"></a>Fazer a portabilidade ou transferir os números de telefone de seu provedor de serviços ou de sua operadora de telefonia
  
- Se precisar de 999 ou menos números de telefone para seus usuários, você pode usar o assistente Novo Pedido de **Portabilidade** de Número Local no Centro de administração do Teams. Siga as etapas encontradas em [Transferir números de telefone para o Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) para transferir seus números de telefone.
    
- Se você precisar fazer a portabilidade de [](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) mais de 999 números de telefone, consulte Gerenciar números de telefone de sua organização para enviar uma solicitação ou pedido de serviço de pedido de portabilidade. 

Para obter informações detalhadas sobre como obter novos números de telefone ou transferir números existentes, consulte [Gerenciar números de telefone da sua organização](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

## <a name="step-4-get-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a>Etapa 4: Obtenha números de telefone do serviço (audioconferência, filas de chamadas, atendedores automáticos)

Além de obter números de telefone para os usuários do Microsoft 365 ou do Office 365, você pode pesquisar e adquirir números de telefone de chamada tarifada ou gratuita para serviços como audioconferência (para pontes de conferência), atender automaticamente e filas de chamadas. Os números telefônicos de serviço têm uma capacidade de chamada simultânea maior do que números de usuários ou assinantes. Por exemplo, um número de serviço pode lidar com centenas de chamadas simultaneamente, enquanto o número de telefone de um usuário só pode lidar com algumas chamadas simultaneamente.

### <a name="get-new-service-numbers-using-the-teams-admin-center"></a>Obter novos números de serviço usando o Centro de administração do Teams


1. Entre com sua conta do trabalho ou da escola.

2. Vá para o **Centro de administração do Teams.**

3. No painel de navegação esquerdo, vá para **Números de Telefone** De Voz Adicionar novo número e clique em Novos números de  >    >   **serviço.**

    > [!IMPORTANT]
    > Para ver a  opção Voz no painel de navegação à esquerda no Centro de administração do  Teams, primeiro você deve comprar pelo menos uma licença **Enterprise E5,** uma licença de complemento do Sistema de Telefonia ou uma licença de complemento de **AudioConferência.**

### <a name="get-new-numbers-that-arent-available-in-the-teams-admin-center"></a>Obter novos números que não estão disponíveis no Centro de administração do Teams
  
Às vezes (dependendo do seu país/região), você não poderá obter seus novos números usando o Centro de administração do Teams. Nesse caso, você precisará baixar um formulário e enviá-lo de volta para nós. Para saber como solicitar novos números, consulte Gerenciar números [de telefone para sua organização.](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 

### <a name="port-or-transfer-existing-service-numbers"></a>Fazer a portabilidade ou transfira números de serviço existentes

Se deseja transferir números de serviço do seu provedor de serviço ou operadora atuais, você precisa enviar manualmente um pedido de portabilidade para a Microsoft. Você precisa enviar pedidos de portabilidade separados para cada tipo de número de serviço (tarifa versus tarifa gratuita) que será transferido usando uma Carta de Autorização (LOA). Na Carta de Autorização (LOA), você deve selecionar o tipo de número de serviço correto. Ao entrar em contato com o suporte da Microsoft, especifique que você está transferindo um número de serviço *(e* não um número de usuário ou assinante) ou a capacidade de chamada simultânea pode não ser suficiente para lidar com os volumes de chamada. Se você deseja transferir números de telefone ou fazer outras coisas com seus números, consulte [Gerenciar números de telefone da sua organização](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

## <a name="step-5-if-you-want-to-set-up-calling-plans"></a>Etapa 5: Se você quiser configurar Planos de Chamadas

Se você seguiu as etapas acima, então já comprou e atribuiu um Sistema de Telefonia, licenças e um Plano de Chamadas (etapa 2), também já adquiriu números de telefone para seus usuários (etapa 3), portanto, seu Plano de Chamadas já está parcialmente configurado. Para concluir os procedimentos para configurar o Plano de Chamada, consulte [Configurar Planos de Chamada.](set-up-calling-plans.md)


## <a name="step-6-if-you-want-to-set-up-audio-conferencing"></a>Etapa 6: Se você deseja configurar a Audioconferência

Às vezes, as pessoas da sua organização precisam usar um telefone para ligar para uma reunião. O Microsoft Teams inclui o recurso audioconferência apenas para esta situação. As pessoas podem ligar para reuniões do Teams usando um telefone, em vez de usar o aplicativo Teams em um dispositivo móvel ou computador.
Para obter informações sobre como configurar a Audioconferência, consulte [Configurar a Audioconferência para o Teams.](set-up-audio-conferencing-in-teams.md)

## <a name="step-7-if-you-want-to-set-up-a-cloud-call-queue"></a>Etapa 7: se você quiser configurar uma fila de chamada na nuvem

As filas de chamadas na nuvem incluem saudações que são usadas quando alguém liga para um número de telefone de sua organização, a capacidade de colocar automaticamente as chamadas em espera e a capacidade de procurar o próximo agente de chamada disponível para lidar com a chamada enquanto as pessoas que telefonam estão ouvindo música em espera. Você pode criar uma ou várias filas de chamadas para sua organização.

Para obter mais informações sobre filas de chamada, consulte [Criar uma fila de chamada na nuvem.](create-a-phone-system-call-queue.md)

## <a name="step-8-if-you-want-to-set-up-a-cloud-auto-attendant"></a>Etapa 8: se você quiser configurar um assistente automático na nuvem

Os participantes automáticos permitem que as pessoas que liguem para sua organização e naveguem por um sistema de menus para que eles acessem o departamento certo, fila de chamada, pessoa ou o operador. Você pode criar um assistente automático para sua organização usando o Centro de administração do Teams.

Para obter informações sobre como configurar um participante automático da Nuvem, consulte [Configurar um atendedor automático na nuvem.](create-a-phone-system-auto-attendant.md)


## <a name="step-9-assign-service-phone-numbers-audio-conferencing-call-queues-auto-attendants"></a>Etapa 9: Atribua números de telefone de serviço (audioconferência, filas de chamadas, atendedores automáticos)

Depois de seguir a **Etapa 4 acima** e conseguir seus números de serviço, você precisará atribuí-los a cada tipo de serviço que deseja. Por exemplo, se você quiser um número de telefone de serviço dedicado (chamada tarifada ou gratuita), será necessário atribuir o número à ponte de conferência.

- Para a Audioconferência, você pode atribuir um número dedicado a uma ponte de conferência indo para pontes de Conferência do Centro de administração do **Teams** e  >    >   seguindo as solicitações.  Para obter mais informações, consulte Alterar os números de tarifa ou de tarifa [gratuita em sua ponte de Audioconferência.](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)

- Para Os Assistentes Automáticos, você pode atribuir um número dedicado a um assistente automático indo para os  >    >  **Assistentes automáticos** do Centro de administração do Teams e seguindo as solicitações.  Para obter mais informações, consulte [Configurar um assistente automático na nuvem.](create-a-phone-system-auto-attendant.md)

- Para filas de chamadas, você pode atribuir um número dedicado a uma fila de chamadas indo para filas de Chamadas de Voz do Centro de administração do **Teams** e  >    >   seguindo as solicitações. Para obter mais informações, consulte [Criar uma fila de chamada na nuvem.](create-a-phone-system-call-queue.md)

Para obter informações detalhadas sobre como obter novos números de serviço e fazer a portabilidade de números de serviço existentes, consulte [Obter números de telefone de serviço](getting-service-phone-numbers.md).

## <a name="step-10-set-up-communications-credits-for-your-organization"></a>Etapa 10: Configurar Créditos de Comunicação para sua organização

Se você quiser usar números de tarifa gratuita com o Microsoft Teams, será necessário configurar Créditos de Comunicação. A Microsoft recomenda que você defina Créditos de Comunicação para seus Planos de Chamada (Domésticas ou Internacionais) e usuários de Audioconferência que precisam da capacidade de discar para qualquer destino. Muitos países/regiões estão incluídos, mas alguns destinos podem não estar incluídos em suas assinaturas de Plano de Chamada ou Audioconferência. 

Se você não configurar a cobrança de Créditos de Comunicação e atribuir uma licença de **Créditos** de Comunicação aos usuários e ficar sem minutos para sua organização (dependendo do plano de Chamada ou do plano de Audioconferência em seu país/região), esses usuários não poderão fazer chamadas ou discar de reuniões de Audioconferência. Para obter mais informações, incluindo valores de financiamento [recomendados,](what-are-communications-credits.md) consulte O que são Créditos de Comunicação? e Configurar Créditos de Comunicação [para sua organização.](set-up-communications-credits-for-your-organization.md)
  

## <a name="related-topics"></a>Tópicos relacionados
[Veja aqui o que você pode obter com o Sistema de Telefonia no Microsoft 365 ou no Office 365](here-s-what-you-get-with-phone-system.md)

[Gerenciar números de telefone para sua organização](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[Obtendo números de telefone de serviço do Skype for Business e do Microsoft Teams](getting-service-phone-numbers.md)

[Disponibilidade de Audioconferência e Planos de Chamadas por país e região](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
    
  
 
