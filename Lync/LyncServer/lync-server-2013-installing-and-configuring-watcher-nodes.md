---
title: 'Lync Server 2013: Instalando e configurando nós do Inspetor'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Installing and configuring watcher nodes
ms:assetid: 61f6deea-e3ef-4468-9be8-a65705815ebb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204943(v=OCS.15)
ms:contentKeyID: 48184284
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 36d466cbffff1cf1e68eefe120215895e52e7c81
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829005"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-and-configuring-watcher-nodes-in-lync-server-2013"></a>Instalar e configurar nós do Inspetor no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-11-07_

*Nós de Inspetor* são computadores que executam periodicamente transações sintéticas do Lync Server. *As transações sintéticas* são cmdlets do Windows PowerShell que verificam se os principais cenários do usuário final, como a capacidade de entrar no sistema, ou a capacidade de trocar mensagens de chat, estão funcionando conforme esperado. Para o Lync Server 2013, o System Center Operations Manager pode executar as transações sintéticas mostradas na tabela a seguir. Há três tipos diferentes de transações sintéticas mostradas na tabela:

  - **Padrão**. Estas são as transações sintéticas que um nó de Inspetor será executado por padrão. Ao criar um novo nó Inspetor, você tem a opção de especificar quais transações sintéticas esse nó executará. (Essa é a finalidade do parâmetro testes usado pelo cmdlet **New-CsWatcherNodeConfiguration** .) Se você não usar o parâmetro tests quando o nó do Inspetor for criado, ele executará automaticamente todas as transações sintéticas padrão e não executará qualquer uma das transações sintéticas não padrão. Isso significa, por exemplo, que o nó do Inspetor será configurado para executar o teste Test-CsAddressBookService, mas não será configurado para executar o teste Test-CsExumConnectivity.

  - **Não padrão**. Como o nome indica, as transações sintéticas não padrão são testes que os nós do inspetor não são executados por padrão. No entanto, o nó do Inspetor pode ser habilitado para executar qualquer uma das transações sintéticas não padrão. Você pode fazer isso quando cria o nó do Inspetor (usando o cmdlet **New-CsWatcherNodeConfiguration** ) ou a qualquer momento após isso. Muitas das transações sintéticas não padrão exigem etapas adicionais de configuração. Para obter detalhes, consulte [instruções de configuração especial para transações sintéticas no Lync Server 2013](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md).

  - **Estendido**. Os testes estendidos são um tipo especial de transação sintética não padrão. Diferentemente das outras transações sintéticas, os testes estendidos podem ser executados várias vezes durante cada fase. Isso pode ser útil ao verificar o comportamento, como várias rotas de voz PSTN (rede telefônica pública comutada) para um pool. Isso pode ser configurado simplesmente adicionando várias instâncias de um teste estendido a um nó de Inspetor.

Para obter detalhes sobre o processo de adicionar outras transações sintéticas a um nó de Inspetor, consulte [Gerenciando nós de Inspetor no Lync Server 2013](lync-server-2013-managing-watcher-nodes.md). Você pode usar o Shell de gerenciamento do Lync Server para remover transações sintéticas de um nó do Inspetor.

