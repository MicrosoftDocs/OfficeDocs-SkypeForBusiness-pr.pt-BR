---
title: Configurando o Lync Server 2013 para usar o Microsoft Exchange Server 2013 Archiving
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server 2013 to use Exchange Server 2013 archiving
ms:assetid: 260346d1-edc8-4a0c-8ad2-6c2401c3c377
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ679896(v=OCS.15)
ms:contentKeyID: 49557731
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b163b0ce3324455f8a80eca7be5c1423b302a3d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723181"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving"></a>Configurando o Microsoft Lync Server 2013 para usar o Microsoft Exchange Server 2013 Archiving

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-06-24_

O Microsoft Lync Server 2013 oferece aos administradores a opção de ter mensagens instantâneas e transcrições de webconferências arquivadas em uma caixa de correio do Microsoft Exchange Server 2013 de um usuário, em vez de um banco de dados SQL Server. Se você habilitar essa opção, as transcrições serão gravadas na Pasta de limpeza do usuário. A Pasta de limpeza é uma pasta oculta encontrada na pasta Itens Recuperáveis. Embora essa pasta não seja visível para os usuários finais, a pasta é indexada pelo mecanismo de pesquisa do Exchange e pode ser descoberta usando a pesquisa da caixa de correio do Exchange e/ou o Microsoft SharePoint Server 2013. Como as informações são armazenadas na mesma pasta usada pelo recurso bloqueio in-loco do Exchange (responsável pelo arquivamento de email e outras comunicações do Exchange), os administradores podem usar uma única ferramenta para pesquisar todas as comunicações eletrônicas arquivadas para um utilizador.

<div>


> [!IMPORTANT]  
> Para desabilitar completamente o arquivamento da conversa do Lync, você também deve desabilitar o histórico de conversas do Lync. Para obter mais informações, consulte os tópicos a seguir: <A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">Gerenciando o arquivamento de comunicações internas e externas no Lync Server 2013</A>, <A href="https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy">New-CsClientPolicy</A>e <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">set-CsClientPolicy</A>.



</div>

Para arquivar transcrições no Exchange 2013, você deve começar Configurando a autenticação de servidor para servidor entre os dois servidores. Após a autenticação do servidor para servidor estar em vigor, você pode executar as seguintes tarefas no Microsoft Lync Server 2013 (Observe que, dependendo da configuração e da configuração, talvez não seja necessário concluir todas essas tarefas):

1.  Habilite o arquivamento do Exchange modificando as configurações de arquivamento do Lync Server. Esta etapa é obrigatória para todas as implantações.

2.  Habilitar o arquivamento de comunicações internas e/ou externas dos usuários. Esta etapa é obrigatória para todas as implantações.

3.  Configurar a propriedade ExchangeArchivingPolicy para cada usuário. Esta etapa só é necessária no Lync Server e o Exchange estão localizados em florestas diferentes.

<div>

## <a name="step-1-enabling-exchange-archiving"></a>Etapa 1: habilitar o arquivamento do Exchange

O arquivamento no Lync Server é gerenciado principalmente com o uso das configurações de arquivamento. Ao instalar o Lync Server 2013, você recebe automaticamente uma única coleção global dessas configurações. (Os administradores podem, opcionalmente, criar novas coleções de configurações de arquivamento no escopo do site.) Por padrão, o arquivamento não está habilitado nas configurações globais, nem o arquivamento do Exchange está habilitado nessas configurações. Para usar os administradores de arquivamento do Exchange devem configurar as propriedades EnableArchiving e EnableExchangeArchiving nesses parâmetros de configuração. A propriedade EnableArchiving pode ser definida como um destes três valores:

  - **Nenhum**. O Arquivamento está desabilitado. Este é o valor padrão. Se EnableArchiving estiver definido como None, nenhum deles será arquivado no banco de dados de arquivamento do Lync Server ou no Exchange 2013.

  - **ImOnly**. Apenas transcrições de mensagem instantânea são arquivadas. Se o arquivamento do Exchange estiver habilitado, essas transcrições serão arquivadas no Exchange 2013. Se o arquivamento do Exchange estiver desabilitado, essas transcrições serão arquivadas no Lync Server.

  - **ImAndWebConf**. As transcrições de mensagens instantâneas e Webconferências são arquivadas. Se o arquivamento do Exchange estiver habilitado, essas transcrições serão arquivadas no Exchange 2013. Se o arquivamento do Exchange estiver desabilitado, essas transcrições serão arquivadas no Lync Server.

