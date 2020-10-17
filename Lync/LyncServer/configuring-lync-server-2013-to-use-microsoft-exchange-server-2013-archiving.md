---
title: Configurando o Lync Server 2013 para usar o arquivamento do Microsoft Exchange Server 2013
description: Configurando o Lync Server 2013 para usar o arquivamento do Microsoft Exchange Server 2013.
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
ms.openlocfilehash: 80b0673071ec38246e366fe7556b39bd495895d1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542937"
---
# <a name="configuring-microsoft-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving"></a>Configurando o Microsoft Lync Server 2013 para usar o arquivamento do Microsoft Exchange Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-06-24_

O Microsoft Lync Server 2013 oferece aos administradores a opção de ter as transcrições de mensagens instantâneas e webconferência arquivadas na caixa de correio do Microsoft Exchange Server 2013 de um usuário, em vez de em um banco de dados do SQL Server. Se você habilitar esta opção, as transcrições são gravadas na pasta Lixeira da caixa de correio do usuário. A pasta Lixeira é uma pasta oculta encontrada na pasta Itens Recuperáveis. Embora essa pasta não fique visível para os usuários finais, a pasta é indexada pelo mecanismo de pesquisa do Exchange e pode ser descoberta usando a pesquisa de caixa de correio do Exchange e/ou o Microsoft SharePoint Server 2013. Como as informações são armazenadas na mesma pasta usada pelo recurso de bloqueio do Exchange In-Place (responsável pelo arquivamento de email e outras comunicações do Exchange), os administradores podem usar uma única ferramenta para pesquisar todas as comunicações eletrônicas arquivadas para um usuário.

<div>


> [!IMPORTANT]  
> Para desabilitar completamente o arquivamento da conversa do Lync, você também deve desabilitar o histórico de conversas do Lync. Para obter mais informações, consulte os seguintes tópicos: <A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">Managing the Archiving of Internal and external Communications in Lync Server 2013</A>, <A href="https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy">New-CsClientPolicy</A>e <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">set-CsClientPolicy</A>.



</div>

Para arquivar transcrições no Exchange 2013, você deve começar Configurando a autenticação de servidor para servidor entre os dois servidores. Depois que a autenticação de servidor para servidor estiver em vigor, você poderá realizar as seguintes tarefas no Microsoft Lync Server 2013 (Observe que, dependendo da configuração e da configuração, talvez não seja necessário concluir todas as tarefas):

1.  Habilite o arquivamento do Exchange modificando suas definições de configuração de arquivamento do Lync Server. Esta etapa é obrigatória para todas as implantações.

2.  Habilitar o arquivamento para comunicações internas e/ou externas dos usuários. Esta etapa é obrigatória para todas as implantações.

3.  Configurar a propriedade ExchangeArchivingPolicy para cada usuário. Esta etapa só é necessária no Lync Server e o Exchange estão localizados em florestas diferentes.

<div>

## <a name="step-1-enabling-exchange-archiving"></a>Etapa 1: habilitar o arquivamento do Exchange

O arquivamento no Lync Server é gerenciado principalmente usando as definições de configuração de arquivamento. Ao instalar o Lync Server 2013, você recebe automaticamente uma única coleção global dessas configurações. (Os administradores podem, opcionalmente, criar novas coleções de configurações de arquivamento no escopo do site.) Por padrão, o arquivamento não está habilitado nas configurações globais, nem o arquivamento do Exchange está habilitado nessas configurações. Para usar os administradores de arquivamento do Exchange deve configurar as propriedades EnableArchiving e EnableExchangeArchiving nessas definições de configuração. A propriedade EnableArchiving pode ser definida para um dos seguintes três valores:

  - **Nenhum**. o Arquivamento é desabilitado. Este é o valor padrão. Se EnableArchiving estiver definido como nenhum, nada será arquivado no seu banco de dados de arquivamento do Lync Server ou no Exchange 2013.

  - **Inonly**. Apenas transcrições de mensagem instantânea são arquivadas. Se o arquivamento do Exchange estiver habilitado, essas transcrições serão arquivadas no Exchange 2013. Se o arquivamento do Exchange estiver desabilitado, essas transcrições serão arquivadas no Lync Server.

  - **ImAndWebConf**. As transcrições de mensagem instantânea e de conferência da Web são arquivadas. Se o arquivamento do Exchange estiver habilitado, essas transcrições serão arquivadas no Exchange 2013. Se o arquivamento do Exchange estiver desabilitado, essas transcrições serão arquivadas no Lync Server.