As transações sintéticas disponíveis para os nós do inspetor incluem as seguintes:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome do cmdlet (nome do teste)</th>
<th>Descrição</th>
<th>Tipo de transação sintética</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Test-CsAddressBookService (ABS)</p></td>
<td><p>Confirma que os usuários podem procurar usuários que não estão na lista de contatos deles.</p></td>
<td><p>Padrão</p></td>
</tr>
<tr class="even">
<td><p>Test-CsAddressBookWebQuery (ABWQ)</p></td>
<td><p>Confirma que os usuários podem procurar usuários que não estão na lista de contatos via HTTP.</p></td>
<td><p>Padrão</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsIM (IM)</p></td>
<td><p>Confirma se os usuários podem enviar mensagens instantâneas ponto a ponto.</p></td>
<td><p>Padrão</p></td>
</tr>
<tr class="even">
<td><p>Test-CsP2PAV (P2PAV)</p></td>
<td><p>Confirma se os usuários podem realizar chamadas de áudio ponto a ponto (apenas sinalização).</p></td>
<td><p>Padrão</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsPresence (Presence)</p></td>
<td><p>Confirma se os usuários podem exibir a presença de outros usuários.</p></td>
<td><p>Padrão</p></td>
</tr>
<tr class="even">
<td><p>Test-CsRegistration (Registration)</p></td>
<td><p>Confirma se os usuários podem entrar no Lync.</p></td>
<td><p>Padrão</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsAudioConferencingProvider (ACP)</p></td>
<td><p>Não usado com a versão local do Lync Server 2013</p></td>
<td><p>Estendidas</p></td>
</tr>
<tr class="even">
<td><p>Test-CsPstnPeerToPeerCall (PSTN)</p></td>
<td><p>Confirma se os usuários podem realizar e receber chamadas de pessoas de fora da organização (números PSTN).</p></td>
<td><p>Não padrão, estendido</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsAVConference (AvConference)</p></td>
<td><p>Confirma se os usuários podem criar e participar de uma conferência de áudio/vídeo.</p></td>
<td><p>Padrão</p></td>
</tr>
<tr class="even">
<td><p>Test-CsAVEdgeConnectivity (AVEdgeConnectivity)</p></td>
<td><p>Confirma que os servidores de borda A/V podem aceitar conexões para chamadas ponto a ponto e chamadas em conferência.</p></td>
<td><p>Não padrão</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsDataConference (DataConference)</p></td>
<td><p>Confirma que os usuários podem participar de uma conferência de colaboração de dados, uma reunião online que inclui atividades como quadros de comunicações e sondagens.</p></td>
<td><p>Não padrão</p></td>
</tr>
<tr class="even">
<td><p>Test-CsExumConnectivity (ExumConnectivity)</p></td>
<td><p>Confirma se um usuário pode se conectar à uma mensagem unificada do Exchange (UM).</p></td>
<td><p>Não padrão</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsGroupIM (GroupIM)</p></td>
<td><p>Confirma se os usuários podem enviar mensagens instantâneas em conferências e participar de conversas de mensagem instantânea com três ou mais pessoas.</p></td>
<td><p>Padrão</p></td>
</tr>
<tr class="even">
<td><p>Test-CsGroupIM –TestJoinLauncher (JoinLauncher)</p></td>
<td><p>Confirma que os usuários podem criar e ingressar em reuniões agendadas por meio de um link de endereço da Web.</p></td>
<td><p>Não padrão</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsMCXP2PIM (MCXP2PIM)</p></td>
<td><p>Confirma se usuários de dispositivos móveis podem registrar-se e enviar mensagens instantâneas.</p></td>
<td><p>Não padrão</p></td>
</tr>
<tr class="even">
<td><p>Test-CsPersistentChatMessage (PersistentChatMessage)</p></td>
<td><p>Confirma se os usuários podem trocar mensagens usando o serviço de chat persistente.</p></td>
<td><p>Não padrão</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsUnifiedContactStore (UnifiedContactStore)</p></td>
<td><p>Confirma se os contatos de um usuário podem ser acessados por meio do repositório unificado de contatos. O repositório de contatos unificado fornece uma maneira para os usuários manterem um único conjunto de contatos que podem ser acessados usando o Lync 2013, o Outlook e/ou o Outlook Web Access.</p></td>
<td><p>Não padrão</p></td>
</tr>
<tr class="even">
<td><p>Test-CsXmppIM (XmppIM)</p></td>
<td><p>Confirma que uma mensagem instantânea pode ser enviada pelo Gateway XMPP (Extensible Messaging and Presence Protocol).</p></td>
<td><p>Não padrão</p></td>
</tr>
</tbody>
</table>


Você não precisa instalar nós de inspetor para usar o System Center Operations Manager. Se você não instalar esses nós, ainda poderá obter alertas em tempo real dos componentes do Lync Server 2013 quando ocorrer um problema. (O componente e o pacote de gerenciamento do usuário não usam nós do Inspetor.) No entanto, nós de Inspetor são necessários se você deseja monitorar cenários de ponta a ponta usando o pacote de gerenciamento de monitoramento ativo.

