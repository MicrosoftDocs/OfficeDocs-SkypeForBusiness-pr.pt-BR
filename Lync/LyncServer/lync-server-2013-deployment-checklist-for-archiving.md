---
title: 'Lync Server 2013: Lista de verificação da implantação para Arquivamento'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment checklist for Archiving
ms:assetid: 7479734d-be01-40d9-ad82-320a09d19d04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205009(v=OCS.15)
ms:contentKeyID: 48184516
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 51c556dd288ff3539bbf2f4de816eab3a544b847
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829519"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-archiving-in-lync-server-2013"></a>Lista de verificação da implantação para Arquivamento no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-18_

O arquivamento é instalado automaticamente em cada servidor front-end na implantação do Lync Server 2013, mas você ainda precisa configurá-lo para poder usá-lo. As etapas necessárias para configurá-lo, conforme resumido nesta seção, constituem a implantação do arquivamento.

<div>

## <a name="deployment-sequence"></a>Sequência de implantação

A forma de configurar o arquivamento depende da opção de armazenamento que você escolher:

  - Se você usa a integração do Microsoft Exchange para todos os usuários na sua implantação, não é necessário configurar as políticas de arquivamento do Lync Server 2013 para seus usuários. Em vez disso, configure suas políticas de bloqueio in-loco do Exchange para dar suporte ao arquivamento para usuários hospedados no Exchange 2013, com as caixas de correio colocadas no bloqueio in-loco. Para obter detalhes sobre como configurar essas políticas, consulte a documentação do produto Exchange 2013.

  - Se você não usar a integração do Microsoft Exchange para todos os usuários em sua implantação, será necessário adicionar bancos de dados de arquivamento do Lync Server (bancos de dados do SQL Server) à sua topologia e publicá-la, além de definir políticas e configurações para seus usuários, antes que você possa arquivar dados para esses usuários. Você pode implantar bancos de dados de arquivamento ao mesmo tempo em que implanta sua topologia inicial ou depois de implantar pelo menos um pool de front-end ou um servidor Standard Edition. Este documento descreve como implantar bancos de dados de arquivamento adicionando-os a uma implantação existente.

Se você habilitar o arquivamento em um pool de front-end ou em um servidor Standard Edition, habilite-o para todos os outros pools front-ends e servidores Standard Edition na sua implantação. Isso porque os usuários cujas comunicações precisam ser arquivadas podem ser convidados para grupos de conversa via IM ou reuniões hospedadas em um pool diferente. Se o arquivamento não estiver habilitado no pool no qual a conversa ou a reunião está hospedada, a sessão completa não poderá ser arquivada. Nesses casos, as IMs com usuários habilitados para arquivamento ainda poderão ser arquivadas, mas não arquivos de conteúdo de conferência e eventos de ingresso ou saída de conferências.

<div>


> [!IMPORTANT]  
> Se o arquivamento for fundamental para a sua organização por motivos de conformidade, certifique-se de implantar o arquivamento, configurar políticas e outras opções no nível apropriado e habilitá-la para todos os usuários apropriados antes de habilitar esses usuários para o Lync Server 2013.



</div>

</div>

<div>

## <a name="archiving-deployment-process"></a>Processo de implantação de arquivamento

A tabela a seguir fornece uma visão geral das etapas necessárias para implantar o arquivamento em uma topologia existente.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Fase</th>
<th>Etapas</th>
<th>Funções e associações de grupo</th>
<th>Documentação</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Instalar pré-requisitos de hardware e software</strong></p></td>
<td><ul>
<li><p>Para usar a integração do Microsoft Exchange (usando o Exchange 2013 para arquivar o armazenamento para alguns ou todos os usuários), você precisa de uma implantação existente do Exchange 2013.</p></li>
<li><p>Para usar bancos de dados de arquivamento separados (usando bancos de dados do SQL Server) para arquivar o armazenamento para alguns ou todos os usuários, SQL Server no servidor que armazenará os dados do arquivamento.</p></li>
</ul>
<div>

> [!NOTE]  
> O arquivamento é executado em servidores front-end de um pool corporativo e servidores Standard Edition. Não há requisitos adicionais de hardware ou software além daqueles necessários para instalar esses servidores.


