---
title: Use o assistente de conector de turnos para conectar Shifts ao Gerenciamento de Força de Trabalho de Zona Azul
author: lanachin
ms.author: v-lanachin
ms.reviewer: ''
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Saiba como usar o assistente do conector shifts para integrar Shifts no Teams com o Gerenciamento de Força de Trabalho do Blue Yonder.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4041b0909a3c5e8f1aa256fd2ec662030548343c
ms.sourcegitcommit: 2388838163812eeabcbd5331aaf680b79da3ccba
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2022
ms.locfileid: "64593629"
---
# <a name="use-the-shifts-connector-wizard-to-connect-shifts-to-blue-yonder-workforce-management"></a>Use o assistente de conector de turnos para conectar Shifts ao Gerenciamento de Força de Trabalho de Zona Azul

## <a name="overview"></a>Visão geral

O assistente do conector shifts no Centro de administração do Microsoft 365 permite integrar o aplicativo Shifts no Microsoft Teams com o sistema WFM (gerenciamento de força de trabalho). Depois de configurar uma conexão, seus funcionários de linha de frente podem exibir e gerenciar seus agendamentos em seu sistema WFM de dentro de Shifts.

O assistente configura o conector Shifts, cria uma conexão com o sistema WFM e aplica as configurações de sincronização e os mapeamentos de equipe escolhidos. As configurações de sincronização determinam as informações de agendamento sincronizadas entre o sistema WFM e Shifts. Mapeamentos de equipe definem a relação de sincronização entre seus sites WFM e equipes em Teams. Você pode mapear para equipes existentes e novas equipes.

Você pode configurar várias conexões, cada uma com configurações de sincronização diferentes. Por exemplo, se sua organização tiver vários locais com requisitos de agendamento diferentes, crie uma conexão com configurações de sincronização exclusivas para cada local. Lembre-se de que um site WFM só pode ser mapeado para uma equipe a qualquer momento. Se um site WFM já estiver mapeado para uma equipe, ele não poderá ser mapeado para outra equipe.

Com seu sistema WFM como o sistema de registro, seus funcionários de linha de frente podem ver e trocar turnos, gerenciar sua disponibilidade e solicitar folga em Turnos em seus dispositivos. Os gerentes de linha de frente podem continuar a usar seu sistema WFM para configurar agendamentos.

## <a name="integrate-shifts-with-blue-yonder-workforce-management"></a>Integrar turnos com o Gerenciamento de Força de Trabalho do Blue Yonder

