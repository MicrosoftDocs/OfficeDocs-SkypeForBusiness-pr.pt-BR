---
title: Conduzir uma investigação de conteúdo de descoberta eletrônica do conteúdo
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- SPO_Content
ms.reviewer: anach
search.appverid: MET150
f1.keywords:
- NOCSH
description: Saiba o que fazer quando você precisar executar uma descoberta eletrônica, como quando precisa enviar todas as informações armazenadas eletronicamente para procedimentos legais.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 75098323afa8aef9e80223cbc1883e9c12cb53c6
ms.sourcegitcommit: 477aac9e14fced139ee7dd827942ce35b9769b63
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/15/2020
ms.locfileid: "43510690"
---
# <a name="conduct-an-ediscovery-investigation-of-content-in-microsoft-teams"></a>Conduzir uma investigação de Descoberta Eletrônica de conteúdo no Microsoft Teams

Grandes empresas muitas vezes são expostas a grandes procedimentos legais de penalidade que exigem o envio de todas as ESI (informações armazenadas eletronicamente). O conteúdo do Microsoft Teams pode ser pesquisado e usado durante investigações de descoberta eletrônica.

## <a name="overview"></a>Visão geral

Todas as equipes 1:1 ou chats em grupo são registradas nas caixas de correio dos respectivos usuários. Todas as mensagens de canal padrão são registradas na caixa de correio do grupo que representa a equipe. Os arquivos carregados em canais padrão são cobertos pela funcionalidade de descoberta eletrônica do SharePoint Online e do OneDrive for Business.

