---
title: Obter números de telefone de serviço para Planos de Chamadas
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, jastark, oscarr, makolomi
ms.topic: article
ms.assetid: e434aeb2-af99-40e7-981e-a474f0383734
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-mar2020
description: Saiba como obter novos números de telefone e portabilidade ou transferir números existentes para Audioconferência, Atendedores Automáticos e Filas de Chamadas (números de serviço) para o Teams.
ms.openlocfilehash: c38d94085597bde2d29ae9233db024a1f2814fdb
ms.sourcegitcommit: f0e2a5928e9b959daf45202b9f256f65c2087195
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68614604"
---
# <a name="service-phone-numbers-for-calling-plans"></a>Números de telefone de serviço para Planos de Chamadas

Além de obter números de telefone para seus [usuários, você](./getting-phone-numbers-for-your-users.md) pode obter números de chamada tarifada ou gratuita para serviços como Audioconferência (para pontes de conferência), Atendedores Automáticos e Filas de Chamadas (também chamados de números de serviço). Os números telefônicos de serviço têm uma capacidade de chamada simultânea maior do que números de usuários ou assinantes. Por exemplo, um número de serviço pode lidar com centenas de chamadas simultaneamente, enquanto o número de telefone de um usuário só pode manipular algumas chamadas simultaneamente.
  
> [!NOTE]
> Você precisa primeiro configurar os Créditos de Comunicação antes de obter números de chamada gratuita. Para saber mais, confira [Configurar Créditos de Comunicação para sua organização](./set-up-communications-credits-for-your-organization.md).
  
Há três maneiras de obter números de serviço:
  
- **Use o centro de administração do Microsoft Teams.** Para alguns países e regiões, você pode obter números de serviço usando o centro de administração do Microsoft Teams. Consulte [Obter novos números de serviço](#get-new-service-numbers).

- **Fazer a portabilidade de seus números existentes.** Você pode portar ou transferir números existentes de seu provedor de serviços ou operadora de telefonia atual. Consulte [Transferir os números dos telefones ao Teams](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md) ou [Gerenciar números de telefone da sua organização](/microsoftteams/manage-phone-numbers-for-your-organization) para obter mais informações.  
  
- **Usar um formulário de solicitação para novos números.** Às vezes (dependendo do seu país ou região), você não poderá obter seus novos números de telefone usando o Centro de administração do Microsoft Teams ou precisará de números de telefone ou códigos de área específicos. Nesse caso, você precisará baixar um formulário e enviá-lo de volta para nós. Para obter mais informações, consulte [Gerenciar números de telefone para sua organização](/microsoftteams/manage-phone-numbers-for-your-organization).
  
> [!NOTE]
> Os números de serviço são necessários para que você possa obter uma capacidade de chamada simultânea mais alta para um número específico. Ao transferir o número para nós, você pode entrar em contato com o suporte de serviço [TNS](manage-phone-numbers-for-your-organization/contact-tns-service-desk.md) para verificar se o número de serviço que você está transferindo tem uma alta capacidade de chamada simultânea.
  
## <a name="get-new-service-numbers"></a>Obtenha novos números de serviço

Para obter novos números de serviço, no centro de administração do Teams:

1. No painel de navegação esquerdo, vá para **números de Telefone** > **de** Voz e clique em **Adicionar**.

2. Insira um nome para o pedido e adicione uma descrição.

3. Na página Localização e quantidade, faça o seguinte:
    - Em **País ou região**, selecione um país ou região.
    - Em **Tipo de número**, selecione o tipo de número de serviço desejado.
    - Em **Local**, selecione um local. Se você precisar criar um novo local, clique **em Adicionar um local**.
    - Em **Código de área**, selecione um código de área. 
    - Em **Quantidade**, insira o número de números desejados para sua organização e clique em **Avançar** para selecionar seus números.

4. Selecione os números desejados. Você tem 10 minutos para selecionar seus números de telefone e fazer seu pedido. Se você levar mais de 10 minutos, os números de telefone serão retornados para o pool de números.

5. Quando estiver pronto para fazer seu pedido, clique em **Fazer pedido**.

## <a name="port-or-transfer-existing-service-numbers"></a>Fazer a portabilidade ou transfira números de serviço existentes

Para transferir seus números de telefone do seu provedor de serviços ou operadora atual para o Teams, você pode usar o assistente de portabilidade no centro de administração do Microsoft Teams. Siga as etapas em [Transferir números de telefone para o Teams](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md).

Se seu país ou região não estiver listado no assistente de portabilidade, você poderá enviar [manualmente](phone-number-calling-plans/manually-submit-port-order.md) um pedido de portabilidade ou ir para Gerenciar números de telefone da sua [organização, selecionar](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) seu país ou região e baixar uma Carta de Autorização (LOA). Você precisará enviar pedidos de portabilidade separados para cada tipo de número de serviço (por exemplo, chamada tarifada versus chamada gratuita) que você transferirá usando uma LOA. Na LOA, você deve selecionar o tipo correto de número de serviço. Certifique-se de especificar que está transferindo um número de serviço (e não um número de usuário ou assinante) ou a capacidade de chamada simultânea pode não ser suficiente para lidar com volumes de chamadas.  

> [!NOTE]
> Se você precisar obter mais números de telefone do que isso, [entre em contato com o suporte de serviço TNS](manage-phone-numbers-for-your-organization/contact-tns-service-desk.md).

## <a name="view-the-phone-numbers-for-your-organization"></a>Exibir os números de telefone da sua organização

No centro de administração do Teams, no painel de navegação esquerdo,  >  vá para números de Telefone de Voz para exibir os números da sua organização, incluindo informações de localização, tipo de número e status.

## <a name="assign-service-phone-numbers"></a>Atribuir números de telefone de serviço

Depois de obter os números de serviço, atribua cada número a uma ponte de Audioconferência. Consulte [Alterar os números de chamada tarifada ou gratuita em sua ponte de Audioconferência](./change-the-phone-numbers-on-your-audio-conferencing-bridge.md).

## <a name="related-topics"></a>Tópicos relacionados

[Veja o que você obtém com o Sistema de Telefonia](./here-s-what-you-get-with-phone-system.md)

[Perguntas comuns sobre transferência de números de telefone](./phone-number-calling-plans/port-order-overview.md)

[Diferentes tipos de números de telefone usados para Planos de Chamadas](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Gerenciar os números de telefone de sua organização](/microsoftteams/manage-phone-numbers-for-your-organization)

[Disponibilidade de Audioconferência e Planos de Chamadas por país e região](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
