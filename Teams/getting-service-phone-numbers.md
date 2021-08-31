---
title: Obter números de telefone de serviço
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
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
- seo-marvel-mar2020
description: Saiba como obter novos números de telefone e porta ou transferir números existentes para audioconferências, atendimentos automáticos e filas de chamada (números de serviço) para Teams.
ms.openlocfilehash: fb0025796ad9bbb91c5172cf2cb551de6ecf619b
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58732910"
---
# <a name="getting-service-phone-numbers"></a>Obter números de telefone de serviço

Além de obter números de telefone para seus [usuários,](./getting-phone-numbers-for-your-users.md)você pode obter números de telefone gratuitos ou de chamada gratuita para serviços como Audioconferência (para pontes de conferência), atendimentos automáticos e filas de chamadas (também chamados de números de serviço). Os números telefônicos de serviço têm uma capacidade de chamada simultânea maior do que números de usuários ou assinantes. Por exemplo, um número de serviço pode manipular centenas de chamadas simultaneamente, enquanto o número de telefone de um usuário só pode manipular algumas chamadas simultaneamente.
  
> [!NOTE]
> Você precisa primeiro configurar os Créditos de Comunicações antes de obter números gratuitos. Para saber mais, consulte [Set up Communications Credits for your organization](./set-up-communications-credits-for-your-organization.md).
  
Há três maneiras de obter números de serviço:
  
- **Use o Microsoft Teams de administração.** Para alguns países e regiões, você pode obter números de serviço usando o Microsoft Teams de administração. Consulte [Obter novos números de serviço](#get-new-service-numbers).

- **Fazer a portabilidade de seus números existentes.** Você pode por ou transferir números existentes de seu provedor de serviços ou operadora de telefonia atual. Consulte [Transferir os números dos telefones ao Teams](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md) ou [Gerenciar números de telefone da sua organização](/microsoftteams/manage-phone-numbers-for-your-organization) para obter mais informações.  
  
- **Usar um formulário de solicitação para novos números.** Às vezes (dependendo do seu país ou região), você não conseguirá obter seus novos números de telefone usando o centro de administração do Microsoft Teams ou precisará de números de telefone ou códigos de área específicos. Em caso afirmado, você precisará baixar um formulário e enviá-lo de volta para nós. Para obter mais informações, consulte [Gerenciar números de telefone para sua organização](/microsoftteams/manage-phone-numbers-for-your-organization).
  
> [!NOTE]
> Os números de serviço são necessários para que você possa obter uma capacidade de chamada simultânea maior para um número específico. Ao transferir o número para nós, você pode entrar em contato com o service [desk PSTN](manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md) para garantir que o número de serviço que você está transferindo tenha uma alta capacidade de chamada simultânea.
  
## <a name="get-new-service-numbers"></a>Obtenha novos números de serviço

![Um ícone mostrando o logotipo Microsoft Teams.](media/teams-logo-30x30.png) **Usando o centro de administração do Microsoft Teams**

1. Na navegação à esquerda, vá para **Voz**  >  **Telefone números** e clique em **Adicionar**.
2. Insira um nome para a ordem e adicione uma descrição.
3. Na página Local e quantidade, faça o seguinte:
    1. Em **País ou região**, selecione um país ou região.
    1. Em **Tipo de número**, selecione o tipo de número de serviço que você deseja.
    1. Em **Local**, selecione um local. Se precisar criar um novo local, clique em **Adicionar um local**.
    1. Em **Código de área,** selecione um código de área. 
    2. Em **Quantidade**, insira o número de números que você deseja para sua organização e clique em **Próximo** para selecionar seus números.
4. Selecione os números que você deseja. Você tem 10 minutos para selecionar seus números de telefone e fazer o pedido. Se você demorar mais de 10 minutos, os números de telefone serão retornados para o pool de números.
5. Quando estiver pronto para fazer seu pedido, clique em **Colocar ordem**.

## <a name="port-or-transfer-existing-service-numbers"></a>Fazer a portabilidade ou transfira números de serviço existentes

Para transferir seus números de telefone do seu provedor de serviços ou operadora atual para Teams, você pode usar o assistente de portação no centro de administração Microsoft Teams. Siga as etapas em [Transferir números de telefone para Teams](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md).

Se seu país ou região não estiver listado no assistente de portabilidade, você poderá enviar [manualmente](phone-number-calling-plans/manually-submit-port-order.md) uma ordem de porta ou ir para Gerenciar números de telefone para sua [organização,](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)selecionar seu país ou região e baixar uma Carta de Autorização (LOA). Você terá que enviar pedidos de porta separados para cada tipo de número de serviço (por exemplo, toll vs. toll-free) que você será transferido usando uma LOA. Na LOA, você deve selecionar o tipo correto de número de serviço. Certifique-se de especificar que você está transferindo um número de serviço (e não um número de usuário ou assinante), ou a capacidade de chamada simultânea pode não ser suficiente para lidar com volumes de chamada.  

> [!NOTE]
> Se você precisar obter mais números de telefone do que isso, [entre em contato com o service desk PSTN](manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md).

## <a name="view-the-phone-numbers-for-your-organization"></a>Exibir os números de telefone para sua organização

![Um ícone mostrando o logotipo Microsoft Teams.](media/teams-logo-30x30.png) **Usando o centro de administração do Microsoft Teams** 

Na navegação à esquerda, vá até **Voz** Telefone para exibir os números da sua organização, incluindo local, tipo de número  >   e informações de status.

## <a name="assign-service-phone-numbers"></a>Atribuir números de telefone de serviço

Depois de obter seus números de serviço, atribua cada número a uma ponte de Audioconferência. Consulte [Alterar os números de tarifação gratuita ou de tarifação em sua ponte de Audioconferência.](./change-the-phone-numbers-on-your-audio-conferencing-bridge.md)

## <a name="related-topics"></a>Tópicos relacionados

[Veja o que você obtém com o Sistema de Telefonia](./here-s-what-you-get-with-phone-system.md)

[Perguntas comuns sobre a transferência de números de telefone](./phone-number-calling-plans/port-order-overview.md)

[Diferentes tipos de números de telefone usados para Planos de Chamadas](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Gerenciar os números de telefone de sua organização](/microsoftteams/manage-phone-numbers-for-your-organization)

[Disponibilidade de Audioconferência e Planos de Chamadas por país e região](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)