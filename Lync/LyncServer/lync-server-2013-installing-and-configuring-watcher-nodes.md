---
title: 'Lync Server 2013: instalar e configurar nós do Inspetor'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing and configuring watcher nodes
ms:assetid: 61f6deea-e3ef-4468-9be8-a65705815ebb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204943(v=OCS.15)
ms:contentKeyID: 48184284
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 980dc8c92488e3806cd6c1bf15970a79af6fa2b4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534938"
---
# <a name="installing-and-configuring-watcher-nodes-in-lync-server-2013"></a>Instalando e configurando nós do Inspetor no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-11-07_

Os *nós do Inspetor* são computadores que executam periodicamente as transações sintéticas do Lync Server. *As transações sintéticas* são cmdlets do Windows PowerShell que verificam se os principais cenários de usuário final, como a capacidade de entrar no sistema, ou a capacidade de trocar mensagens instantâneas, estão funcionando conforme o esperado. Para o Lync Server 2013, o System Center Operations Manager pode executar as transações sintéticas mostradas na tabela a seguir. A tabela mostra três tipos diferentes de transações sintéticas:

  - **Padrão**. Estas são as transações sintéticas que um nó do Inspetor será executado por padrão. Ao criar um novo nó do Inspetor, você tem a opção de especificar quais transações sintéticas esse nó será executado. (Esse é o objetivo do parâmetro tests usado pelo cmdlet **New-CsWatcherNodeConfiguration** .) Se você não usar o parâmetro tests quando o nó do Inspetor for criado, ele executará automaticamente todas as transações sintéticas padrão e não executará qualquer uma das transações sintéticas não padrão. Isso significa, por exemplo, que o nó do Inspetor será configurado para executar o teste de Test-CsAddressBookService, mas não será configurado para executar o teste de Test-CsExumConnectivity.

  - **Não padrão**. Como o nome já diz, as transações sintéticas não padrão são testes que os nós do inspetor não executam por padrão. No entanto, o nó do inspetor pode ser habilitado para executar qualquer uma das transações sintéticas não padrão. Você pode fazer isso ao criar o nó do inspetor (usando o cmdlet **New-CsWatcherNodeConfiguration**) ou a qualquer momento após a criação. Muitas das transações sintéticas não padrão exigem etapas de configuração adicionais. Para obter detalhes, consulte [instruções de configuração especial para transações sintéticas no Lync Server 2013](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md).

  - **Estendido**. Os testes estendidos são um tipo especial de transação sintética não padrão. Diferentemente das outras transações sintéticas, os testes estendidos podem ser executados várias vezes durante cada fase. Isso pode ser útil, por exemplo, para verificações de várias rotas de voz de PSTN (rede telefônica pública comutada) de um pool. Isso pode ser configurado com a simples adição de várias instâncias de um teste estendido a um nó do inspetor.

Para obter detalhes sobre o processo de adição de outras transações sintéticas a um nó do Inspetor, consulte [Managing Watchers Nodes in Lync Server 2013](lync-server-2013-managing-watcher-nodes.md). Você pode usar o Shell de gerenciamento do Lync Server para remover as transações sintéticas de um nó do Inspetor.

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
<td><p>Confirma se os usuários podem pesquisar outros usuários que não estão em sua lista de contatos.</p></td>
<td><p>Padrão</p></td>
</tr>
<tr class="even">
<td><p>Test-CsAddressBookWebQuery (ABWQ)</p></td>
<td><p>Confirma se os usuários podem pesquisar outros usuários que não estão em sua lista de contatos via HTTP.</p></td>
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
<td><p>Não é usado com a versão local do Lync Server 2013</p></td>
<td><p>Estendida</p></td>
</tr>
<tr class="even">
<td><p>Test-CsPstnPeerToPeerCall (PSTN)</p></td>
<td><p>Confirma se os usuários podem realizar e receber chamadas de pessoas de fora da organização (números PSTN).</p></td>
<td><p>Não padrão, estendida</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsAVConference (AvConference)</p></td>
<td><p>Confirma se os usuários podem criar e participar de uma conferência de áudio/vídeo.</p></td>
<td><p>Padrão</p></td>
</tr>
<tr class="even">
<td><p>Test-CsAVEdgeConnectivity (AVEdgeConnectivity)</p></td>
<td><p>Confirma se os servidores de borda A/V podem aceitar conexões para chamadas ponto a ponto e chamadas em conferência.</p></td>
<td><p>Não padrão</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsDataConference (dataconferência)</p></td>
<td><p>Confirma se os usuários podem participar de uma conferência com colaboração de dados, uma reunião online que inclui atividades como quadros de comunicações e votações.</p></td>
<td><p>Não padrão</p></td>
</tr>
<tr class="even">
<td><p>Test-CsExumConnectivity (exumconnectivity)</p></td>
<td><p>Confirma se um usuário pode se conectar à UM (Unificação de mensagens) do Exchange.</p></td>
<td><p>Não padrão</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsGroupIM (GroupIM)</p></td>
<td><p>Confirma se os usuários podem enviar mensagens instantâneas em conferências e participar de conversas de mensagem instantânea com três ou mais pessoas.</p></td>
<td><p>Padrão</p></td>
</tr>
<tr class="even">
<td><p>Test-CsGroupIM – TestJoinLauncher (JoinLauncher)</p></td>
<td><p>Confirma se os usuários podem criar reuniões agendadas e ingressar nelas através de um link de endereço Web.</p></td>
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
<td><p>Confirma se os contatos de um usuário podem ser acessados por meio do repositório unificado de contatos. O repositório unificado de contatos permite que os usuários mantenham um único conjunto de contatos que podem ser acessados usando o Lync 2013, Outlook e/ou Outlook Web Access.</p></td>
<td><p>Não padrão</p></td>
</tr>
<tr class="even">
<td><p>Test-CsXmppIM (XmppIM)</p></td>
<td><p>Confirma se uma mensagem instantânea pode ser enviada através do gateway XMPP.</p></td>
<td><p>Não padrão</p></td>
</tr>
</tbody>
</table>


