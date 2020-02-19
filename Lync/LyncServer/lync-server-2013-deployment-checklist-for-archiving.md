---
title: 'Lync Server 2013: lista de verificação de implantação para arquivamento'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for Archiving
ms:assetid: 7479734d-be01-40d9-ad82-320a09d19d04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205009(v=OCS.15)
ms:contentKeyID: 48184516
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9f7c8184862993500d09819de912bccf4310aa73
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134637"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-archiving-in-lync-server-2013"></a>Lista de verificação de implantação para arquivamento no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-18_

O arquivamento é instalado automaticamente em cada servidor de front-end em sua implantação do Lync Server 2013, mas você ainda precisa configurá-lo antes de usá-lo. As etapas necessário para configurá-lo (resumidas nesta seção) constituem a implantação do Arquivamento.

<div>

## <a name="deployment-sequence"></a>Sequência de implantação

O modo de configuração do Arquivamento depende da opção de armazenamento escolhida:

  - Se você usar a integração do Microsoft Exchange para todos os usuários em sua implantação, não será necessário configurar as políticas de arquivamento do Lync Server 2013 para seus usuários. Em vez disso, configure suas políticas de bloqueio in-loco do Exchange para dar suporte ao arquivamento para usuários hospedados no Exchange 2013, com suas caixas de correio colocadas em bloqueio in-loco. Para obter detalhes sobre como configurar essas políticas, consulte a documentação do produto Exchange 2013.

  - Se você não usar a integração do Microsoft Exchange para todos os usuários em sua implantação, será necessário adicionar bancos de dados de arquivamento do Lync Server (bancos de dados do SQL Server) à sua topologia e publicá-lo, além de configurar políticas e configurações para seus usuários, antes de poder arquivar dados para esses usuários. Você pode implantar os bancos de dados de Arquivamento ao mesmo tempo em que implanta a topologia inicial ou após implantar pelo menos um pool front-end ou servidor Standard Edition. Este documento descreve como implantar os bancos de dados de Arquivamento adicionando-os a uma implantação existente.

Se você habilitar o arquivamento em um pool de Front-Ends ou em um servidor Standard Edition, você deve habilitá-lo em todos os pools e servidores de mesmo tipo na sua implantação. Isso porque os usuários cujas comunicações precisam ser arquivadas podem ser convidados a um grupo de conversação de IM ou a reuniões hospedadas em um pool diferente. Se o arquivamento não estiver habilitado no pool no qual a conversa ou a reunião está hospedada, a sessão completa não poderá ser arquivada. Nesses casos, as IMs com usuários habilitados para arquivamento ainda poderão ser arquivados, menos para arquivos de conteúdo de conferência e eventos de ingresso ou saída de conferências.

<div>


> [!IMPORTANT]  
> Se o arquivamento for crucial na sua organização por motivos de conformidade, certifique-se de implantar o arquivamento, configurar políticas e outras opções no nível apropriado e habilitá-lo para todos os usuários apropriados antes de habilitar esses usuários para o Lync Server 2013.



</div>

</div>

<div>

## <a name="archiving-deployment-process"></a>Processo de implantação do Arquivamento

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
<th>Associações a grupos e funções</th>
<th>Documentação</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Instalar pré-requisitos de hardware e software</strong></p></td>
<td><ul>
<li><p>Para usar a integração do Microsoft Exchange (usando o Exchange 2013 para armazenamento de arquivamento para alguns ou todos os usuários), você precisa de uma implantação existente do Exchange 2013.</p></li>
<li><p>Para usar bancos de dados de Arquivamento separados (usando bancos de dados do SQL Server) para armazenamento de arquivamento para alguns ou todos os usuários, SQL Server no servidor que armazenará os dados de arquivamento.</p></li>
</ul>
<div>

> [!NOTE]  
> O Arquivamento é executado nos servidores front-end de um pool Enterprise e servidores Standard Edition. Não há requisitos adicionais de hardware e software além daqueles para instalar esses servidores.