A propriedade EnableExchangeArchiving é um valor booliano: defina EnableExchangeArchiving como true ($True) para habilitar o arquivamento do Exchange ou defina EnableExchangeArchiving como false ($False) para desabilitar o arquivamento do Exchange. Por exemplo, esse comando permite o arquivamento de transcrições de mensagens instantâneas e também permite o arquivamento do Exchange:

    Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $True

Para desabilitar o arquivamento do Exchange, use um comando semelhante ao seguinte, que permite o arquivamento de mensagens instantâneas, mas que desabilite o arquivamento no Exchange (em outras palavras, as transcrições serão arquivadas no Lync Server):

    Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $False

<div>


> [!NOTE]  
> Se a propriedade EnableArchiving estiver definida como None, o Lync Server não arquivará mensagens instantâneas e transcrições da Webconferência. Nesse caso, o servidor simplesmente ignorará o valor configurado para EnableExchangeArchiving.



</div>

O arquivamento do Exchange também pode ser habilitado (ou desabilitado) usando o painel de controle do Lync Server. Para fazer isso, execute o seguinte procedimento:

1.  No Painel de Controle, clique em **Monitoramento e Arquivamento** e, em seguida, clique em **Configuração de Arquivamento**.

2.  Na guia **Configuração de Arquivamento**, clique duas vezes no conjunto de configurações de arquivamento a ser modificado (por exemplo, o conjunto **Global**).

3.  No painel **Editar Configuração de Arquivamento**, clique na lista suspensa **Configuração de arquivamento** e selecione **Arquivar sessões de IM** (para arquivar apenas sessões de mensagens instantâneas) ou **Arquivar sessões de IM e Webconferência** (para arquivar sessões de mensagens instantâneas e de Webconferência).

4.  Depois de escolher os itens a serem arquivados, selecione a caixa de seleção **integração do Exchange Server** para habilitar o arquivamento do Exchange. Para desabilitar o arquivamento do Exchange, desmarque esta caixa de seleção.

<div>


> [!NOTE]  
> A caixa de seleção <STRONG>Integração com o Exchange Server</STRONG> não estará disponível se a opção <STRONG>Configuração de arquivamento</STRONG> estiver definida como <STRONG>Desabilitar arquivamento</STRONG>. Você deve habilitar o arquivamento primeiro e, em seguida, habilitar o arquivamento do Exchange.



</div>

Se o Lync Server 2013 e o Exchange 2013 estiverem localizados na mesma floresta, o arquivamento para usuários individuais (ou pelo menos para usuários que tenham contas de email no Exchange 2013) serão gerenciados usando as políticas de bloqueio in-loco do Exchange. Se você tiver usuários que são hospedados em uma versão anterior do Exchange, o arquivamento para esses usuários serão gerenciados usando as políticas de arquivamento do Lync Server. Observe que somente os usuários com contas no Exchange 2013 podem ter suas transcrições do Lync arquivadas no Exchange.

Se o Lync Server 2013 e o Exchange 2013 estiverem localizados em florestas diferentes, o arquivamento para usuários individuais será gerenciado com a configuração da propriedade ExchangeArchivingPolicy para cada conta de usuário individual. Consulte a Etapa 3 para obter mais informações.

</div>

<div>

## <a name="step-2-enabling-the-archiving-of-internal-andor-external-communications"></a>Etapa 2: Habilitar o arquivamento de comunicações internas e/ou externas

Depois de habilitar o arquivamento (e o arquivamento do Exchange), você deve modificar as políticas de arquivamento adequadas para garantir que as sessões do usuário sejam realmente arquivadas. Observe que a simples habilitação do arquivamento (etapa 1) não faz com que o Lync Server comece a arquivar mensagens instantâneas e transcrições da Webconferência. Em vez disso, você deverá usar políticas de arquivamento para habilitar o arquivamento interno e/ou externo. Ao instalar o Lync Server 2013, você também pode instalar uma única política de arquivamento global contendo duas propriedades:

  - **ArchiveInternal**. Quando definida como True ($True), indica que as sessões de comunicação interna envolvendo apenas usuários com contas do Active Directory em sua organização serão arquivadas.

  - **ArchiveExternal**. Quando definida como True ($True), indica que as sessões de comunicação interna (sessões envolvendo pelo menos um usuário que não possui uma conta do Active Directory em sua organização) serão arquivadas.

Por padrão, os valores de ambas as propriedade são definidos como False, indicando que nem as sessões de comunicação interna nem externa são arquivadas. Para modificar a política global, você pode usar o Shell de gerenciamento do Lync Server e o cmdlet Set-CsArchivingPolicy. Este comando habilita o arquivamento das sessões de comunicação interna e externa:

    Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True

