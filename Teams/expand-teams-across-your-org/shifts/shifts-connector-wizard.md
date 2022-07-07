---
title: Use o assistente do conector Shifts para conectar o Shifts ao Blue Yonder Workforce Management
author: lanachin
ms.author: v-lanachin
ms.reviewer: ''
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Saiba como usar o assistente de conector do Shifts para integrar o Shifts no Teams ao Blue Yonder Workforce Management.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: de511df118e1c5e6d62e0bed8cd076a7481b3407
ms.sourcegitcommit: 90f03a841f8ca33092dce65c543357c7c2f7b82a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/06/2022
ms.locfileid: "66647807"
---
# <a name="use-the-shifts-connector-wizard-to-connect-shifts-to-blue-yonder-workforce-management"></a>Use o assistente do conector Shifts para conectar o Shifts ao Blue Yonder Workforce Management

## <a name="overview"></a>Visão Geral

O assistente do conector shifts no Centro de administração do Microsoft 365 permite integrar o aplicativo Shifts no Microsoft Teams ao seu sistema de gerenciamento de força de trabalho (WFM). Depois de configurar uma conexão, os trabalhadores da linha de frente podem exibir e gerenciar diretamente suas agendas em seu WFM de dentro do Shifts.

O assistente configura o conector do Shifts, cria uma conexão com seu sistema WFM e aplica as configurações de sincronização e os mapeamentos de equipe que você escolher. As configurações de sincronização determinam as informações de agendamento sincronizadas entre o WFM e o Shifts. Os mapeamentos de equipe definem a relação de sincronização entre suas WFM e equipes no Teams. Você pode mapear para equipes existentes e novas equipes.

Você pode configurar várias conexões, cada uma com configurações de sincronização diferentes. Por exemplo, se sua organização tiver vários locais com requisitos de agendamento diferentes, crie uma conexão com configurações de sincronização exclusivas para cada local. Tenha em mente que uma instância WFM pode ser mapeada apenas para uma equipe em um determinado momento. Se uma WFM instância já estiver mapeada para uma equipe, ela não poderá ser mapeada para outra equipe.

Com seu WFM como o sistema de registro, os trabalhadores da linha de frente podem ver e trocar turnos, gerenciar sua disponibilidade e solicitar folga em turnos em seus dispositivos. Os gerentes de linha de frente podem continuar a usar seu WFM para configurar agendas.

## <a name="integrate-shifts-with-blue-yonder-workforce-management"></a>Integrar o Shifts ao Blue Yonder Workforce Management

