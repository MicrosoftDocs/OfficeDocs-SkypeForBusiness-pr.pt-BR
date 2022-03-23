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
ms.openlocfilehash: 85124047c5bb894eb4eb4177fad0e0cfee53dfc3
ms.sourcegitcommit: fcac607fb4ad342a0936527f848e04c85f153ba5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/22/2022
ms.locfileid: "63711765"
---
# <a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a>Conduzir uma investigação de Descoberta Eletrônica de conteúdo no Microsoft Teams

As grandes empresas geralmente são expostas a processos legais de alta penalidade que exigem o envio de todas as Informações Armazenadas Eletronicamente (ESI). Microsoft Teams o conteúdo pode ser pesquisado e usado durante investigações de Descobertas EDiscovery.

## <a name="overview"></a>Visão Geral

Todas as Microsoft Teams 1:1 ou chats de grupo são contadas no diário nas caixas de correio dos respectivos usuários. Todas as mensagens de canal padrão são enviadas para a caixa de correio do grupo que representa a equipe. Os arquivos carregados em canais padrão são abordados na funcionalidade de Descoberta SharePoint Online e OneDrive for Business.

A descoberta de mensagens e arquivos [em canais privados](private-channels.md) funciona de maneira diferente dos canais padrão. Para saber mais, consulte [eDiscovery of private channels](#ediscovery-of-private-and-shared-channels).

Nem todo Teams conteúdo é eDiscoverable. A tabela a seguir mostra os tipos de conteúdo que você pode pesquisar usando ferramentas de Descoberta Online da Microsoft:

| Tipo de conteúdo | Descoberta eDiscoverable | Observações |
|:--- | :--- |:--- |
|Gravações de áudio | Não | |
|Conteúdo do cartão|Sim|Consulte [Pesquisar conteúdo de cartão](#search-for-card-content) para obter mais informações.|
|Links de chat | Sim | |
|Mensagens de chat | Sim |Isso inclui conteúdo em canais Teams padrão, chats 1:1, chats de grupo 1:N e chats com participantes convidados do usuário.  |
|Trechos de código | Não | |
|Mensagens editadas | Sim | Se o usuário estiver em espera, versões anteriores de mensagens editadas também serão preservadas. |
|Emojis, GIFs e adesivos | Sim | |
|Notificações de feed | Não | |
|Imagens em linha | Sim | |
|Componentes de loop| Sim|O conteúdo em um componente de loop é salvo em um arquivo .fluid que é armazenado na conta OneDrive for Business do usuário que envia o componente de loop. Isso significa que você precisa incluir OneDrive como fonte de dados ao pesquisar conteúdo em componentes de loop. |
|Conversas de IM de Reunião | Sim | |
|Metadados <sup>de reunião1</sup> | Sim |  |
|Nome do canal | Sim | |
|Mensagens de chat de canal privado e compartilhado | Sim | |
|Aspas | Sim | O conteúdo cotado é pesquisável. No entanto, os resultados da pesquisa não indicam que o conteúdo foi citado. |
|Reações (como likes, hearts e outras reações) | Não | |
|Assunto | Sim | |
|Tabelas | Sim | |
||||

<sup>1</sup> Os metadados de reunião (e de chamada) incluem o seguinte:

- Hora de início e término da reunião e duração
- Eventos de participação e saída de reunião para cada participante
- Junções/chamadas VOIP
- Insições anônimas
- Inserções de usuário federado
- Insições de usuário convidado

Veja um exemplo de uma conversa de chat entre participantes durante uma reunião.

![Conversa entre participantes no Teams.](media/MeetingIMConversations.png)

[!div class="mx-imgBorder"]

Aqui está um exemplo da cópia de conformidade da mesma conversa de chat exibida em uma ferramenta de Descoberta e.

![Conversa entre participantes nos resultados da pesquisa de Descobertas EDiscovery.](media/MeetingImConversation2.png)

Veja um exemplo dos metadados da reunião.

  > [!div class="mx-imgBorder"]
  > ![Os metadados da reunião da cópia de conformidade.](media/conversationOption3.png)

Para obter mais informações sobre como conduzir uma investigação de Descoberta eDiscovery, consulte [Get started with Core eDiscovery](/microsoft-365/compliance/get-started-core-ediscovery).

Microsoft Teams dados serão exibidos como IM ou Conversas na saída de exportação Excel eDiscovery. Você pode abrir o arquivo `.pst` em Outlook exibir essas mensagens depois de exportá-las.

Ao exibir o arquivo .pst para a equipe, todas as conversas estão localizadas na pasta Chat de Equipe em Histórico de Conversas. O título da mensagem contém o nome da equipe e o nome do canal. Por exemplo, a imagem abaixo mostra uma mensagem de Bob que a mensagem Project canal padrão 7 da equipe de Especificações de Manufatura.

![Captura de tela de uma pasta de bate-papo da equipe na caixa de correio de um usuário no Outlook.](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

Chats privados na caixa de correio de um usuário são armazenados na pasta Chat de Equipe em Histórico de Conversas.

## <a name="ediscovery-of-private-and-shared-channels"></a>Descoberta eDiscover de canais privados e compartilhados

Cópias de conformidade de mensagens em canais privados e compartilhados são enviadas para caixas de correio diferentes, dependendo do tipo de canal. Isso significa que você precisa pesquisar diferentes locais de caixa de correio com base no tipo de canal do qual um usuário é membro.

- **Canais privados**. Cópias de conformidade são enviadas para a caixa de correio de todos os membros dos membros do canal privado. Isso significa que você precisa pesquisar a caixa de correio do usuário ao pesquisar conteúdo em mensagens de canal privado.

- **Canais compartilhados**. Cópias de conformidade são enviadas para uma caixa de correio do sistema associada à equipe pai. Como Teams não dá suporte a uma pesquisa de Descoberta Eletrônico de uma única caixa de correio do sistema para um canal compartilhado, você precisa pesquisar a caixa de correio para a equipe pai (selecionando o nome da caixa de correio equipe) ao pesquisar o conteúdo da mensagem em canais compartilhados.

Cada canal privado e compartilhado tem seu próprio site SharePoint separado do site de equipe pai. Isso significa que os arquivos em canais privados e compartilhados são armazenados em seu próprio site e gerenciados independentemente da equipe pai. Isso significa que você deve identificar e pesquisar o site específico associado a um canal ao pesquisar conteúdo em arquivos e anexos de mensagens de canal.

Use as seções a seguir para ajudar a identificar o canal privado ou compartilhado a ser incluído em sua pesquisa de Descoberta Online.

### <a name="identifying-the-members-of-a-private-channel"></a>Identificar os membros de um canal privado

Use o procedimento nesta seção para identificar membros de um canal privado para que você possa usar as ferramentas de Descoberta Eletrônico para pesquisar conteúdo na caixa de correio do membro em mensagens de canal privado.

Antes de executar essas etapas, certifique-se de ter a versão mais recente [do módulo Teams PowerShell](teams-powershell-overview.md) instalado.

1. Execute o seguinte comando para obter a ID de grupo da equipe que contém os canais compartilhados que você deseja pesquisar.

   ```powershell
   Get-Team -DisplayName <display name of the the parent team>
   ```

   > [!TIP]
   > Execute o cmdlet **Get-Team** sem parâmetros para exibir uma lista de todos os Teams em sua organização. A lista contém a ID do grupo e DisplayName para cada equipe.

2. Execute o seguinte comando para obter uma lista de canais privados na equipe pai. Use a ID do grupo para a equipe obtida na etapa 1.

   ```PowerShell
    Get-TeamChannel -GroupId <parent team GroupId> -MembershipType Private
   ```

3. Execute o seguinte comando para obter uma lista de proprietários e membros de canal privado para um canal particular específico.

   ```PowerShell
    Get-TeamChannelUser -GroupId <parent team GroupId> -DisplayName "Partner Shared Channel"
   ```

4. Inclua as caixas de correio de proprietários e membros de um canal privado como parte [](/microsoft-365/compliance/search-for-content-in-core-ediscovery) de sua consulta de pesquisa de Descoberta Eletrônico na Descoberta Principal ou ao identificar e coletar conteúdo [custodiante](/microsoft-365/compliance/add-custodians-to-case) no Advanced eDiscovery.

### <a name="identifying-the-sharepoint-site-for-private-and-shared-channels"></a>Identificar o site SharePoint para canais privados e compartilhados

Conforme explicado anteriormente, arquivos compartilhados em canais privados e compartilhados (e arquivos anexados a mensagens de canal) são armazenados no conjunto de sites associado ao canal. Use o procedimento nesta seção para identificar a URL do site associado a um canal particular ou compartilhado específico. Em seguida, você pode usar as ferramentas de Descoberta Online para pesquisar conteúdo no site.

Antes de executar essas etapas, [instale o Shell de Gerenciamento SharePoint Online e conecte-se ao SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).

1. Opcionalmente, execute o seguinte para obter uma lista de todos os SharePoint de sites associados a canais compartilhados na equipe pai.

   ```PowerShell
    Get-SPOSite
   ```

   > [!TIP]
   > A convenção de nomenis da URL de um site associado a canais privados e compartilhados é `[SharePoint domain]/sites/[Name of parent team]-[Name of private or shared channel]`. Por exemplo, a URL do canal compartilhado chamado "Colaboração de Parceiros", que está localizada na equipe pai "Equipe de Engenheiros" na organização da Contoso é `https://contoso.sharepoint.com/sites/EngineeringTeam-PartnerCollaboration`.

2. Execute os seguintes comandos do PowerShell para exibir a URL de todos os sites SharePoint associados aos canais privados e compartilhados em sua organização. A saída do script também inclui a ID de grupo da equipe pai, que você precisa executar os comandos na etapa 3.

    ```PowerShell
    $sites = Get-SPOSite -Template "TEAMCHANNEL#1"
    foreach ($site in $sites) {$x= Get-SPOSite -Identity $site.url -Detail; $x.relatedgroupID; $x.url}
    ```

   > [!NOTE]
   > SharePoint sites para canais privados criados antes de 28 de junho de 2021 usam `"TEAMCHANNEL#0"` o valor para a ID do modelo personalizado. Para exibir canais privados criados após essa data, use o valor ao `"TEAMCHANNEL#1"` executar os dois scripts anteriores. Canais compartilhados só usam o valor de `"TEAMCHANNEL#1"`.

3. Para cada equipe pai, execute os seguintes comandos do PowerShell para identificar os sites de canal privado e compartilhado, `$groupID` onde está a ID de grupo da equipe pai.

    ```PowerShell
    $sites = Get-SPOSite -Template "TEAMCHANNEL#1"
    $groupID = "<group ID of parent team)"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

4. Inclua o site associado a um canal privado ou compartilhado como parte de sua consulta [](/microsoft-365/compliance/search-for-content-in-core-ediscovery) de pesquisa de Descoberta Online na Descoberta Principal ou ao identificar e coletar conteúdo [custodiante no Advanced eDiscovery](/microsoft-365/compliance/add-custodians-to-case).

## <a name="search-for-content-for-guest-users"></a>Pesquisar conteúdo para usuários convidados

Você pode usar as ferramentas de Descoberta Online para pesquisar Teams conteúdo relacionado aos usuários convidados em sua organização. Teams conteúdo de chat associado a um usuário convidado é preservado em um local de armazenamento baseado em nuvem e pode ser pesquisado para usar a Descoberta Virtual. Isso inclui a pesquisa de conteúdo em conversas de chat 1:1 e 1:N nas quais um usuário convidado é um participante com outros usuários em sua organização. Você também pode pesquisar mensagens de canal privado nas quais um usuário convidado é um participante e pesquisar conteúdo em conversas de chat de convidado *:convidado* , onde os únicos participantes são usuários convidados.

Para pesquisar conteúdo para usuários convidados:

1. Conexão ao PowerShell do Azure AD. Para obter instruções, consulte a seção "Conexão com o Azure Active Directory PowerShell" no Conexão [para Microsoft 365 com o PowerShell](/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module). Certifique-se de concluir a Etapa 1 e a Etapa 2 no tópico anterior.

2. Depois de se conectar com êxito ao Azure AD PowerShell, execute o seguinte comando para exibir o nome principal do usuário (UPN) para todos os usuários convidados em sua organização. Você precisa usar o UPN do usuário convidado ao criar a pesquisa na etapa 4.

   ```powershell
   Get-AzureADUser -Filter "userType eq 'Guest'" -All $true | FL UserPrincipalName
   ```

   > [!TIP]
   > Em vez de exibir uma lista de nomes principais do usuário na tela do computador, você pode redirecionar a saída do comando para um arquivo de texto. Você pode fazer isso de acordo com `> filename.txt` o comando anterior. O arquivo de texto com os nomes principais do usuário será salvo na pasta atual.

3. Em uma janela Windows PowerShell, conecte-se ao Centro de Conformidade e Segurança & PowerShell. Para obter instruções, [consulte Conexão o PowerShell do Centro de Conformidade & Segurança](/powershell/exchange/connect-to-scc-powershell). Você pode se conectar ou sem usar a autenticação multifa factor.

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

6. Vá para [https://compliance.microsoft.com](https://compliance.microsoft.com) e clique em **Mostrar pesquisa** **allContent** > .

7. Na lista de pesquisas, selecione a pesquisa que você criou na etapa 4 para exibir a página de sobrevoo.

8. Na página de sobrevoo, você pode fazer as seguintes coisas:

   - Clique **em Exibir resultados** para exibir os resultados da pesquisa e visualizar o conteúdo.

   - Ao lado do **campo Consulta** , clique em **Editar** para editar e, em seguida, reprise a pesquisa. Por exemplo, você pode adicionar uma consulta de pesquisa para restringir os resultados.

   - Clique **em Exportar resultados** para exportar e baixar os resultados da pesquisa.

## <a name="search-for-card-content"></a>Pesquisar conteúdo de cartão

O conteúdo do cartão gerado por aplicativos Teams canais, chats 1:1 e chats 1xN é armazenado em caixas de correio e pode ser pesquisado. Um *cartão* é um contêiner de interface do usuário para partes curtas de conteúdo. Os cartões podem ter várias propriedades e anexos e podem incluir botões que podem disparar ações de cartão. Para obter mais informações, consulte [Cards](/microsoftteams/platform/task-modules-and-cards/what-are-cards)

Como outros Teams conteúdo, onde o conteúdo do cartão é armazenado é baseado no local onde o cartão foi usado. O conteúdo dos cartões usados em um canal Teams é armazenado na caixa de correio Teams grupo. O conteúdo do cartão para chats 1:1 e 1xN são armazenados nas caixas de correio dos participantes do chat.

Para pesquisar o conteúdo do cartão, você pode usar as condições `kind:microsoftteams` de `itemclass:IPM.SkypeTeams.Message` pesquisa ou. Ao analisar os resultados da pesquisa, o conteúdo do cartão gerado por bots em um canal Teams tem a propriedade de email `<appname>@teams.microsoft.com`**Remetente/** Autor como , `appname` onde é o nome do aplicativo que gerou o conteúdo do cartão. Se o conteúdo do cartão foi gerado por um usuário, o valor de **Remetente/Autor** identifica o usuário.

Ao exibir o conteúdo do cartão nos resultados da pesquisa de conteúdo, o conteúdo aparece como um anexo à mensagem. O anexo é chamado `appname.html`, onde `appname` é o nome do aplicativo que gerou o conteúdo do cartão. As capturas de tela a seguir mostram como o conteúdo do cartão (para um aplicativo chamado Asana) aparece no Teams e nos resultados de uma pesquisa.

### <a name="card-content-in-teams"></a>Conteúdo do cartão em Teams

![Conteúdo do cartão Teams mensagem de canal.](media/CardContentTeams.png)

### <a name="card-content-in-search-results"></a>Conteúdo do cartão nos resultados da pesquisa
  
![Mesmo conteúdo de cartão nos resultados de uma pesquisa de conteúdo.](media/CardContentEdiscoverySearchResults.png)

> [!NOTE]
> Para exibir imagens do conteúdo do cartão nos resultados da pesquisa neste momento (como as marcas de seleção na captura de tela anterior), você precisa estar entrando no Teams (https://teams.microsoft.com)em uma guia diferente na mesma sessão do navegador que você usa para exibir os resultados da pesquisa. Caso contrário, os espaço reservados de imagem serão exibidos.

## <a name="related-topics"></a>Tópicos relacionados

- [Microsoft 365 eDiscovery](/microsoft-365/compliance/ediscovery)
- [Começar a trabalhar com a Descoberta Básica de EDiscovery](/microsoft-365/compliance/get-started-core-ediscovery)
- [Teams fluxo de trabalho no Advanced eDiscovery](/microsoft-365/compliance/teams-workflow-in-advanced-ediscovery)
- [Visão Geral do PowerShell do Teams](teams-powershell-overview.md)
