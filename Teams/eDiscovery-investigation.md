---
title: Conduzir uma investigação de Descoberta EDiscovery de conteúdo
author: markjjo
ms.author: markjjo
manager: laurawi
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- SPO_Content
ms.reviewer: anwara
search.appverid: MET150
f1.keywords:
- NOCSH
description: Saiba o que fazer quando precisar executar a Descoberta Eletrônica, como quando precisar enviar todas as Informações Armazenadas Eletronicamente para procedimentos legais.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ca4e85be70ce85d8e35c743275c9f3689061bcda
ms.sourcegitcommit: c8951fe3504c1776d7aec14b79605aaf5d317e7f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/08/2021
ms.locfileid: "61331122"
---
# <a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a>Conduzir uma investigação de Descoberta Eletrônica de conteúdo no Microsoft Teams

As grandes empresas geralmente são expostas a processos legais de alta penalidade que exigem o envio de todas as Informações Armazenadas Eletronicamente (ESI). Microsoft Teams conteúdo pode ser pesquisado e usado durante investigações de Descobertas EDiscovery.

## <a name="overview"></a>Visão Geral

Todas as Microsoft Teams 1:1 ou chats de grupo são contadas no diário até as caixas de correio dos respectivos usuários. Todas as mensagens de canal padrão são enviadas para a caixa de correio do grupo que representa a equipe. Os arquivos carregados em canais padrão são abordados na funcionalidade de Descoberta SharePoint Online e OneDrive for Business.

