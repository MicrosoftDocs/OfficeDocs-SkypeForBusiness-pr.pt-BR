---
title: Usar o assistente do conector do Shifts para conectar o Shifts ao Blue Yonder Workforce Management
author: lanachin
ms.author: v-lanachin
ms.reviewer: ''
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Saiba como usar o assistente de conector do Shifts para integrar o Shifts no Teams com o Blue Yonder Workforce Management.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4041b0909a3c5e8f1aa256fd2ec662030548343c
ms.sourcegitcommit: bf0071417188b33fc23e2a420187da5024d4bd40
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/20/2022
ms.locfileid: "64593629"
---
# <a name="use-the-shifts-connector-wizard-to-connect-shifts-to-blue-yonder-workforce-management"></a>Usar o assistente do conector do Shifts para conectar o Shifts ao Blue Yonder Workforce Management

## <a name="overview"></a>Visão Geral

O assistente do conector do Shifts no Centro de administração do Microsoft 365 permite integrar o aplicativo Shifts no Microsoft Teams com o sistema WFM (gerenciamento de força de trabalho). Depois de configurar uma conexão, os trabalhadores da linha de frente podem exibir e gerenciar diretamente suas agendas no sistema WFM de dentro do Shifts.

O assistente configura o conector do Shifts, cria uma conexão com o sistema WFM e aplica as configurações de sincronização e os mapeamentos de equipe que você escolher. As configurações de sincronização determinam as informações de agendamento sincronizadas entre o sistema WFM e o Shifts. Os mapeamentos de equipe definem a relação de sincronização entre seus sites do WFM e as equipes Teams. Você pode mapear para equipes existentes e novas equipes.

Você pode configurar várias conexões, cada uma com configurações de sincronização diferentes. Por exemplo, se sua organização tiver vários locais com requisitos de agendamento diferentes, crie uma conexão com configurações de sincronização exclusivas para cada local. Tenha em mente que um site WFM só pode ser mapeado para uma equipe em um determinado momento. Se um site WFM já estiver mapeado para uma equipe, ele não poderá ser mapeado para outra equipe.

Com o sistema WFM como o sistema de registro, os trabalhadores da linha de frente podem ver e trocar turnos, gerenciar sua disponibilidade e solicitar folga em turnos em seus dispositivos. Os gerentes de linha de frente podem continuar a usar o sistema WFM para configurar agendamentos.

## <a name="integrate-shifts-with-blue-yonder-workforce-management"></a>Integrar o Shifts ao Blue Yonder Workforce Management