a descoberta eletrônica de mensagens e arquivos em [canais privados](private-channels.md) funciona de forma diferente em canais padrão. Para saber mais, consulte [descoberta eletrônica de canais privados](#ediscovery-of-private-channels).

Nem todo o conteúdo do teams é eDiscoverable. A tabela a seguir mostra os tipos de conteúdo que podem ser localizados por meio de descoberta eletrônica.

| Tipo de conteúdo | eDiscoverable | Observações |
|:--- | --- |:--- |
| Mensagens de chat do teams | Sim | Mensagens de chat de chats em que os usuários convidados são os únicos participantes de um 1:1 ou 1: N o chat não é eDiscoverable. |
| Gravações de áudio | Não | |
| Carimbo de data/hora mostrando quando uma mensagem foi lida por cada usuário | Não | |
| Gravações de áudio | Não | |
| Mensagens de canal privado | Não | |
| Emojis, GIFs, adesivos | Não | |
| Trechos de código | Não | |
| Links de chat | Não | |
| Reações (curtidas, corações e assim por diante) | Não | |
| Mensagens editadas | Sim | Se o usuário estiver em espera, as versões anteriores das mensagens editadas serão preservadas. |
| Imagens embutidas | Não | |
| Tabelas | Não | |
| Assunto | Não | |
| Cota | Sim | Conteúdo entre aspas é pesquisável. No entanto, os resultados da pesquisa não indicam que o conteúdo foi cotado. |
| Nome do canal | Não | |

- Para conduzir uma investigação de descoberta eletrônica com o conteúdo do Microsoft Teams, examine a etapa 1 em [gerenciar casos de descoberta eletrônica no link do centro de conformidade de segurança do &](https://support.office.com/article/Manage-eDiscovery-cases-in-the-Office-365-Security-Compliance-Center-edea80d6-20a7-40fb-b8c4-5e8c8395f6da) .

- Os dados do Microsoft Teams serão exibidos como mensagens instantâneas ou conversas na saída de exportação do Excel para descoberta eletrônica. Você pode abrir o `.pst` arquivo no Outlook para exibir essas mensagens após a exportação.

    Ao exibir o `.pst` arquivo da equipe, observe que todas as conversas são mantidas na pasta de chat da equipe em histórico de conversas. O título da mensagem contém o nome da equipe e o nome do canal. Por exemplo, a imagem abaixo mostra uma mensagem de Bob que encontrava o canal padrão do Project 7 da equipe de especificações de fabricação.

    ![Captura de tela de uma pasta de chat de equipe na caixa de correio de um usuário no Outlook](media/Conduct_an_eDiscovery_investigation_of_content_in_Microsoft_Teams_image1.png)

- Chats privados na caixa de correio de um usuário são armazenados na pasta de chat da equipe em histórico de conversas.

## <a name="ediscovery-of-private-channels"></a>Descoberta eletrônica de canais privados

Os registros das mensagens enviadas em um canal privado são entregues na caixa de correio de todos os membros do canal privado, e não em uma caixa de correio de grupo. Os títulos dos registros são formatados para indicar de qual canal privado eles foram enviados.

Como cada canal privado tem seu próprio conjunto de sites do SharePoint separado do site de equipe pai, os arquivos em um canal privado são gerenciados independentemente da equipe pai.

O Teams não é compatível com a pesquisa de descoberta eletrônica de um único canal dentro de uma equipe, portanto, a equipe inteira deve ser pesquisada. Para executar uma pesquisa de descoberta eletrônica do conteúdo em um canal privado, pesquise na equipe, no conjunto de sites associado ao canal privado (para incluir arquivos) e caixas de correio de membros do canal privado (para incluir mensagens).

Use as etapas a seguir para identificar arquivos e mensagens em um canal privado para incluir em sua pesquisa de descoberta eletrônica.

### <a name="include-private-channel-files-in-an-ediscovery-search"></a>Incluir arquivos de canal privado em uma pesquisa de descoberta eletrônica

Antes de executar essas etapas, instale o [Shell de gerenciamento do SharePoint Online e conecte-se ao SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).

1. Execute o seguinte para obter uma lista de todos os conjuntos de sites do SharePoint associados a canais privados na equipe.

    ```PowerShell
    Get-SPOSite
    ```

2. Execute o seguinte script do PowerShell para obter uma lista de todas as URLs de conjuntos de sites do SharePoint associadas a canais privados na equipe e a ID do grupo pai da equipe.

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    foreach ($site in $sites) {$x= get-sposite -identity $site.url -detail; $x.relatedgroupID; $x.url} 
    ```

3. Para cada ID de equipe ou grupo, execute o seguinte script do PowerShell para identificar todos os sites de canais particulares relevantes, em que $groupID é a ID de grupo da equipe.

    ```PowerShell
    $sites = get-sposite -template "teamchannel#0"
    $groupID = "e8195240-4a70-4830-9106-80193cf717cb"
    foreach ($site in $sites) {$x= Get-SpoSite -Identity $site.url -Detail; if ($x.RelatedGroupId -eq $groupID) {$x.RelatedGroupId;$x.url}}
    ```

### <a name="include-private-channel-messages-in-an-ediscovery-search"></a>Incluir mensagens de canal privado em uma pesquisa de descoberta eletrônica

Antes de executar essas etapas, verifique se você tem a [versão mais recente do módulo Teams PowerShell](teams-powershell-overview.md) instalada.

1. Execute o seguinte para obter uma lista de canais privados na equipe.

    ```PowerShell
    Get-TeamChannel -GroupId <GroupID> -MembershipType Private
    ```

2. Execute o seguinte para obter uma lista de membros do canal privado.

    ```PowerShell
    Get-TeamChannelUser -GroupId <GroupID> -DisplayName "Engineering" -Role Member
    ```

3. Inclua as caixas de correio de todos os membros de cada canal privado da equipe como parte da sua consulta de pesquisa de descoberta eletrônica.

## <a name="advanced-ediscovery"></a>Advanced eDiscovery

Alguns conteúdos do Microsoft Teams também podem ser pesquisados e preservados usando o [fluxo de trabalho de descoberta avançada](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20). Embora o eDiscovery forneça uma variedade de funcionalidades de pesquisa, retenção e exportação, a descoberta eletrônica avançada proporciona aos administradores de conformidade mais ferramentas para identificar fontes de dados e analisar o conteúdo delas.

### <a name="advanced-ediscovery-custodian-workflow-for-teams-content"></a>Fluxo de trabalho de responsáveis pelo descoberta eletrônica avançada para conteúdo de equipes

Os responsáveis podem ser membros de várias equipes. Você pode capturar o conteúdo da equipe que é relevante para esses responsáveis. Para obter informações detalhadas sobre o fluxo de trabalho do responsáveis, consulte [fluxo de trabalho de descoberta eletrônica avançado](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20).

Depois de adicionar um novo, clique no botão **Avançar** e, em seguida, no botão **Adicionar** . Em seguida, uma janela exibe isso solicita que você selecione outros locais, que mostrarão todas as associações do responsáveis e os locais de sites correspondentes do SharePoint para seus dados. Em todas essas fontes de dados e equipes, você pode escolher o conteúdo que deseja usar para a descoberta eletrônica e, em seguida, colocar o usuário e todas as fontes de dados que você identificou em espera.

Você pode selecionar se deseja incluir o conteúdo do Exchange, o conteúdo do OneDrive dele ou ambos. O conteúdo do Exchange inclui todo o conteúdo do aplicativo nas caixas de correio do usuário, como o email, o conteúdo da equipe que é armazenado na caixa de correio e assim por diante. O conteúdo do OneDrive inclui não apenas o conteúdo do usuário, mas também todo o conteúdo do teams armazenado no OneDrive, como chats de 1:1, 1: N chats e arquivos compartilhados em chats.

Você também tem a opção de associar qualquer equipe na qual os responsáveis sejam membros, para que as mensagens de chat do canal e os arquivos aos quais os responsáveis tenham acesso sejam incluídos. Além disso, qualquer outra equipe pode ser associada a um ou mais responsáveis. Para obter mais informações, consulte [Adicionar responsáveis a um caso de descoberta eletrônica avançada](https://docs.microsoft.com/microsoft-365/compliance/add-custodians-to-case).

> [!NOTE]
> a descoberta eletrônica de mensagens e arquivos em [canais privados](private-channels.md) funciona de forma diferente em canais padrão. Para saber mais, consulte [descoberta eletrônica de canais privados](#ediscovery-of-private-channels).

### <a name="placing-a-data-source-on-hold"></a>Colocando uma fonte de dados em espera

Se não houver um usuário específico para designar como um usuário, você poderá colocar uma fonte de dados inteira em espera. Para obter mais informações sobre isenções, consulte [gerenciar isenções na descoberta eletrônica avançada](https://docs.microsoft.com/microsoft-365/compliance/managing-holds).

Ao criar um bloqueio para o conteúdo do Teams, você pode escolher todos os locais que deseja incluir em sua espera. Mesmo que os usuários estejam excluindo ou alterando o conteúdo, a retenção manterá cópias de todas as versões anteriores desse conteúdo.

Você também pode usar uma consulta opcional para definir condições para a retenção com base em palavras-chave, intervalo de datas, autor e muitos outros critérios. Se você especificar nenhuma palavra-chave, tudo dessa fonte de dados estará sujeito à retenção.

### <a name="advanced-ediscovery-searches"></a>Pesquisas avançadas de descoberta eletrônica

O conteúdo do teams também pode ser pesquisado. Para obter mais informações sobre pesquisas, consulte [coletar dados para um caso na descoberta eletrônica avançada](https://docs.microsoft.com/microsoft-365/compliance/collecting-data-for-ediscovery). Uma pesquisa retornará uma conversa inteira se até uma mensagem coincidir com a consulta de pesquisa.

Ao criar uma consulta de pesquisa, você pode escolher os responsáveis para que todas as fontes que você já selecionou sejam pesquisadas. Você também pode pesquisar fontes não custodial como um site de equipe que não está mapeado para um usuário. Consultas opcionais também estão disponíveis para restringir sua pesquisa dentro do conteúdo do teams.

Depois de criar uma pesquisa e a selecionar, uma janela será exibida com detalhes adicionais e ações que você pode executar na pesquisa selecionada. Se você clicar no botão **estatísticas** , poderá ver as estatísticas sobre a pesquisa, incluindo as divisões de acordo com os tipos de localização, a fonte original do conteúdo e se o conteúdo está localizado em uma caixa de correio de grupo, na caixa de correio do usuário individual ou em um site do SharePoint. Isso permite que você veja um detalhamento de quais fontes estão contribuindo para seus resultados de pesquisa. Há também uma exibição de **consultas** disponível para que você possa ver quais palavras-chave individuais estão contribuindo para seus resultados.

Depois de finalizar a pesquisa, você pode clicar no botão de **configuração adicionar resultados à revisão** e adicioná-lo a um conjunto de revisão. Para obter mais informações sobre conjuntos de revisão, consulte [gerenciar os conjuntos de revisão no fluxo de trabalho de descoberta eletrônica avançada](https://docs.microsoft.com/microsoft-365/compliance/managing-review-sets) e [examinar conjuntos](#review-sets-workflow) mais adiante neste artigo.

#### <a name="normal-review-sets-and-conversation-review-sets"></a>Conjuntos de revisão normais e conjuntos de revisão de conversa

Ao adicionar uma pesquisa a um conjunto de revisão, você pode escolher um conjunto de revisão normal ou um conjunto de revisão de conversa.

Um conjunto de revisão normal é semelhante a uma exportação; Ele fornece os arquivos `.msg` individuais para o conteúdo do Teams e apresenta o conteúdo em um modo de exibição básico. Normalmente, você usaria um conjunto de revisão normal quando planeja usar outras ferramentas de software para reprocessar os arquivos mais tarde.

Um conjunto de revisão de conversa fornece uma exibição encadeada e mais intuitiva das conversas; Ele exibe mensagens relacionadas juntas na ordem correta.

A funcionalidade como a redação está disponível nos dois tipos de conjuntos de revisão.

Para obter mais informações sobre conjuntos de revisão, consulte [rever conversas na descoberta eletrônica avançada](https://docs.microsoft.com/microsoft-365/compliance/conversation-review-sets)

#### <a name="collection-options"></a>Opções de coleção

Ao adicionar a um conjunto de revisão, há várias opções disponíveis como caixas de seleção na seção **Opções de cobrança** da janela, incluindo **Opções de recuperação de conversa** e conversas de **equipe**. Se você habilitar essas opções, todas as mensagens individuais do teams que fazem parte do seu conjunto de revisão também serão mostradas com mensagens adicionais ao redor do contexto. Por exemplo, se a sua consulta for muito específica e apenas uma mensagem for retornada como resultado, habilitar essas opções também retornará várias mensagens de acordo com a mensagem que correspondeu à sua consulta.

Muitos critérios lógicos são usados para determinar se as mensagens adicionais fornecem contexto para mensagens que correspondam à sua consulta. Por exemplo, para o conteúdo do Teams, habilitar essas opções recuperará a mensagem pai e todas as mensagens filho, devido à maneira como as mensagens são encadeadas.

Os carimbos de data/hora da mensagem também são verificados. Se uma mensagem corresponder à sua consulta, as mensagens vizinhas que a precede dentro de um intervalo de 4 horas ou que o seguem dentro de um intervalo de 4 horas serão consideradas como parte da conversa e também serão incluídas nos resultados.

Se você deve ter certeza de que mensagens contextuais serão retornadas com correspondências para a sua consulta de pesquisa, não é necessário usar essas opções. Você pode coletar todo o conteúdo ou pode ampliar o intervalo de datas de sua pesquisa para que mais mensagens sejam retornadas como resultado da sua consulta.

### <a name="review-sets-workflow"></a>Fluxo de trabalho conjuntos de revisão

Você pode ver os conjuntos de revisão existentes ou criar novos clicando na guia **revisão** de registros. Para obter mais informações sobre conjuntos de revisão, consulte [gerenciar conjuntos de revisão em descoberta eletrônica avançada](https://docs.microsoft.com/microsoft-365/compliance/managing-review-sets).

Além de documentos, você pode adicionar emails, mensagens de equipe, mensagens do Yammer e outros conteúdos ao conjunto de revisão. Em um conjunto de revisão, você também pode executar muitas das mesmas operações que você pode executar em outros contextos, como pesquisar conteúdo e criar consultas personalizadas. Essas operações só se aplicam a itens que foram adicionados ao conjunto de revisão.

O botão **gerenciar conjuntos de revisão** fornece opções adicionais, como análises, relatórios resumidos, Quantos conjuntos de carregamento foram adicionados e assim por diante.

Para acessar visualizações e gráficos de seus dados, clique em **exibição de perfil de pesquisa** de **resultados** \> individuais no canto superior direito. Você pode clicar em fatias nestes gráficos para selecionar interativamente o tipo de conteúdo que deseja consultar. Por exemplo, você pode optar por consultar somente o conteúdo da equipe. Você também pode salvar essas consultas da mesma forma que salva as consultas que você escreve manualmente.

#### <a name="summary-view-text-view-and-annotate-view"></a>Modo de exibição de resumo, modo de exibição de texto e exibição de anotação

Se você clicar em uma conversa de equipe no conjunto de revisão, ele exibirá o **modo de exibição Resumo**, que exibe uma conversa de equipe inteira como uma lista de mensagens com as quais você pode interagir individualmente. Clique na seta para baixo à direita de uma mensagem para exibir um menu de contexto que permite que você exiba detalhes da mensagem ou baixe `.msg` o arquivo individual. Clicar em detalhes da mensagem mostrará um resumo dos metadados ou os metadados completos da mensagem.

Para baixar um PDF, clique no botão baixar no canto superior direito do modo de exibição de resumo.

Clique na guia **modo de exibição de texto** para exibir um modo de exibição de texto sem formatação do texto extraído da conversa do teams. Isso é adequado para exportação e você pode facilmente trabalhar com esse texto extraído usando outras ferramentas de software.

Clique na guia **modo de exibição de anotação** para acessar os recursos de anotação. Esta guia exibe o conteúdo em um formato semelhante a uma conversa de equipe, mas também há opções adicionais para edição. Há uma ferramenta lápis que você pode usar para fazer anotações, desenhar na mensagem ou fazer um rascunho fino para fins de redação. Há também uma ferramenta de **redação de área** que você pode usar para desenhar um retângulo que escurece a área e a marca como "redigida".

Na parte inferior da guia **modo de exibição de anotação** está o botão **Marcar documentos** , que exibe o painel de marcação. Nesse painel, você pode aplicar uma marca a todas as mensagens dentro da conversa do teams. Você pode rotular uma conversa como responsiva ou não responsiva, privilegiada ou não privilegiada, se contiver "itens interessantes", se deve ser incluído na exportação e se precisa de uma revisão adicional. Você também pode gerenciar e aplicar outras marcas personalizáveis.

#### <a name="action-menu"></a>Menu de ação

Na janela conjuntos de revisão, você pode exportar o conteúdo clicando em **ação** \> **Exportar**. Há muitas opções disponíveis ao exportar.

Para exportar um arquivo que contenha todos os metadados de todas as mensagens do Teams, clique para marcar a caixa de seleção **carregar arquivo** . Para incluir no arquivo todas as marcas que você aplicou ao conteúdo, clique para marcar a caixa de seleção **marcas** .

Use a opção **arquivos nativos** para exportar arquivos em seu formato nativo. Você pode optar por exportar uma conversa como um arquivo ou todas as mensagens de chat individuais em seus próprios arquivos separados.

A opção **arquivos de texto** permite salvar versões de texto sem formatação do conteúdo. Veja o [modo de exibição de resumo, o modo](#summary-view-text-view-and-annotate-view) de exibição de texto e a exibição de anotação acima para obter mais informações sobre como obter uma exibição de texto sem formatação de conversas do teams no conjunto de revisão.

Se você aplicou qualquer redação ao conteúdo conforme descrito na seção modo de exibição [Resumo, modo de exibição de texto e modo de anotação](#summary-view-text-view-and-annotate-view) acima, poderá selecionar a opção substituir itens **nativos reconvertidos por PDFs convertidos** para substituir os arquivos nativos por cópias convertidas em PDF.

Você pode optar por exportar para um contêiner de armazenamento de blob do Azure fornecido pela Microsoft ou pode fornecer seu próprio contêiner de armazenamento de blob do Azure.

Quando estiver pronto para começar o processo de exportação, clique no botão **Exportar** . Após a exportação ser concluída, consulte [baixar trabalhos de exportação](https://docs.microsoft.com/microsoft-365/compliance/download-export-jobs) para obter mais informações sobre como você pode acessar o contêiner de armazenamento do blob do Azure e baixar o conteúdo exportado.

> [!NOTE]
> A exportação pode levar um período de tempo prolongado. Para acompanhar o status do processo de exportação, saia da guia **revisar conjuntos** e clique na guia **exportações** .

## <a name="related-topics"></a>Tópicos relacionados

- [Descoberta eletrônica no Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/ediscovery)
- [Visão Geral do PowerShell do Teams](teams-powershell-overview.md)