A propriedade EnableExchangeArchiving é um valor booliano: defina EnableExchangeArchiving como true ($True) para habilitar o arquivamento do Exchange ou definir EnableExchangeArchiving como false ($False) para desabilitar o arquivamento do Exchange. Por exemplo, este comando habilita o arquivamento de transcrições de mensagens instantâneas e também habilita o arquivamento do Exchange:

    Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $True

Para desabilitar o arquivamento do Exchange, use um comando semelhante ao seguinte, que permite o arquivamento de mensagens instantâneas, mas desabilita o arquivamento para o Exchange (em outras palavras, as transcrições serão arquivadas no Lync Server):

    Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $False

<div>


> [!NOTE]  
> Se a propriedade EnableArchiving estiver definida como nenhum, o Lync Server não arquivará as transcrições de mensagens instantâneas e Webconferência. Neste caso, o servidor simplesmente ignora o valor configurado para EnableExchangeArchiving.



</div>

O arquivamento do Exchange também pode ser habilitado (ou desabilitado) usando o painel de controle do Lync Server. Para fazer isso, conclua o seguinte procedimento:

1.  No Painel de Controle, clique em **Monitoramento e Arquivamento** e clique em **Configuração de Arquivamento**.

2.  Na guia **Configuração de Arquivamento**, clique duas vezes no conjunto de configurações de arquivamento a ser modificado (por exemplo, o conjunto **Global**).

3.  No painel **Editar configuração de arquivamento**, clique na lista suspensa **Configuração de arquivamento** e selecione **Arquivar sessões de IM** (para arquivar apenas sessões de mensagem instantânea) ou **Arquivar sessões de IM e conferência da Web** (para arquivar sessões de mensagem instantânea e conferência da Web).

4.  Após escolher os itens a serem arquivados, marque a caixa de seleção integração com o **Exchange Server** para habilitar o arquivamento do Exchange. Para desabilitar o arquivamento do Exchange, desmarque essa caixa de seleção.

<div>


> [!NOTE]  
> A caixa de seleção <STRONG>Integração do Exchange Server</STRONG> não estará disponível se a <STRONG>Configuração de arquivamento</STRONG> está definido para <STRONG>Desabilitar arquivamento</STRONG>. Você deve habilitar o arquivamento primeiro e, em seguida, habilitar o arquivamento do Exchange.



</div>

Se o Lync Server 2013 e o Exchange 2013 estiverem localizados na mesma floresta, o arquivamento para usuários individuais (ou pelo menos para usuários que tenham contas de email no Exchange 2013) será gerenciado usando as políticas de retenção do Exchange In-Place. Se você tiver usuários hospedados em uma versão anterior do Exchange, o arquivamento desses usuários será gerenciado usando as políticas de arquivamento do Lync Server. Observe que apenas usuários com contas no Exchange 2013 podem ter suas transcrições do Lync arquivadas no Exchange.

Se o Lync Server 2013 e o Exchange 2013 estiverem localizados em florestas diferentes, o arquivamento de usuários individuais será gerenciado pela configuração da propriedade ExchangeArchivingPolicy para cada conta de usuário individual. Consulte a Etapa 3 para obter mais informações.

</div>

<div>

## <a name="step-2-enabling-the-archiving-of-internal-andor-external-communications"></a>Etapa 2: Habilitar o arquivamento de comunicações internas e/ou externas

Depois de habilitar o arquivamento (e o arquivamento do Exchange), você deve modificar as políticas de arquivamento apropriadas para garantir que as sessões de usuário sejam realmente arquivadas. Observe que simplesmente habilitar o arquivamento (etapa 1) não faz com que o Lync Server comece a arquivar transcrições de mensagens instantâneas e webconferências. Ao invés disso, você deve usar políticas de arquivamento para habilitar o arquivamento interno e/ou externo. Ao instalar o Lync Server 2013, você também instala uma política de arquivamento única e global que contém duas propriedades:

  - **ArchiveInternal**. Quando definido para True ($True) indica que as sessões de comunicação interna envolvendo apenas usuários com contas do Active Directory em sua organização serão arquivadas.

  - **ArchiveExternal**. Quando definido para True ($True) indica que as sessões de comunicação interna (sessões envolvendo pelo menos um usuário que não possui uma conta do Active Directory em sua organização) serão arquivadas.

Por padrão, ambos os valores de propriedade são definidos para False, significando que as sessões de comunicação interna e externa não são arquivadas. Para modificar a política global, você pode usar o Shell de gerenciamento do Lync Server e o cmdlet Set-CsArchivingPolicy. Este comando habilita o arquivamento de sessões de comunicação interna e externa:

    Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True