Como alternativa, é possível usar New-CsArchivingPolicy para criar uma nova política no escopo do site ou no escopo por usuário. Por exemplo, este comando cria uma nova política de arquivamento por usuário chamada RedmondArchivingPolicy:

    New-CsArchivingPolicy -Identity "RedmondArchivingPolicy" -ArchiveInternal $True -ArchiveExternal $True

Se você criar uma política por usuário, precisará atribuir esta política para os usuários adequados. Por exemplo:

    Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName  "RedmondArchivingPolicy"

As políticas de arquivamento também podem ser gerenciadas usando o painel de controle do Lync Server. No Painel de Controle, clique em **Monitoramento e Arquivamento** e em **Política de Arquivamento**. Para modificar uma política existente, clique duas vezes na política (por exemplo, Global) e, no painel **Editar Política de Arquivamento**, marque ou desmarque as caixas de seleção **Arquivar comunicações internas** e **Arquivar comunicações externas**, conforme necessário. Para criar uma nova política de arquivamento, clique em **novo** e, em seguida, selecione política de **site** ou **política de usuário**. Se você criar uma nova política de usuário, deverá acessar as contas de usuário adequadas (na guia **Usuários**) e atribuir a nova política a esses usuários.

</div>

<div>

## <a name="step-3-configuring-the-exchangearchivingpolicy-property"></a>Etapa 3: Configurar a propriedade ExchangeArchivingPolicy

Se o Lync Server 2013 e o Exchange 2013 estiverem localizados em florestas diferentes, não será suficiente simplesmente habilitar o arquivamento do Exchange nas configurações de arquivamento de configuração; Isso não resultará em mensagens instantâneas e transcrições de conferência na Web sendo arquivadas no Exchange. Em vez disso, você também deve configurar a propriedade ExchangeArchivingPolicy em cada uma das contas de usuário relevantes do Lync Server. Essa propriedade pode ser definida como um destes quatro valores:

1.  Não inicializado. Indica que o arquivamento será baseado nas configurações de bloqueio in-loco definidas para a caixa de correio do Exchange do usuário; Se o bloqueio in-loco não tiver sido habilitado na caixa de correio do usuário, o usuário terá suas transcrições de mensagens e de conferência na Web arquivadas no Lync Server.

2.  **UseLyncArchivingPolicy**. Indica que as transcrições de mensagens instantâneas e conferência na Web do usuário devem ser arquivadas no Lync Server, em vez de no Exchange.

3.  **NoArchiving**. Indica que as transcrições de mensagens instantâneas e Webconferências do usuário não devem ser arquivadas. Observe que essa configuração substitui todas as políticas de arquivamento do Lync Server atribuídas ao usuário.

4.  **ArchivingToExchange**. Indica que as transcrições de mensagens instantâneas e webconferências do usuário devem ser arquivadas no Exchange independentemente das configurações de bloqueio in-loco que tiverem (ou não) sido atribuídas à caixa de correio do usuário.

Por exemplo, para configurar uma conta de usuário para que as transcrições de mensagens instantâneas e webconferências sejam sempre arquivadas no Exchange, você pode usar um comando semelhante a este do Shell de gerenciamento do Lync Server:

    Set-CsUser -Identity "Ken Myer" -ExchangeArchivingPolicy ArchivingToExchange

Se desejar definir a mesma política de arquivamento para um grupo de usuários (por exemplo, todos os usuários hospedados em um pool de Registradores Avançados especificado), você poderá usar um comando semelhante ao seguinte:

    Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Set-CsUser -ExchangeArchivingPolicy ArchivingToExchange

Observe que você deve usar o Shell de gerenciamento do Lync Server (e o Windows PowerShell) para configurar o valor da propriedade ExchangeArchivingPolicy. Essa propriedade não é exposta a administradores no painel de controle do Lync Server.

Se desejar exibir uma lista de todos os usuários aos quais foi atribuída uma política de arquivamento específica, você poderá usar um comando semelhante ao apresentando a seguir, que retorna o nome para exibição do Active Directory de todos os usuários que tiveram a propriedade ExchangeArchivingPolicy definida como Não inicializado:

    Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -eq "Uninitialized"} | Select-Object DisplayName

Da mesma forma, este comando retorna o nome para exibição dos usuários que não têm a propriedade ExchangeArchivingPolicy definida como UseLyncArchivingPolicy:

    Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -ne "UseLyncArchivingPolicy"} | Select-Object DisplayName

</div>

</div>

<span> </span>

</div>

</div>

</div>