<div>


> [!NOTE]  
> Os administradores também podem executar transações sintéticas manualmente, sem precisar usar ou instalar o Operations Manager. Para obter detalhes sobre os vários cmdlets Test-cs, consulte o índice de cmdlets do <A href="https://docs.microsoft.com/powershell/module/skype/?view=skype-ps">Lync Server 2013</A>.



</div>

Dependendo do tamanho da sua implantação, as transações sintéticas podem usar uma grande quantidade de memória do computador e tempo do processador. Por esse motivo, recomendamos que você use um computador dedicado como nó de Inspetor. Por exemplo, você não deve configurar um servidor front-end para atuar como um nó de Inspetor. Os nós de Inspetor devem atender às seguintes especificações de hardware:

<div>


> [!NOTE]  
> Um nó de Inspetor do Microsoft Lync Server 2010 herdado não pode ser posicionado na mesma máquina com um nó do Inspetor do Lync Server 2013. Isso ocorre porque os principais arquivos de sistema do Lync Server 2010 e do Lync Server 2013 não podem ser instalados no mesmo computador.<BR>No entanto, os nós do Inspetor do Lync Server 2013 podem monitorar simultaneamente o Lync Server 2013 e o Lync Server 2010. As transações sintéticas padrão são suportadas nas duas versões do produto.



</div>

Os nós do Inspetor do Lync Server 2013 podem ser implantados dentro ou fora de uma empresa para ajudar a verificar:

  - <span></span>  
    A conectividade com pools para usuários internos da empresa.

  - <span></span>  
    Conectividade por meio de redes de perímetro para usuários remotos que trabalham fora da empresa.

  - <span></span>  
    A conectividade com dispositivos de filiais.

  - <span></span>  
    Conectividade com o Lync Server 2010 dentro da empresa e através de redes de perímetro.

Opções de autenticação diferentes estão disponíveis para dentro e para fora da empresa para ajudar a simplificar a administração. Para obter detalhes, consulte Configurando [um nó de inspetor para executar transações sintéticas no Lync Server 2013](lync-server-2013-configuring-a-watcher-node-to-run-synthetic-transactions.md).

Para configurar um computador para atuar como um nó de Inspetor, você deve concluir as seguintes etapas após ter instalado o System Center Operations Manager e importado os pacotes de gerenciamento do Lync Server 2013.

Antes de instalar os arquivos do Lync Server 2013 Core e os arquivos do agente do System Center, você também deve verificar se o computador do nó do Inspetor atende a todos os pré-requisitos para instalar o Lync Server 2013. Além disso, o computador do nó do Inspetor também deve ter os seguintes itens instalados:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Componente de hardware</th>
<th>Requisitos mínimos</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CPU</p></td>
<td><p>Um dos seguintes:</p>
<ul>
<li><p>Processador de 64 bits, quad-core, 2.33 GHz ou superior</p></li>
<li><p>Processador de 2 vias e 64 bits, dual-core, 2.33 GHz ou superior</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Memória</p></td>
<td><p>8 GB</p></td>
</tr>
<tr class="odd">
<td><p>Sistema operacional de rede</p></td>
<td><ul>
<li><p>1 adaptador de rede 1 Gbps</p></li>
<li><p>Windows Server 2008 R2, Windows Server 2012 ou</p>
<p>Windows Server 2012 R2</p></li>
</ul></td>
</tr>
</tbody>
</table>


  - A versão completa do .NET Framework 4,5.

  - Windows Identity Foundation.

  - Windows PowerShell 3,0.

Assim que todos esses pré-requisitos forem atendidos, você poderá configurar o nó do Inspetor por:

  - Instalar os arquivos do Lync Server 2013 Core no computador do nó inspetor.

  - Instalando o agente do System Center Operations Manager no computador do nó inspetor.

  - Executar o arquivo executável Watchernode. msi.

  - Usar os cmdlets **CsWatcherNodeConfiguration** para configurar os usuários de teste para serem empregados pelo nó do Inspetor.

</div>

<span> </span>

</div>

</div>

</div>