Atualmente, o assistente dá suporte ao [conector Microsoft Teams Shifts para Blue Yonder](shifts-connectors.md#microsoft-teams-shifts-connector-for-blue-yonder). Esse conector permite integrar Shifts ao Blue Yonder Workforce Management (Blue Yonder WFM) para gerenciar seus agendamentos e mantê-los atualizados. Neste artigo, explicamos como executar o assistente para configurar uma conexão com o WFM do Blue Yonder por meio do conector.

> [!NOTE]
> Você também pode usar o PowerShell para integrar Shifts com Blue Yonder WFM. Para saber mais, [consulte Use PowerShell to connect Shifts to Blue Yonder Workforce Management](shifts-connector-blue-yonder-powershell-setup.md).

## <a name="before-you-begin"></a>Antes de você começar

Você deve ser um Microsoft 365 global para executar o assistente.

### <a name="prerequisites"></a>Pré-requisitos
<a name="prerequisites"> </a>
[!INCLUDE [shifts-connector-prerequisites](../../includes/shifts-connector-prerequisites.md)]

- As equipes que você deseja mapear não têm cronogramas. Se uma equipe tiver uma agenda existente, [remova](#remove-schedules-from-teams-you-want-to-map) a agenda da equipe antes de mapear um site WFM do Blue Yonder para ele. Caso contrário, você verá turnos duplicados.

## <a name="remove-schedules-from-teams-you-want-to-map"></a>Remover agendas das equipes que você deseja mapear
<a name="remove_schedules"> </a>

> [!NOTE]
> Conclua esta etapa se você estiver mapeando sites WFM do Blue Yonder para equipes existentes que tenham agendamentos. Se você estiver mapeando para equipes que não têm cronogramas ou se estiver criando novas equipes para mapear, ignore esta etapa.

Use o PowerShell para remover agendamentos das equipes.

1. Primeiro, você precisará instalar os módulos do PowerShell e se configurar. Siga as etapas para [configurar seu ambiente](shifts-connector-powershell-manage.md#set-up-your-environment).
1. Execute o seguinte comando:

    ```powershell
    Remove-CsTeamsShiftsScheduleRecord -TeamId <Teams team ID> -DateRangeStartDate <start time> -DateRangeEndDate <end time> -ClearSchedulingGroup:$false -EntityType <the scenario entities that you want to remove, the format is @(scenario1, scenario2, ...)> -DesignatedActorId <Teams team owner ID>
    ```

    Para obter uma lista de cenários para o `EntityType` parâmetro, execute [Get-CsTeamsShiftsConnectionConnector](/powershell/module/teams/get-csteamsshiftsconnectionconnector?view=teams-ps). Os dados de agendamento serão removidos para a data e o intervalo de tempo especificados.

Para saber mais, confira [Remove-CsTeamsShiftsScheduleRecord](/powershell/module/teams/remove-csteamsshiftsschedulerecord?view=teams-ps).

## <a name="run-the-wizard"></a>Executar o assistente

### <a name="get-started"></a>Introdução

1. Na navegação à esquerda [do Centro de administração do Microsoft 365,](https://admin.microsoft.com/) escolha **Configurar** e vá para a seção **Aplicativos e email**.
1. Selecione **Conexão seu sistema de gerenciamento de força de trabalho**. Aqui, você pode saber mais sobre conectores shifts e a experiência de trabalho e gerente de linha de frente ao conectar Shifts ao sistema WFM.
    :::image type="content" source="../../media/shifts-connector-wizard-get-started.png" alt-text="Captura de tela da página de detalhes do assistente do conector shifts no Centro de administração do Microsoft 365." lightbox="../../media/shifts-connector-wizard-get-started.png":::
1. Quando estiver pronto, selecione **Introdução**.
1. Selecione **Próximo** para criar uma conexão WFM do Blue Yonder.

### <a name="enter-connection-details"></a>Insira detalhes da conexão
<a name="connection_details"> </a>

1. Na página Detalhes da conexão, dê à sua conexão um nome exclusivo. Não pode ter mais de 128 caracteres ou ter caracteres especiais.
    :::image type="content" source="../../media/shifts-connector-wizard-connection-details.png" alt-text="Captura de tela da página Detalhes da conexão do assistente, mostrando configurações de conexão." lightbox="../../media/shifts-connector-wizard-connection-details.png":::
1. Insira o nome da conta de serviço WFM do Blue Yonder e as URLs de senha e serviço.
1. Quando terminar, selecione **Próximo** para testar a conexão com as configurações inseridas.

### <a name="choose-sync-settings"></a>Escolha configurações de sincronização
<a name="sync"> </a>

Na página Configurações de sincronização, você escolhe as informações para sincronizar do WFM do Blue Yonder para Shifts, a frequência de sincronização e se os usuários de Shifts podem fazer alterações nos dados.

1. Insira sua Microsoft 365 do sistema.
    :::image type="content" source="../../media/shifts-connector-wizard-sync-settings.png" alt-text="Captura de tela da página Configurações de sincronização do assistente, mostrando configurações de sincronização." lightbox="../../media/shifts-connector-wizard-sync-settings.png":::
<a name="email"> </a>
1. Em **Destinatários de notificação de** email, escolha quem recebe notificações por email sobre essa conexão. Você pode adicionar usuários e grupos individuais. As notificações por email contêm informações sobre o status da configuração de conexão e quaisquer problemas ou erros que possam ocorrer após a configuração da conexão.
1. Escolha suas configurações de sincronização:
    1. Em **Agenda e turnos**, escolha os dados WFM do Blue Yonder que os usuários shifts podem ver ou alterar e, em seguida, definir a frequência de sincronização.
    2. Em **Solicitações**, escolha os tipos de solicitações que os usuários shifts podem ver e criar.

    > [!IMPORTANT]
    > Se você escolher qualquer uma das opções a seguir para desabilitar turnos abertos, solicitações de turno aberto, solicitações de troca ou solicitações de folga, há outra etapa que você precisa fazer para ocultar o recurso em Shifts.
    >
    > - Turnos abertos: **os usuários de turnos não verão dados WFM do Blue Yonder**
    > - Solicitações de troca: **o recurso está desabilitado para todos os usuários**
    > - Solicitações de tempo de folga: **o recurso está desabilitado para todos os usuários**
    >
    > Depois de executar o assistente, siga as etapas na seção Desabilitar turnos abertos, abrir solicitações de [turnos,](#disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests) solicitações de troca e solicitações de folga posteriormente neste artigo.
 
1. Quando terminar de escolher suas configurações, selecione **Criar conexão**.

### <a name="map-blue-yonder-workforce-management-sites-to-teams"></a>Mapear sites de Gerenciamento de Força de Trabalho do Blue Yonder para equipes
<a name="sites"> </a>

Escolha os sites WFM do Blue Yonder que você deseja conectar a Shifts. Você pode selecionar até 100 sites.

:::image type="content" source="../../media/shifts-connector-wizard-sites.png" alt-text="Captura de tela do assistente, mostrando a lista de sites WFM do Blue Yonder." lightbox="../../media/shifts-connector-wizard-sites.png":::
<a name="mapping"> </a>
<a name="search_teams"> </a> Em seguida, mapeie cada site WFM do Blue Yonder selecionado para uma equipe no Teams. Você pode mapear um site para uma equipe existente ou criar uma nova equipe.
:::image type="content" source="../../media/shifts-connector-wizard-search-team.png" alt-text="Captura de tela do painel mostrando a opção de equipe de pesquisa e crie uma nova opção de equipe." lightbox="../../media/shifts-connector-wizard-search-team.png":::
#### <a name="to-map-a-site-to-an-existing-team"></a>Para mapear um site para uma equipe existente

1. Selecione o nome do site.
2. No painel, procure a equipe e selecione-a. Lembre-se de que as equipes que já estão mapeadas para um site nessa conexão não aparecem na pesquisa.
3. Escolha o fuso horário e a cidade mais próxima.
4. Selecione **Salvar** e selecione **Próximo**.

#### <a name="to-map-a-site-to-a-new-team"></a>Para mapear um site para uma nova equipe

1. Selecione o nome do site.
2. No painel, escolha **Criar uma nova equipe**. Você será levado para uma nova guia no navegador, onde poderá criar uma nova equipe no Centro de administração do Microsoft 365.
    1. Insira um nome e uma descrição opcional para a equipe.
    1. Adicione um ou mais proprietários de equipe. Certifique-se de adicionar a Microsoft 365 do sistema como proprietário.
    1. Adicionar membros da equipe.
    1. Adicione um endereço de email de equipe e escolha uma configuração de privacidade.
    1. Revise suas configurações e escolha **Adicionar equipe**. Quando sua equipe for criada, escolha **Fechar**.
3. Voltar ao assistente, procure e selecione a nova equipe que você criou.
4. Escolha o fuso horário e a cidade mais próxima.
5. Selecione **Salvar** e selecione **Próximo**.

### <a name="review-and-finish"></a>Revisar e concluir

Revise suas configurações. Se você precisar fazer alterações em qualquer mapeamento de equipe, escolha **Editar** para fazer isso. Quando estiver pronto, selecione **Concluir**.

:::image type="content" source="../../media/shifts-connector-wizard-review.png" alt-text="Captura de tela da página Revisão do assistente, mostrando mapeamentos." lightbox="../../media/shifts-connector-wizard-review.png":::

Você verá uma mensagem para confirmar que recebemos sua solicitação juntamente com uma ID de operação. Anote a ID da operação. Você precisará dele para verificar o status de configuração de sua conexão.

:::image type="content" source="../../media/shifts-connector-wizard-operation-id.png" alt-text="Captura de tela da página do assistente, mostrando a mensagem de confirmação e a ID da operação." lightbox="../../media/shifts-connector-wizard-operation-id.png":::

O assistente inicia o processo para configurar a conexão e mapear os sites para as equipes selecionadas. Esse processo pode levar algum tempo para ser concluído. Os destinatários escolhidos receberão notificações por email sobre o status da instalação.

Selecione **Feito** para sair do assistente.

Você está a caminho, mas ainda não terminou! Verifique seu email. Você receberá uma confirmação de que recebemos sua solicitação juntamente com um [link](shifts-connector-powershell-manage.md#check-connection-setup-status) para como você pode verificar o status da instalação.

> [!NOTE]
> Se ocorrer um problema ou erro em uma conexão após a configuração, você será notificado por email. Siga as instruções no email para solucionar o problema.

## <a name="disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests"></a>Desabilitar turnos abertos, solicitações de turnos abertos, solicitações de troca e solicitações de folga

> [!IMPORTANT]
> Siga estas etapas somente se você escolher qualquer uma das opções a seguir para desabilitar turnos abertos, solicitações de turno aberto, solicitações de troca ou solicitações de tempo de folga no assistente. Concluir esta etapa oculta a funcionalidade em Shifts.
>
> - Turnos abertos: **os usuários de turnos não verão dados WFM do Blue Yonder**
> - Solicitações de troca: **o recurso está desabilitado para todos os usuários**
> - Solicitações de tempo de folga: **o recurso está desabilitado para todos os usuários**
>
> Sem essa segunda etapa, os usuários ainda verão o recurso em Shifts e receberão uma mensagem de erro "operação sem suporte" se tentarem usá-lo.

Para ocultar os turnos abertos, solicitações de troca e solicitações de folga no Shifts, use o tipo [](/graph/api/resources/schedule?view=graph-rest-1.0) de recurso agendar API do Graph para definir os seguintes parâmetros ```false``` para cada equipe mapeada para um site WFM do Blue Yonder:

- Turnos abertos: ```openShiftsEnabled```
- Solicitações de troca:  ```swapShiftsRequestsEnabled```
- Solicitações de tempo de folga: ```timeOffRequestsEnabled```

Para ocultar solicitações de turnos abertos em Turnos,  vá para Configurações turnos e, em seguida, desativar a **configuração Abrir turnos**.

## <a name="if-you-need-to-make-changes-to-a-connection"></a>Se você precisar fazer alterações em uma conexão
<a name="update_connection"> </a>

Depois que uma conexão é configurada, você usa o PowerShell para fazer alterações nele. Por exemplo, você pode atualizar configurações de sincronização, mapeamentos de equipe e desabilitar a sincronização de uma conexão. Para obter orientações passo a passo, consulte [Use PowerShell to manage your Shifts connection to Blue Yonder Workforce Management](shifts-connector-powershell-manage.md).

## <a name="related-articles"></a>Artigos relacionados

- [Conectores de turnos](shifts-connectors.md)
- [Use o PowerShell para gerenciar sua conexão shifts com o Gerenciamento de Força de Trabalho de Blue Yonder](shifts-connector-powershell-manage.md)
- [Gerenciar o aplicativo Shifts no Teams](manage-the-shifts-app-for-your-organization-in-teams.md)