Atualmente, o assistente dá suporte ao [conector Microsoft Teams Shifts para o Blue Yonder](shifts-connectors.md#microsoft-teams-shifts-connector-for-blue-yonder). Esse conector permite integrar o Shifts ao Blue Yonder Workforce Management (Blue Yonder WFM) para gerenciar suas agendas e mantê-las atualizadas. Neste artigo, explicaremos como executar o assistente para configurar uma conexão com o Blue Yonder WFM por meio do conector.

> [!NOTE]
> Você também pode usar o PowerShell para integrar o Shifts ao Blue Yonder WFM. Para saber mais, confira [Usar o PowerShell para conectar o Shifts ao Blue Yonder Workforce Management](shifts-connector-blue-yonder-powershell-setup.md).

## <a name="before-you-begin"></a>Antes de você começar

Você deve ser um Microsoft 365 administrador global para executar o assistente.

### <a name="prerequisites"></a>Pré-requisitos
<a name="prerequisites"> </a>
[!INCLUDE [shifts-connector-prerequisites](../../includes/shifts-connector-prerequisites.md)]

- As equipes que você deseja mapear não têm agendas. Se uma equipe tiver um agendamento existente, [remova](#remove-schedules-from-teams-you-want-to-map) o agendamento da equipe antes de mapear um site WFM do Remetente Azul para ela. Caso contrário, você verá turnos duplicados.

## <a name="remove-schedules-from-teams-you-want-to-map"></a>Remover agendas das equipes que você deseja mapear
<a name="remove_schedules"> </a>

> [!NOTE]
> Conclua esta etapa se você estiver mapeando sites WFM do Blue Yonder para equipes existentes que têm agendamentos. Se você estiver mapeando para equipes que não têm agendas ou se estiver criando novas equipes para as qual mapear, ignore esta etapa.

Use o PowerShell para remover agendas das equipes.

1. Primeiro, você precisará instalar os módulos do PowerShell e se configurar. Siga as etapas para [configurar seu ambiente](shifts-connector-powershell-manage.md#set-up-your-environment).
1. Execute o seguinte comando:

    ```powershell
    Remove-CsTeamsShiftsScheduleRecord -TeamId <Teams team ID> -DateRangeStartDate <start time> -DateRangeEndDate <end time> -ClearSchedulingGroup:$false -EntityType <the scenario entities that you want to remove, the format is @(scenario1, scenario2, ...)> -DesignatedActorId <Teams team owner ID>
    ```

    Para obter uma lista de cenários para o `EntityType` parâmetro, execute [Get-CsTeamsShiftsConnectionConnector](/powershell/module/teams/get-csteamsshiftsconnectionconnector?view=teams-ps). Os dados de agendamento serão removidos para o intervalo de data e hora que você especificar.

Para saber mais, confira [Remove-CsTeamsShiftsScheduleRecord](/powershell/module/teams/remove-csteamsshiftsschedulerecord?view=teams-ps).

## <a name="run-the-wizard"></a>Executar o assistente

### <a name="get-started"></a>Introdução

1. No painel de navegação [esquerdo do Centro de administração do Microsoft 365](https://admin.microsoft.com/), escolha Configurar **e vá para** a seção **Aplicativos e email**.
1. Selecione Conexão **seu sistema de gerenciamento de força de trabalho**. Aqui, você pode saber mais sobre os conectores do Shifts e a experiência de trabalho e gerente de linha de frente ao conectar o Shifts ao sistema WFM.
    :::image type="content" source="../../media/shifts-connector-wizard-get-started.png" alt-text="Captura de tela da página de detalhes do assistente do conector shifts no Centro de administração do Microsoft 365." lightbox="../../media/shifts-connector-wizard-get-started.png":::
1. Quando estiver pronto, selecione **Introdução**.
1. Selecione **Avançar** para criar uma conexão WFM de Remetente Azul.

### <a name="enter-connection-details"></a>Inserir detalhes da conexão
<a name="connection_details"> </a>

1. Na página Detalhes da conexão, dê um nome exclusivo à conexão. Ele não pode ter mais de 128 caracteres ou ter caracteres especiais.
    :::image type="content" source="../../media/shifts-connector-wizard-connection-details.png" alt-text="Captura de tela da página Detalhes da conexão do assistente, mostrando as configurações de conexão." lightbox="../../media/shifts-connector-wizard-connection-details.png":::
1. Insira o nome da conta de serviço blue yonder WFM e as URLs de serviço e senha.
1. Quando terminar, selecione Avançar **para** testar a conexão com as configurações inseridas.

### <a name="choose-sync-settings"></a>Escolher configurações de sincronização
<a name="sync"> </a>

Na página Configurações de sincronização, você escolhe as informações a serem sincronizadas do WFM do Remetente Azul para Shifts, a frequência de sincronização e se os usuários do Shifts podem fazer alterações nos dados.

1. Insira sua Microsoft 365 do sistema.
    :::image type="content" source="../../media/shifts-connector-wizard-sync-settings.png" alt-text="Captura de tela da página Configurações de sincronização do assistente, mostrando as configurações de sincronização." lightbox="../../media/shifts-connector-wizard-sync-settings.png":::
<a name="email"> </a>
1. Em **Destinatários de notificação por** email, escolha quem recebe notificações por email sobre essa conexão. Você pode adicionar usuários e grupos individuais. As notificações por email contêm informações sobre o status da configuração de conexão e quaisquer problemas ou erros que possam ocorrer após a configuração da conexão.
1. Escolha as configurações de sincronização:
    1. Em **Agenda e turnos**, escolha os dados WFM do Remetente Azul que os usuários do Shifts podem ver ou alterar e, em seguida, defina a frequência de sincronização.
    2. Em **Solicitações**, escolha os tipos de solicitações que os usuários do Shifts podem ver e criar.

    > [!IMPORTANT]
    > Se você escolher qualquer uma das opções a seguir para desabilitar turnos abertos, solicitações de turno abertas, solicitações de permuta ou solicitações de folga, há outra etapa que você precisa fazer para ocultar a funcionalidade no Shifts.
    >
    > - Turnos abertos: **os usuários de turnos não verão dados WFM do Remetente Azul**
    > - Solicitações de **permuta: o recurso está desabilitado para todos os usuários**
    > - Solicitações de folga: **o recurso está desabilitado para todos os usuários**
    >
    > Depois de executar o assistente, siga as etapas na seção Desabilitar turnos abertos, abrir solicitações de [turnos,](#disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests) solicitações de permuta e solicitações de folga posteriormente neste artigo.
 
1. Quando terminar de escolher as configurações, selecione **Criar conexão**.

### <a name="map-blue-yonder-workforce-management-sites-to-teams"></a>Mapear sites do Blue Yonder Workforce Management para equipes
<a name="sites"> </a>

Escolha os sites WFM do Remetente Azul que você deseja conectar ao Shifts. Você pode selecionar até 100 sites.

:::image type="content" source="../../media/shifts-connector-wizard-sites.png" alt-text="Captura de tela do assistente, mostrando a lista de sites WFM do Remetente Azul." lightbox="../../media/shifts-connector-wizard-sites.png":::
<a name="mapping"> </a>
<a name="search_teams"> </a> Em seguida, mapeie cada site WFM do Remetente Azul que você selecionou para uma equipe no Teams. Você pode mapear um site para uma equipe existente ou criar uma nova equipe.
:::image type="content" source="../../media/shifts-connector-wizard-search-team.png" alt-text="Captura de tela do painel mostrando a opção de equipe de pesquisa e crie uma nova opção de equipe." lightbox="../../media/shifts-connector-wizard-search-team.png":::
#### <a name="to-map-a-site-to-an-existing-team"></a>Para mapear um site para uma equipe existente

1. Selecione o nome do site.
2. No painel, pesquise a equipe e selecione-a. Tenha em mente que as equipes que já estão mapeadas para um site nessa conexão não aparecem na pesquisa.
3. Escolha o fuso horário e a cidade mais próxima.
4. Selecione **Salvar** e, em seguida, **selecione Avançar**.

#### <a name="to-map-a-site-to-a-new-team"></a>Para mapear um site para uma nova equipe

1. Selecione o nome do site.
2. No painel, escolha **Criar uma nova equipe**. Você será direcionado para uma nova guia no navegador, na qual poderá criar uma nova equipe no Centro de administração do Microsoft 365.
    1. Insira um nome e uma descrição opcional para a equipe.
    1. Adicione um ou mais proprietários de equipe. Certifique-se de adicionar a Microsoft 365 do sistema como proprietário.
    1. Adicionar membros da equipe.
    1. Adicione um endereço de email de equipe e escolha uma configuração de privacidade.
    1. Examine suas configurações e escolha **Adicionar equipe**. Quando sua equipe for criada, escolha **Fechar**.
3. Voltar ao assistente, pesquise e selecione a nova equipe que você criou.
4. Escolha o fuso horário e a cidade mais próxima.
5. Selecione **Salvar** e, em seguida, **selecione Avançar**.

### <a name="review-and-finish"></a>Revisar e concluir

Examine suas configurações. Se você precisar fazer alterações em qualquer mapeamento de equipe, escolha **Editar** para fazer isso. Quando estiver pronto, selecione **Concluir**.

:::image type="content" source="../../media/shifts-connector-wizard-review.png" alt-text="Captura de tela da página Revisão do assistente, mostrando mapeamentos." lightbox="../../media/shifts-connector-wizard-review.png":::

Você verá uma mensagem para confirmar que recebemos sua solicitação junto com uma ID de operação. Anote a ID da operação. Você precisará dele para verificar o status de configuração da conexão.

:::image type="content" source="../../media/shifts-connector-wizard-operation-id.png" alt-text="Captura de tela da página do assistente mostrando a mensagem de confirmação e a ID da operação." lightbox="../../media/shifts-connector-wizard-operation-id.png":::

O assistente inicia o processo para configurar a conexão e mapear os sites para as equipes selecionadas. Esse processo pode levar algum tempo para ser concluído. Os destinatários escolhidos receberão notificações por email sobre o status da instalação.

Selecione **Concluído** para sair do assistente.

Você está a caminho, mas ainda não acabou! Verifique seu email. Você receberá uma confirmação de que recebemos sua solicitação juntamente com um [link](shifts-connector-powershell-manage.md#check-connection-setup-status) para como você pode verificar o status da configuração.

> [!NOTE]
> Se ocorrer um problema ou erro em uma conexão após a configuração, você será notificado por email. Siga as instruções no email para solucionar o problema.

## <a name="disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests"></a>Desabilitar turnos abertos, abrir solicitações de turnos, solicitações de permuta e solicitações de folga

> [!IMPORTANT]
> Siga estas etapas somente se você escolher qualquer uma das opções a seguir para desabilitar turnos abertos, abrir solicitações de turno, solicitações de permuta ou solicitações de folga no assistente. A conclusão desta etapa oculta a funcionalidade em Turnos.
>
> - Turnos abertos: **os usuários de turnos não verão dados WFM do Remetente Azul**
> - Solicitações de **permuta: o recurso está desabilitado para todos os usuários**
> - Solicitações de folga: **o recurso está desabilitado para todos os usuários**
>
> Sem essa segunda etapa, os usuários ainda verão a funcionalidade no Shifts e receberão uma mensagem de erro de "operação sem suporte" se tentarem usá-la.

Para ocultar turnos abertos, solicitações de permuta e solicitações de folga no Shifts, use o tipo de recurso de agendamento API do Graph para [definir os seguintes](/graph/api/resources/schedule?view=graph-rest-1.0) parâmetros ```false``` para cada equipe mapeada para um site WFM do Remetente Azul:

- Abrir turnos: ```openShiftsEnabled```
- Solicitações de permuta:  ```swapShiftsRequestsEnabled```
- Solicitações de folga: ```timeOffRequestsEnabled```

Para ocultar solicitações de turnos abertos em Turnos,  vá para Configurações shifts e desative a **configuração Abrir turnos**.

## <a name="if-you-need-to-make-changes-to-a-connection"></a>Se você precisar fazer alterações em uma conexão
<a name="update_connection"> </a>

Depois que uma conexão for configurada, você usará o PowerShell para fazer alterações nela. Por exemplo, você pode atualizar configurações de sincronização, mapeamentos de equipe e desabilitar a sincronização para uma conexão. Para obter diretrizes passo a passo, [consulte Usar o PowerShell para gerenciar sua conexão shifts com o Blue Yonder Workforce Management](shifts-connector-powershell-manage.md).

## <a name="related-articles"></a>Artigos relacionados

- [Conectores de turnos](shifts-connectors.md)
- [Usar o PowerShell para gerenciar sua conexão shifts com o Blue Yonder Workforce Management](shifts-connector-powershell-manage.md)
- [Gerenciar o aplicativo Shifts no Teams](manage-the-shifts-app-for-your-organization-in-teams.md)