A descoberta de mensagens e arquivos em [canais](private-channels.md) privados funciona de maneira diferente dos canais padrão. Para saber mais, consulte [eDiscovery of private channels](#ediscovery-of-private-channels).

Nem todo Teams conteúdo é eDiscoverable. A tabela a seguir mostra os tipos de conteúdo que você pode pesquisar usando ferramentas de Descoberta Online da Microsoft:

| Tipo de conteúdo | Descoberta eDiscoverable | Observações |
|:--- | :--- |:--- |
|Gravações de áudio | Não | |
|Conteúdo do cartão|Sim|Consulte [Pesquisar conteúdo de cartão](#search-for-card-content) para obter mais informações.|
|Links de chat | Sim | |
|Mensagens de chat | Sim |Isso inclui conteúdo em Teams canais, chats 1:1, chats de grupo 1:N e chats com participantes do usuário convidado.  |
|Trechos de código | Não | |
|Mensagens editadas | Sim | Se o usuário estiver em espera, versões anteriores de mensagens editadas também serão preservadas. |
|Emojis, GIFs e adesivos | Sim | |
|Notificações de feed | Não | |
|Imagens em linha | Sim | |
|Conversas de IM de Reunião | Sim | |
|Metadados<sup>de reunião 1</sup> | Sim |  |
|Nome do canal | Sim | |
|Mensagens de canal privado | Sim | |
|Aspas | Sim | O conteúdo cotado é pesquisável. No entanto, os resultados da pesquisa não indicam que o conteúdo foi citado. |
|Reações (como likes, hearts e outras reações) | Não | |
|Assunto | Sim | |
|Tabelas | Sim | |
|||

<sup>1</sup> Os metadados de reunião (e de chamada) incluem o seguinte:

- Hora de início e término da reunião e duração
- Eventos de participação e saída de reunião para cada participante
- Junções/chamadas VOIP
- Insições anônimas
- Inserções de usuário federado
- Insições de usuário convidado

  A imagem mostra um exemplo de metadados de reunião.

  > [!div class="mx-imgBorder"]
  > ![A imagem é dos metadados de reunião de registros CVR.](media/conversationOption3.png)

Veja um exemplo de uma conversa de IM entre participantes durante a reunião.

![Conversa entre participantes no Teams.](media/MeetingIMConversations.png)

> [!div class="mx-imgBorder"]
> ![Conversa entre participantes nos resultados da pesquisa de Descobertas EDiscovery.](media/MeetingImConversation2.png)

Para obter mais informações sobre como conduzir uma investigação de Descoberta eDiscovery, consulte [Get started with Core eDiscovery](/microsoft-365/compliance/get-started-core-ediscovery).

Microsoft Teams dados serão exibidos como IM ou Conversas na saída de exportação Excel eDiscovery. Você pode abrir o `.pst` arquivo em Outlook exibir essas mensagens depois de exportá-las.

Ao exibir o arquivo .pst para a equipe, todas as conversas estão localizadas na pasta Chat de Equipe em Histórico de Conversas. O título da mensagem contém o nome da equipe e o nome do canal. Por exemplo, a imagem abaixo mostra uma mensagem de Bob que Project canal padrão 7 da equipe de Especificações de Manufatura.

![Captura de tela de uma pasta de bate-papo da equipe na caixa de correio de um usuário no Outlook.](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

Chats privados na caixa de correio de um usuário são armazenados na pasta Chat de Equipe em Histórico de Conversas.

## <a name="ediscovery-of-private-channels"></a>Descoberta eDiscover de canais privados

Os registros das mensagens enviadas em um canal privado são entregues na caixa de correio de todos os membros do canal privado, e não em uma caixa de correio de grupo. Os títulos dos registros são formatados para indicar de qual canal privado eles foram enviados.

Como cada canal privado tem seu próprio site SharePoint separado do site de equipe pai, os arquivos em um canal privado são gerenciados independentemente da equipe pai.

Teams não dá suporte à pesquisa de Descoberta Online de um único canal dentro de uma equipe, portanto, toda a equipe deve ser pesquisada. Para executar uma pesquisa de Descoberta Eletrônico de conteúdo em um canal privado, pesquise pela equipe, o conjunto de sites associado ao canal privado (para incluir arquivos) e caixas de correio de membros do canal privado (para incluir mensagens).

Use as etapas a seguir para identificar arquivos e mensagens em um canal privado para incluir em sua pesquisa de Descoberta Online.

### <a name="include-private-channel-files-in-an-ediscovery-search"></a>Incluir arquivos de canal privado em uma pesquisa de Descoberta Online

Antes de executar essas etapas, instale o Shell SharePoint [Gerenciamento Online e conecte-se ao SharePoint Online.](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

1. Execute o seguinte para obter uma lista de todos os SharePoint de sites associados a canais privados na equipe.

    ```PowerShell
    Get-SPOSite
    ```

2. Execute o seguinte script do PowerShell para obter uma lista de todas as URLs do conjunto de sites SharePoint associadas a canais privados na equipe e à ID do grupo de equipe pai.

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url}
    ```

3. Para cada ID de equipe ou grupo, execute o seguinte script do PowerShell para identificar todos os sites de canal particular relevantes, onde está a ID de `$groupID` grupo da equipe.

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```
> [!NOTE]
> SharePoint sites para canais privados criados após 28 de junho de 2021 usam o valor da ID do modelo `teamchannel#1` personalizado. Portanto, para canais privados criados após essa data, use o valor `teamchannel#1` ao executar os dois scripts anteriores.

### <a name="include-private-channel-messages-in-an-ediscovery-search"></a>Incluir mensagens de canal privado em uma pesquisa de Descoberta Online

Antes de executar essas etapas, certifique-se de ter a versão mais recente [do módulo Teams PowerShell](teams-powershell-overview.md) instalado.

1. Execute o seguinte comando para obter uma lista de canais privados na equipe.

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```

2. Execute o seguinte comando para obter uma lista de membros do canal privado.

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```

3. Inclua as caixas de correio de todos os membros de cada canal privado na equipe como parte de sua consulta de pesquisa de Descoberta [Eletrônico.](/microsoft-365/compliance/search-for-content-in-core-ediscovery)

## <a name="search-for-content-for-guest-users"></a>Pesquisar conteúdo para usuários convidados

Você pode usar as ferramentas de Descoberta Online para pesquisar Teams conteúdo relacionado aos usuários convidados em sua organização. Teams conteúdo de chat associado a um usuário convidado é preservado em um local de armazenamento baseado em nuvem e pode ser pesquisado para usar a Descoberta Virtual. Isso inclui a pesquisa de conteúdo em conversas de chat 1:1 e 1:N nas quais um usuário convidado é um participante com outros usuários em sua organização. Você também pode pesquisar mensagens de canal privado nas quais um usuário convidado é um participante e pesquisar conteúdo em conversas de chat de *convidado:convidado,* onde os únicos participantes são usuários convidados.

Para pesquisar conteúdo para usuários convidados:

1. Conexão ao PowerShell do Azure AD. Para obter instruções, consulte a seção "Conexão com o Azure Active Directory PowerShell" no Conexão para Microsoft 365 [com o PowerShell](/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module). Certifique-se de concluir a Etapa 1 e a Etapa 2 no tópico anterior.

2. Depois de se conectar com êxito ao Azure AD PowerShell, execute o seguinte comando para exibir o nome principal do usuário (UPN) para todos os usuários convidados em sua organização. Você precisa usar o UPN do usuário convidado ao criar a pesquisa na etapa 4.

   ```powershell
   Get-AzureADUser -Filter "userType eq 'Guest'" -All $true | FL UserPrincipalName
   ```

   > [!TIP]
   > Em vez de exibir uma lista de nomes principais do usuário na tela do computador, você pode redirecionar a saída do comando para um arquivo de texto. Você pode fazer isso de acordo `> filename.txt` com o comando anterior. O arquivo de texto com os nomes principais do usuário será salvo na pasta atual.

3. Em uma janela Windows PowerShell, conecte-se ao Centro de Conformidade e Segurança & PowerShell. Para obter instruções, [consulte Conexão Segurança & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell). Você pode se conectar ou sem usar a autenticação multifator.

4. Crie uma pesquisa de conteúdo que pesquise todo o conteúdo (como mensagens de chat e mensagens de email) na qual o usuário convidado especificado era um participante executando o comando a seguir.

   ```powershell
   New-ComplianceSearch <search name> -ExchangeLocation <guest user UPN>  -AllowNotFoundExchangeLocationsEnabled $true -IncludeUserAppContent $true
   ```

   Por exemplo, para pesquisar conteúdo associado à usuária convidada Sara Davis, execute o seguinte comando.

   ```powershell
   New-ComplianceSearch "Sara Davis Guest User" -ExchangeLocation "sara.davis_hotmail.com#EXT#@contoso.onmicrosoft.com" -AllowNotFoundExchangeLocationsEnabled $true -IncludeUserAppContent $true
   ```

    Para obter mais informações sobre como usar o PowerShell para criar pesquisas de conteúdo, consulte [New-ComplianceSearch](/powershell/module/exchange/new-compliancesearch).

5. Execute o seguinte comando para iniciar a pesquisa de conteúdo criada na etapa 4:

   ```powershell
   Start-ComplianceSearch <search name>
   ```

6. Vá até [https://compliance.microsoft.com](https://compliance.microsoft.com) e clique em Mostrar toda a **pesquisa**  >  **de conteúdo.**

7. Na lista de pesquisas, selecione a pesquisa que você criou na etapa 4 para exibir a página de sobrevoo.

8. Na página de sobrevoo, você pode fazer as seguintes coisas:

   - Clique **em Exibir resultados** para exibir os resultados da pesquisa e visualizar o conteúdo.

   - Ao lado do **campo Consulta,** clique em **Editar** para editar e, em seguida, reprise a pesquisa. Por exemplo, você pode adicionar uma consulta de pesquisa para restringir os resultados.

   - Clique **em Exportar resultados** para exportar e baixar os resultados da pesquisa.

## <a name="search-for-card-content"></a>Pesquisar conteúdo de cartão

O conteúdo do cartão gerado por aplicativos Teams canais, chats 1:1 e chats 1xN é armazenado em caixas de correio e pode ser pesquisado. Um *cartão* é um contêiner de interface do usuário para partes curtas de conteúdo. Os cartões podem ter várias propriedades e anexos e podem incluir botões que podem disparar ações de cartão. Para obter mais informações, consulte [Cards](/microsoftteams/platform/task-modules-and-cards/what-are-cards)

Como outros Teams conteúdo, onde o conteúdo do cartão é armazenado é baseado em onde o cartão foi usado. O conteúdo dos cartões usados em um canal Teams é armazenado na caixa de correio Teams grupo. O conteúdo do cartão para chats 1:1 e 1xN são armazenados nas caixas de correio dos participantes do chat.

Para pesquisar o conteúdo do cartão, você pode usar as `kind:microsoftteams` condições de `itemclass:IPM.SkypeTeams.Message` pesquisa ou. Ao analisar os resultados da pesquisa, o conteúdo do cartão gerado por bots em um canal Teams tem a propriedade de email **Remetente/Autor** como , onde é o nome do aplicativo que gerou o conteúdo do `<appname>@teams.microsoft.com` `appname` cartão. Se o conteúdo do cartão foi gerado por um usuário, o valor de **Remetente/Autor** identifica o usuário.

Ao exibir o conteúdo do cartão nos resultados da pesquisa de conteúdo, o conteúdo aparece como um anexo à mensagem. O anexo é chamado `appname.html` , onde é o nome do aplicativo que gerou o conteúdo do `appname` cartão. As capturas de tela a seguir mostram como o conteúdo do cartão (para um aplicativo chamado Asana) aparece no Teams e nos resultados de uma pesquisa.

**Conteúdo do cartão em Teams**

![Conteúdo do cartão Teams mensagem de canal.](media/CardContentTeams.png)

**Conteúdo do cartão nos resultados da pesquisa**
  
![Mesmo conteúdo de cartão nos resultados de uma pesquisa de conteúdo.](media/CardContentEdiscoverySearchResults.png)

> [!NOTE]
> Para exibir imagens do conteúdo do cartão nos resultados da pesquisa neste momento (como as marcas de seleção na captura de tela anterior), você precisa estar Teams no Teams (em uma guia diferente na mesma sessão do navegador que você usa para exibir os resultados da https://teams.microsoft.com) pesquisa. Caso contrário, os espaço reservados de imagem serão exibidos.

## <a name="related-topics"></a>Tópicos relacionados

- [Microsoft 365 eDiscovery](/microsoft-365/compliance/ediscovery)
- [Começar a trabalhar com a Descoberta Básica de EDiscovery](/microsoft-365/compliance/get-started-core-ediscovery)
- [Teams fluxo de trabalho no Advanced eDiscovery](/microsoft-365/compliance/teams-workflow-in-advanced-ediscovery)
- [Visão Geral do PowerShell do Teams](teams-powershell-overview.md)