Em alternativa, é possível usar New-CsArchivingPolicy para criar uma nova política no escopo local ou no escopo por usuário. Por exemplo, este comando cria uma nova política de arquivamento por usuário chamada RedmondArchivingPolicy:

    New-CsArchivingPolicy -Identity "RedmondArchivingPolicy" -ArchiveInternal $True -ArchiveExternal $True

Se você criar uma política por usuário, precisará atribuir esta política para os usuários adequados. Por exemplo:

    Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName  "RedmondArchivingPolicy"

As políticas de arquivamento também podem ser gerenciadas usando o painel de controle do Lync Server. Dentro do Painel de Controle, clique em **Monitoramento e Arquivamento** e em **Política de Arquivamento**. Para modificar uma política existente, clique duas vezes na política (por exemplo, Global) e, no painel **Editar política de arquivamento**, marque ou desmarque as caixas de seleção **Arquivar comunicações internas** e **Arquivar comunicações externas** conforme necessário. Para criar uma nova política de arquivamento, clique em **novo** e selecione política de **site** ou **política de usuário**. Se você criar uma nova política de usuário, deve acessar as contas de usuário adequadas (na guia **Usuários**) e atribuir estes usuários com a nova política.

</div>

<div>

## <a name="step-3-configuring-the-exchangearchivingpolicy-property"></a>Etapa 3: Configurar a propriedade ExchangeArchivingPolicy

Se o Lync Server 2013 e o Exchange 2013 estiverem localizados em florestas diferentes, não é suficiente simplesmente habilitar o arquivamento do Exchange nas definições de configuração de arquivamento; Isso não resultará em mensagens instantâneas e transcrições de webconferências sendo arquivadas no Exchange. Em vez disso, você também deve configurar a propriedade ExchangeArchivingPolicy em cada uma das contas de usuário relevantes do Lync Server. Esta propriedade pode ser definida para uma dos quatro valores possíveis:

1.  Não inicializado. Indica que o arquivamento será baseado nas configurações de retenção de In-Place configuradas para a caixa de correio do Exchange do usuário; se In-Place bloqueio não tiver sido habilitado na caixa de correio do usuário, o usuário terá suas transcrições de mensagens e webconferência arquivadas no Lync Server.

2.  **UseLyncArchivingPolicy**. Indica que as transcrições de mensagens instantâneas e webconferências do usuário devem ser arquivadas no Lync Server, e não no Exchange.

3.  **Noarquivamento**. Indica que as transcrições de mensagem instantânea e conferência da Web do usuário não devem ser arquivadas. Observe que essa configuração substitui as políticas de arquivamento do Lync Server atribuídas ao usuário.

4.  **ArchivingToExchange**. Indica que as transcrições de mensagens instantâneas e webconferências do usuário devem ser arquivadas no Exchange independentemente das configurações de retenção de In-Place que tiverem (ou não) atribuídas à caixa de correio do usuário.

Por exemplo, para configurar uma conta de usuário para que as transcrições de mensagens instantâneas e webconferências sejam sempre arquivadas no Exchange, você pode usar um comando semelhante a este no Shell de gerenciamento do Lync Server:

    Set-CsUser -Identity "Ken Myer" -ExchangeArchivingPolicy ArchivingToExchange

Se você deseja definir a mesma política de arquivamento para um grupo de usuários (por exemplo, todos os usuários hospedados em um pool do Registrador específico), é possível usar um comando semelhante ao seguinte:

    Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Set-CsUser -ExchangeArchivingPolicy ArchivingToExchange

Observe que você deve usar o Shell de gerenciamento do Lync Server (e o Windows PowerShell) para configurar o valor da propriedade ExchangeArchivingPolicy. Essa propriedade não é exposta a administradores no painel de controle do Lync Server.

Se você deseja ver uma lista de todos os usuários atribuídos com uma política de arquivamento específica, é possível usar um comando semelhante ao seguinte, que retorna o nome de exibição do Active Directory de todos os usuários com a propriedade ExchangeArchivingPolicy definida para Não inicializado:

    Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -eq "Uninitialized"} | Select-Object DisplayName

Da mesma forma, este comando retorna o nome de exibição dos usuários que não tem a propriedade ExchangeArchivingPolicy definida para UseLyncArchivingPolicy:

    Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -ne "UseLyncArchivingPolicy"} | Select-Object DisplayName

</div>

</div>

<span> </span>

</div>

</div>

</div>