</div></td>
<td><p>Usuário do domínio que é membro do grupo local de administradores.</p></td>
<td><p><a href="lync-server-2013-supported-hardware.md">Hardware suportado para o Lync Server 2013</a> na documentação de suporte.</p>
<p><a href="lync-server-2013-server-software-and-infrastructure-support.md">Suporte a infraestrutura e software de servidor no Lync Server 2013</a> na documentação de suporte.</p>
<p><a href="lync-server-2013-technical-requirements-for-archiving.md">Requisitos técnicos para arquivamento no Lync Server 2013</a> na documentação de planejamento.</p>
<p><a href="lync-server-2013-setting-up-systems-and-infrastructure-for-archiving.md">Configurar sistemas e infraestrutura para arquivamento no Lync Server 2013</a> na documentação de implantação.</p>
<p><a href="lync-server-2013-exchange-and-sharepoint-integration-support.md">Suporte à integração do Exchange Server e do SharePoint no Lync Server 2013</a> na documentação de suporte.</p></td>
</tr>
<tr class="even">
<td><p><strong>Crie a topologia interna apropriada para oferecer suporte ao arquivamento (apenas se não estiver usando a integração do Microsoft Exchange para todos os usuários em sua implantação)</strong></p></td>
<td><p>Execute o construtor de topologias para adicionar bancos de dados de arquivamento do Lync Server 2013 (bancos de dados do SQL Server) à topologia e, em seguida, publique a topologia.</p></td>
<td><p>Para definir a topologia a fim de incorporar bancos de dados de Arquivamento, uma conta que é membro do grupo local de usuários.</p>
<p>Para publicar a topologia, uma conta que é membro do grupo de administradores de domínio e do grupo RTCUniversalServerAdmins e que tem permissões de controle total (ler/gravar/modificar) no compartilhamento de arquivo a ser usado para o repositório de arquivos do Lync Server 2013 (de modo que o construtor de topologias possa configurar as DACLs necessárias).</p></td>
<td><p><a href="lync-server-2013-adding-archiving-databases-to-an-existing-lync-server-2013-deployment.md">Adicionar bancos de dados de arquivamento a uma implantação existente do Lync Server 2013</a> na documentação de implantação.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Configurar a autenticação de servidor para servidor (somente se estiver usando a integração com o Microsoft Exchange)</strong></p></td>
<td><p>Configure os servidores para habilitar a autenticação entre o Lync Server 2013 e o Exchange 2013. Recomendamos executar <strong>Test-CsExchangeStorageConnectivity testuser_sipUri – Folder dumpster</strong> para validar a conectividade de armazenamento de arquivamento do Exchange antes de habilitar o arquivamento.</p></td>
<td><p>Uma conta com permissões adequadas para gerenciar certificados nos servidores.</p></td>
<td><p><a href="lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md">Gerenciamento de autenticação de servidor para servidor (OAuth) e aplicativos de parceiros no Lync server 2013</a> na documentação de implantação ou na documentação de operações.</p></td>
</tr>
<tr class="even">
<td><p><strong>Definir políticas e configurações de arquivamento</strong></p></td>
<td><p>Configure o arquivamento, incluindo se deve usar a integração do Microsoft Exchange, a política global e as políticas de site e de usuário (quando não estiver usando a integração do Microsoft Exchange para todos os armazenamentos de dados) e opções de arquivamento específicas, como o modo crítico e os dados exportação e limpeza.</p>
<p>Se estiver usando a integração com o Microsoft Exchange, configure as políticas de bloqueio in-loco do Exchange conforme apropriado.</p></td>
<td><p>Grupo RTCUniversalServerAdmins (somente Windows PowerShell) ou atribua usuários à função CSArchivingAdministrator ou CSAdministrator.</p></td>
<td><p><a href="lync-server-2013-configuring-support-for-archiving.md">Configurando o suporte para arquivamento no Lync Server 2013</a> na documentação de implantação.</p>
<p>Documentação do produto Exchange (se estiver usando a integração com o Microsoft Exchange).</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="deploying-lync-server-and-microsoft-exchange-in-different-forests"></a>Implantando o Lync Server e o Microsoft Exchange em diferentes florestas

Se o Microsoft Exchange Server não estiver implantado na mesma floresta do Lync Server, você deverá verificar se os seguintes atributos do Active Directory do Exchange estão sincronizados com a floresta onde o Lync Server está implantado:

1.  msExchUserHoldPolicies

2.  proxyAddresses

Este é um atributo com vários valores. Ao sincronizá-lo, você deve mesclar os valores, não substitui-los, de modo a garantir que os valores existentes não sejam perdidos.

</div>

</div>

<span> </span>

</div>

</div>

</div>