Atualmente, o assistente dá suporte ao [conector do Microsoft Teams Shifts para o Blue Yonder](shifts-connectors.md#microsoft-teams-shifts-connector-for-blue-yonder). Esse conector permite integrar o Shifts ao Blue Yonder Workforce Management (Blue Yonder WFM) para gerenciar suas agendas e mantê-las atualizadas. Neste artigo, explicaremos como executar o assistente para configurar uma conexão com o Blue Yonder WFM por meio do conector.

> [!NOTE]
> Você também pode usar o PowerShell para integrar o Shifts ao Blue Yonder WFM. Para saber mais, [confira Usar o PowerShell para conectar o Shifts ao Blue Yonder Workforce Management](shifts-connector-blue-yonder-powershell-setup.md).

## <a name="before-you-begin"></a>Antes de você começar

Você deve ser um administrador global do Microsoft 365 para executar o assistente.

### <a name="prerequisites"></a>Pré-requisitos
<a name="prerequisites"> </a>
[!INCLUDE [shifts-connector-prerequisites](../../includes/shifts-connector-prerequisites.md)]

- As equipes que você deseja mapear não têm agendas. Se uma equipe tiver um agendamento existente, [remova](#remove-schedules-from-teams-you-want-to-map) o agendamento da equipe antes de mapear uma instância do Blue Yonder WFM para ela. Caso contrário, você verá turnos duplicados.

## <a name="remove-schedules-from-teams-you-want-to-map"></a>Remover agendas das equipes que você deseja mapear
<a name="remove_schedules"> </a>

> [!NOTE]
> Conclua esta etapa se você estiver mapeando instâncias do Blue Yonder WFM para equipes existentes que têm agendamentos. Se você estiver mapeando para equipes que não têm agendas ou se estiver criando novas equipes para as qual mapear, ignore esta etapa.

Use o PowerShell para remover agendas das equipes.

1. Primeiro, você precisará instalar os módulos do PowerShell e se configurar. Siga as etapas para [configurar seu ambiente](shifts-connector-powershell-manage.md#set-up-your-environment).
1. Execute o seguinte comando:

    ```powershell
    Remove-CsTeamsShiftsScheduleRecord -TeamId <Teams team ID> -DateRangeStartDate <start time> -DateRangeEndDate <end time> -ClearSchedulingGroup:$false -EntityType <the scenario entities that you want to remove, the format is @(scenario1, scenario2, ...)> -DesignatedActorId <Teams team owner ID>
    ```

    Para obter uma lista de cenários para o `EntityType` parâmetro, execute [Get-CsTeamsShiftsConnectionConnector](/powershell/module/teams/get-csteamsshiftsconnectionconnector). Os dados de agendamento serão removidos para o intervalo de data e hora que você especificar.

Para saber mais, confira [Remove-CsTeamsShiftsScheduleRecord](/powershell/module/teams/remove-csteamsshiftsschedulerecord).

## <a name="run-the-wizard"></a>Executar o assistente

### <a name="get-started"></a>Introdução

1. No painel de navegação [esquerdo do Centro de administração do Microsoft 365](https://admin.microsoft.com/), escolha Configurar **e vá para** a seção **Aplicativos e email**.
1. Selecione **Conectar seu sistema de gerenciamento de força de trabalho**. Aqui, você pode saber mais sobre os conectores do Shifts e a experiência de trabalho e gerente de linha de frente ao conectar o Shifts ao seu sistema WFM.
    :::image type="content" source="../../media/shifts-connector-wizard-get-started.png" alt-text="Captura de tela da página de detalhes do assistente do conector shifts no Centro de administração do Microsoft 365." lightbox="../../media/shifts-connector-wizard-get-started.png":::
1. Quando estiver pronto, selecione **Introdução**.
1. Selecione **Avançar** para criar uma conexão de WFM Azul.

### <a name="enter-connection-details"></a>Inserir detalhes da conexão
<a name="connection_details"> </a>

1. Na página Detalhes da conexão, dê um nome exclusivo à conexão. Ele não pode ter mais de 128 caracteres ou ter caracteres especiais.
    :::image type="content" source="../../media/shifts-connector-wizard-connection-details.png" alt-text="Captura de tela da página Detalhes da conexão do assistente, mostrando as configurações de conexão." lightbox="../../media/shifts-connector-wizard-connection-details.png":::
1. Insira o nome da conta WFM de serviço e as URLs de serviço e senha do Blue Yonder.
1. Quando terminar, selecione Avançar **para** testar a conexão com as configurações inseridas.

### <a name="choose-sync-settings"></a>Escolher configurações de sincronização
<a name="sync"> </a>

Na página Configurações de sincronização, você escolhe as informações a serem sincronizadas do Blue Yonder WFM para Shifts, a frequência de sincronização e se os usuários do Shifts podem fazer alterações nos dados.

1. Insira sua conta de sistema do Microsoft 365.
    :::image type="content" source="../../media/shifts-connector-wizard-sync-settings.png" alt-text="Captura de tela da página Configurações de sincronização do assistente, mostrando as configurações de sincronização." lightbox="../../media/shifts-connector-wizard-sync-settings.png":::
<a name="email"> </a>
1. Em **Destinatários de notificação por** email, escolha quem recebe notificações por email sobre essa conexão. Você pode adicionar usuários e grupos individuais. As notificações por email contêm informações sobre o status da configuração de conexão e quaisquer problemas ou erros que possam ocorrer após a configuração da conexão.
1. Escolha as configurações de sincronização:
    1. Em **Agenda e turnos**, escolha os dados de WFM que os usuários do Shifts podem ver ou alterar e, em seguida, defina a frequência de sincronização.
    2. Em **Solicitações**, escolha os tipos de solicitações que os usuários do Shifts podem ver e criar.

    > [!IMPORTANT]
    > Se você escolher qualquer uma das opções a seguir para desabilitar turnos abertos, solicitações de turno abertas, solicitações de permuta ou solicitações de folga, há outra etapa que você precisa fazer para ocultar a funcionalidade no Shifts.
    >
    > - Turnos abertos: **os usuários de turnos não verão dados de WFM Blue Yonder**
    > - Solicitações de **permuta: o recurso está desabilitado para todos os usuários**
    > - Solicitações de folga: **o recurso está desabilitado para todos os usuários**
    >
    > Depois de executar o assistente, siga as etapas na seção Desabilitar turnos abertos, abrir solicitações de [turnos,](#disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests) solicitações de permuta e solicitações de folga posteriormente neste artigo.
 
1. Quando terminar de escolher as configurações, selecione **Criar conexão**.

### <a name="map-blue-yonder-workforce-management-instances-to-teams"></a>Mapear instâncias do Blue Yonder Workforce Management para as equipes
<a name="sites"> </a>

Escolha as instâncias de WFM azul que você deseja conectar ao Shifts e, em seguida, mapeie cada instância para uma equipe no Teams. Você pode mapear até 100 instâncias. Há duas maneiras de fazer isso:

- [Mapear manualmente instâncias para equipes](#manually-map-instances-to-teams)
- [Preparar e carregar um arquivo CSV que define seus mapeamentos](#use-a-csv-file-to-map-instances-to-teams)

#### <a name="manually-map-instances-to-teams"></a>Mapear manualmente instâncias para equipes

Selecione as instâncias que você deseja mapear.

:::image type="content" source="../../media/shifts-connector-wizard-sites.png" alt-text="Captura de tela do assistente mostrando a lista de instâncias de WFM Azul." lightbox="../../media/shifts-connector-wizard-sites.png":::
<a name="mapping"> </a>
<a name="search_teams"> </a> Em seguida, mapeie cada instância para uma equipe no Teams. Você pode mapear uma instância para uma equipe existente ou criar uma nova equipe.
:::image type="content" source="../../media/shifts-connector-wizard-search-team.png" alt-text="Captura de tela do painel mostrando a opção de equipe de pesquisa e crie uma nova opção de equipe." lightbox="../../media/shifts-connector-wizard-search-team.png":::

##### <a name="to-map-an-instance-to-an-existing-team"></a>Para mapear uma instância para uma equipe existente

1. Selecione o nome da instância.
2. No painel, pesquise a equipe e selecione-a. Tenha em mente que as equipes que já estão mapeadas para uma instância nessa conexão não aparecem na pesquisa.
3. Escolha o fuso horário e a cidade mais próxima.
4. Selecione **Salvar** e, em seguida, **selecione Avançar**.

##### <a name="to-map-an-instance-to-a-new-team"></a>Para mapear uma instância para uma nova equipe

1. Selecione o nome da instância.
2. No painel, escolha **Criar uma nova equipe**. Você será direcionado para uma nova guia no navegador, na qual poderá criar uma nova equipe no Centro de administração do Microsoft 365.
    1. Insira um nome e uma descrição opcional para a equipe.
    1. Adicione um ou mais proprietários de equipe. Certifique-se de adicionar a conta de sistema do Microsoft 365 como proprietário.
    1. Adicionar membros da equipe.
    1. Adicione um endereço de email de equipe e escolha uma configuração de privacidade.
    1. Examine suas configurações e escolha **Adicionar equipe**. Quando sua equipe for criada, escolha **Fechar**.
3. Voltar ao assistente, pesquise e selecione a nova equipe que você criou.
4. Escolha o fuso horário e a cidade mais próxima.
5. Selecione **Salvar** e, em seguida, **selecione Avançar**.

#### <a name="use-a-csv-file-to-map-instances-to-teams"></a>Usar um arquivo CSV para mapear instâncias para equipes

1. Selecione **alternar para o modo em massa**.
1. Selecione **baixar um arquivo de modelo** para baixar um modelo de mapeamento que você pode usar para definir seus mapeamentos.

    :::image type="content" source="../../media/shifts-connector-wizard-mapping-file.png" alt-text="Captura de tela da página Carregar arquivo de mapeamento do assistente." lightbox="../../media/shifts-connector-wizard-mapping-file.png":::

1. Use o modelo para criar o arquivo de mapeamento. Ele contém essas colunas, na ordem a seguir, começando com a primeira coluna. Um asterisco (*) indica uma coluna necessária.

    |Nome da coluna  |Descrição  |
    |---------|---------|
    |**ID da Instância de Remetente Azul*** |A ID da instância WFM Azul.|
    |**Nome da instância de remetente azul**|O nome da instância WFM Azul.|
    |**ID da equipe*** |A ID da equipe.|
    |**Nome da equipe**|O nome da equipe.|
    |**Fuso horário*** |O fuso horário no formato de banco de dados tz. Por exemplo, Europa/Londres.|

    > [!NOTE]
    > Você só precisa preencher as colunas necessárias (ID da Instância do Remetente Azul, ID da Equipe, Fuso Horário) para mapear instâncias para equipes.

    Aqui está um exemplo de como é um arquivo de mapeamento.

    |ID da Instância de Remetente Azul|Nome da instância de remetente azul|ID da equipe|Nome da equipe|Fuso horário|
    |---------|---------|---------|---------|---------|
    |2111|Equipe contoso dos EUA|3a4d78a-2261|Equipe dos EUA|América/Los_Angeles|
    |3212|Equipe da Contoso no Reino Unido|2d1f6c2e-5272|Equipe do Reino Unido|Europa/Londres|
    |4865||bfa6o89e-1328||América/Toronto|

1. Quando você tiver criado o arquivo de mapeamento, selecione **Procurar** para carregá-lo. O assistente valida seu arquivo. Se encontrar erros, você verá uma lista dos erros e uma mensagem solicitando que você os corrija. Caso contrário, você verá uma mensagem para continuar para a próxima etapa.  
1. Selecione **Avançar**.

### <a name="review-and-finish"></a>Revisar e concluir

Examine suas configurações. Se você precisar fazer alterações em qualquer mapeamento de equipe, escolha **Editar** para fazer isso. Quando estiver pronto, selecione **Concluir**.

:::image type="content" source="../../media/shifts-connector-wizard-review.png" alt-text="Captura de tela da página Revisão do assistente, mostrando mapeamentos." lightbox="../../media/shifts-connector-wizard-review.png":::

Você verá uma mensagem para confirmar que recebemos sua solicitação junto com uma ID de operação. Anote a ID da operação. Você precisará dele para verificar o status de configuração da conexão.

:::image type="content" source="../../media/shifts-connector-wizard-operation-id.png" alt-text="Captura de tela da página do assistente mostrando a mensagem de confirmação e a ID da operação." lightbox="../../media/shifts-connector-wizard-operation-id.png":::

O assistente inicia o processo para configurar a conexão e mapear as instâncias para as equipes selecionadas. Esse processo pode levar algum tempo para ser concluído. Os destinatários escolhidos receberão notificações por email sobre o status da instalação.

Selecione **Concluído** para sair do assistente.

Você está a caminho, mas ainda não acabou! Verifique seu email. Você receberá uma confirmação de que recebemos sua solicitação juntamente com um [link](shifts-connector-powershell-manage.md#check-connection-setup-status) para como você pode verificar o status da configuração.

> [!NOTE]
> Se ocorrer um problema ou erro em uma conexão após a configuração, você será notificado por email. Siga as instruções no email para solucionar o problema.

## <a name="disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests"></a>Desabilitar turnos abertos, abrir solicitações de turnos, solicitações de permuta e solicitações de folga

> [!IMPORTANT]
> Siga estas etapas somente se você escolher qualquer uma das opções a seguir para desabilitar turnos abertos, abrir solicitações de turno, solicitações de permuta ou solicitações de folga no assistente. A conclusão desta etapa oculta a funcionalidade em Turnos.
>
> - Turnos abertos: **os usuários de turnos não verão dados de WFM Blue Yonder**
> - Solicitações de **permuta: o recurso está desabilitado para todos os usuários**
> - Solicitações de folga: **o recurso está desabilitado para todos os usuários**
>
> Sem essa segunda etapa, os usuários ainda verão a funcionalidade no Shifts e receberão uma mensagem de erro de "operação sem suporte" se tentarem usá-la.

Para ocultar turnos abertos, solicitações de permuta e solicitações de folga no Shifts, use o [](/graph/api/resources/schedule) tipo de recurso de agendamento API do Graph para definir os seguintes parâmetros ```false``` para cada equipe mapeada para uma instância de WFM Blue Yonder:

- Abrir turnos: ```openShiftsEnabled```
- Solicitações de permuta:  ```swapShiftsRequestsEnabled```
- Solicitações de folga: ```timeOffRequestsEnabled```

Para ocultar solicitações de turnos abertos em Turnos,  vá para Configurações em Turnos e desative a **configuração Abrir turnos**.

## <a name="if-you-need-to-make-changes-to-a-connection"></a>Se você precisar fazer alterações em uma conexão
<a name="update_connection"> </a>

Depois que uma conexão for configurada, você usará o PowerShell para fazer alterações nela. Por exemplo, você pode atualizar configurações de sincronização, mapeamentos de equipe e desabilitar a sincronização para uma conexão. Para obter diretrizes passo a passo, consulte [Usar o PowerShell para gerenciar sua conexão shifts com o Blue Yonder Workforce Management](shifts-connector-powershell-manage.md).

## <a name="related-articles"></a>Artigos relacionados

- [Conectores de turnos](shifts-connectors.md)
- [Use o PowerShell para gerenciar sua conexão shifts com o Blue Yonder Workforce Management](shifts-connector-powershell-manage.md)
- [Gerenciar o aplicativo Turnos no Teams](manage-the-shifts-app-for-your-organization-in-teams.md)