Não é necessário instalar nós do inspetor para usar o System Center Operations Manager. Se você não instalar esses nós, ainda poderá obter alertas em tempo real dos componentes do Lync Server 2013 quando ocorrer um problema. (O pacote de gerenciamento de componente e usuário não usa nós do Inspetor.) No entanto, os nós do Inspetor serão necessários se você quiser monitorar cenários de ponta a ponta usando o pacote de gerenciamento de monitoramento ativo.

<div>


> [!NOTE]  
> Os administradores também podem executar transações sintéticas manualmente, sem a necessidade de usar ou instalar o Operations Manager. Para obter detalhes sobre os vários cmdlets do Test-Cs, consulte o <A href="https://docs.microsoft.com/powershell/module/skype/?view=skype-ps">índice de cmdlets do Lync Server 2013</A>.



</div>

Dependendo do porte de sua implantação, as transações sintéticas podem consumir uma grande quantidade de memória e tempo de processamento do computador. Por esse motivo, é recomendável usar um computador dedicado como nó do inspetor. Por exemplo, você não deve configurar um servidor front-end para atuar como um nó do Inspetor. Os nós do Inspetor devem atender às seguintes especificações de hardware:

<div>


> [!NOTE]  
> Um nó do Inspetor do Microsoft Lync Server 2010 herdado não pode ser colocado no mesmo computador com um nó do Inspetor do Lync Server 2013. Isso ocorre porque os principais arquivos de sistema do Lync Server 2010 e do Lync Server 2013 não podem ser instalados no mesmo computador.<BR>No entanto, os nós do Inspetor do Lync Server 2013 podem monitorar simultaneamente o Lync Server 2013 e o Lync Server 2010. As duas versões do produto oferecem suporte a transações sintéticas padrão.



</div>

Os nós do Inspetor do Lync Server 2013 podem ser implantados dentro ou fora de uma empresa para ajudar a verificar:

  - <span></span>  
    A conectividade com pools para usuários internos da empresa.

  - <span></span>  
    A conectividade através de redes de perímetro para usuários remotos que trabalham fora da empresa.

  - <span></span>  
    A conectividade com dispositivos de filiais.

  - <span></span>  
    Conectividade com o Lync Server 2010 dentro da empresa e através de redes de perímetro.

Diferentes opções de autenticação estão disponíveis para dentro e fora da empresa a fim de simplificar a administração. Para obter detalhes, consulte [Configurando um nó do inspetor para executar transações sintéticas no Lync Server 2013](lync-server-2013-configuring-a-watcher-node-to-run-synthetic-transactions.md).

Para configurar um computador para atuar como um nó do Inspetor, você deve concluir as etapas a seguir após ter instalado o System Center Operations Manager e importou os pacotes de gerenciamento do Lync Server 2013.

Antes de instalar os arquivos principais do Lync Server 2013 e os arquivos do agente do System Center, você também deve certificar-se de que o computador do nó do Inspetor atende a todos os pré-requisitos para instalar o Lync Server 2013. Além disso, o computador do nó do inspetor também deve ter os seguintes itens instalados:


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
<li><p>processador de 64 bits, Quad-Core, 2,33 GHz ou superior</p></li>
<li><p>processador de 2 vias com 64 bits, Dual-Core, 2,33 GHz ou superior</p></li>
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


  - A versão completa do .NET Framework 4.5.

  - Windows Identity Foundation.

  - Windows PowerShell 3.0.

Depois que todos esses pré-requisitos forem atendidos, você poderá configurar o nó do inspetor executando as seguintes etapas:

  - Instalação dos arquivos do Lync Server 2013 Core no computador do nó do Inspetor.

  - Instalando o agente do System Center Operations Manager no computador do nó do observador.

  - Execute o arquivo executável Watchernode.msi.

  - Use os cmdlets **CsWatcherNodeConfiguration** para configurar os usuários de teste a serem empregados pelo nó do inspetor.

</div>

<span> </span>

</div>

</div>

</div>