</div></td>
<td><p>Usuário do domínio que é membro do grupo local de administradores.</p></td>
<td><p><a href="lync-server-2013-supported-hardware.md">Hardware com suporte para o Lync Server 2013</a> na documentação de suporte.</p>
<p><a href="lync-server-2013-server-software-and-infrastructure-support.md">Suporte de software e infraestrutura do servidor no Lync Server 2013</a> na documentação de suporte.</p>
<p><a href="lync-server-2013-technical-requirements-for-archiving.md">Requisitos técnicos para arquivamento no Lync Server 2013</a> na documentação de planejamento.</p>
<p><a href="lync-server-2013-setting-up-systems-and-infrastructure-for-archiving.md">Configurar sistemas e infraestrutura para arquivamento no Lync Server 2013</a> na documentação de implantação.</p>
<p><a href="lync-server-2013-exchange-and-sharepoint-integration-support.md">Suporte à integração do Exchange Server e do SharePoint no Lync server 2013</a> na documentação de suporte.</p></td>
</tr>
<tr class="even">
<td><p><strong>Criar a topologia interna apropriada para dar suporte ao arquivamento (apenas se não estiver usando a integração do Microsoft Exchange para todos os usuários em sua implantação)</strong></p></td>
<td><p>Execute o construtor de topologias para adicionar bancos de dados de arquivamento do Lync Server 2013 (bancos de dados do SQL Server) à topologia e, em seguida, publique a topologia.</p></td>
<td><p>Para definir uma topologia para incorporar bancos de dados de arquivamento, uma conta que seja membro do grupo usuários local.</p>
<p>Para publicar a topologia, uma conta que é membro do grupo Domain admins e do grupo RTCUniversalServerAdmins, e que tem permissões de controle total (leitura/gravação/modificação) no compartilhamento de arquivos a ser usado para o repositório de arquivos do Lync Server 2013 (para que o construtor de topologias possa configurar as DACLs obrigatórias).</p></td>
<td><p><a href="lync-server-2013-adding-archiving-databases-to-an-existing-lync-server-2013-deployment.md">Adicionar bancos de dados de arquivamento a uma implantação existente do Lync Server 2013</a> na documentação de implantação.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Configurar a autenticação do servidor para o servidor (somente se estiver usando a integração do Microsoft Exchange)</strong></p></td>
<td><p>Configurar servidores para habilitar a autenticação entre o Lync Server 2013 e o Exchange 2013. Recomendamos executar <strong>Test-CsExchangeStorageConnectivity testuser_sipUri – diretório dumpster</strong> para validar a conectividade do armazenamento do Exchange Archiving antes de habilitar o arquivamento.</p></td>
<td><p>Uma conta com permissões adequadas para gerenciar certificados nos servidores.</p></td>
<td><p><a href="lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md">Gerenciamento de autenticação de servidor para servidor (OAuth) e aplicativos de parceiros no Lync server 2013</a> na documentação de implantação ou na documentação de operações.</p></td>
</tr>
<tr class="even">
<td><p><strong>Configurar políticas e configurações de arquivamento</strong></p></td>
<td><p>Configurar o arquivamento, incluindo se a integração do Microsoft Exchange, a política global e as políticas de usuário e de qualquer site (quando não estão sendo usadas na integração do Microsoft Exchange para todos os dados) e opções de arquivamento específicas, como dados e modo crítico exportar e descartar.</p>
<p>Se estiver usando a integração do Microsoft Exchange, configure as políticas de bloqueio do Exchange in-loco conforme apropriado.</p></td>
<td><p>Grupo RTCUniversalServerAdmins (somente Windows PowerShell) ou atribua usuários à função CSArchivingAdministrator ou CSAdministrator.</p></td>
<td><p><a href="lync-server-2013-configuring-support-for-archiving.md">Configuração do suporte para arquivamento no Lync Server 2013</a> na documentação de implantação.</p>
<p>Documentação do produto Exchange (se estiver usando a integração do Microsoft Exchange).</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="deploying-lync-server-and-microsoft-exchange-in-different-forests"></a>Implantar o Lync Server e o Microsoft Exchange em florestas diferentes

Se o Microsoft Exchange Server não for implantado na mesma floresta do Lync Server, você deve verificar se os seguintes atributos do Active Directory do Exchange estão sincronizados com a floresta onde o Lync Server está implantado:

1.  msExchUserHoldPolicies

2.  proxyAddresses

Este é um atributo com vários valores. Ao sincronizá-lo, você deve mesclar os valores, não substitui-los, de modo a garantir que os valores existentes não sejam perdidos.

</div>

</div>

<span> </span>

</div>

</div>

</div>

