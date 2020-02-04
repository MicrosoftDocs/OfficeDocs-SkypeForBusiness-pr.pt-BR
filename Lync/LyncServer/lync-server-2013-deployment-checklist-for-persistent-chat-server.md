---
title: 'Lync Server 2013: Lista de verificação de implantação para o Servidor de Chat Persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for Persistent Chat Server
ms:assetid: b1108f8f-88a2-4660-8086-d25ba76f7239
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412851(v=OCS.15)
ms:contentKeyID: 48185155
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d80122534739d443dedaeeb203ab09da94cb0067
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762699"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-persistent-chat-server-in-lync-server-2013"></a>Lista de verificação de implantação para o Servidor de Chat Persistente no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-16_

A implantação do Lync Server 2013, servidor de chat persistente exige que você o implante na sequência correta e conclua todas as etapas de implantação necessárias.

<div>

## <a name="deployment-sequence"></a>Sequência de implantação

Você pode implantar o servidor de chat persistente após implantar a topologia inicial, incluindo pelo menos um Lync Server 2013, um pool de front-end ou um servidor do Lync Server 2013, Standard Edition. Este tópico descreve como implantar o servidor de chat persistente adicionando-o a uma implantação existente.

</div>

<div>

## <a name="deployment-process"></a>Processo de implantação

A tabela a seguir lista as etapas básicas para implantar o servidor de chat persistente e fornece links para obter mais detalhes.

### <a name="persistent-chat-server-deployment-process"></a>Processo de implantação do servidor de chat persistente

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Tarefa</th>
<th>Etapas</th>
<th>Funções exigidas e associações em grupo</th>
<th>Tópicos relacionados</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Instalar pré-requisitos de hardware e software</strong></p></td>
<td><p>No hardware que atender aos requisitos do sistema, instale o seguinte:</p>
<ul>
<li><p>Nos servidores de front-end do servidor de chat persistente:</p></li>
</ul>
<ul>
<li><p>Um sistema operacional que atenda aos requisitos do sistema</p></li>
<li><p>Pré-requisitos de software para computadores que executam o Lync Server 2013</p></li>
<li><p>SQL Server no servidor que hospedará o banco de dados persistente do servidor de chat</p></li>
</ul>
<p>Se for necessário conformidade com o servidor de chat persistente:</p>
<ul>
<li><p>SQL Server no servidor que hospedará o banco de dados de conformidade do servidor de chat persistente</p></li>
</ul></td>
<td><p>Qualquer usuário que seja membro do grupo Administradores locais.</p></td>
<td><p><a href="lync-server-2013-supported-hardware.md">Hardware com suporte para o Lync Server 2013</a> na documentação de suporte</p>
<p><a href="lync-server-2013-server-software-and-infrastructure-support.md">Suporte de software e infraestrutura do servidor no Lync Server 2013</a> na documentação de suporte</p>
<p><a href="lync-server-2013-determining-your-system-requirements.md">Determinando seus requisitos de sistema para Lync Server 2013</a></p>
<p><a href="lync-server-2013-technical-requirements-for-persistent-chat-server.md">Requisitos técnicos para servidor de chat persistente no Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p><strong>Criar a topologia interna apropriada para dar suporte a servidor de chat persistente (e, opcionalmente, conformidade de chat persistente)</strong></p></td>
<td><p>Execute o construtor de topologias para adicionar um pool de servidores de chat persistentes à sua topologia:</p>
<ul>
<li><p>Adicionar componentes persistentes do servidor de chat à topologia</p></li>
<li><p>Criar um banco de dados SQL Server para o repositório persistente do servidor de chat (e um SQL Server de backup para recuperação de desastres)</p></li>
<li><p>Definir um novo repositório de arquivos do Lync ou usar um repositório de arquivos existente do Lync para arquivos persistentes do servidor de chat</p></li>
<li><p>Associar o pool do Lync Server 2013 que pode rotear solicitações para este pool do servidor de chat persistente</p></li>
</ul>
<p>Se a conformidade com Chat Persistente for necessária:</p>
<ul>
<li><p>Adicionar repositório de conformidade de chat persistente</p></li>
<li><p>Clique na caixa de seleção definição do pool de servidores de chat persistentes para habilitar a conformidade</p></li>
<li><p>Publicar a topologia</p></li>
</ul>
<p>Se você instalar o servidor de chat persistente na edição Standard, o nome de domínio totalmente qualificado (FQDN) do pool do servidor de chat persistente deve coincidir com o servidor Standard Edition e os bancos de dados do SQL Server são posicionados na instância do SQL Server Express no padrão Servidor de edição</p></td>
<td><p>Para definir uma topologia, uma canta membro do grupo de usuários local.</p>
<p>Para publicar a topologia, uma conta que seja membro do grupo Domain admins e do grupo RTCUniversalServerAdmins e o usuário também deve ter permissões de controle total (ler/gravar/modificar) no repositório de arquivos do Lync para arquivos de servidor de chat persistente (para que o construtor de topologias possa configurar as DACLs necessárias).</p></td>
<td><p><a href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adicionar um servidor de chat persistente à sua implantação no Lync Server 2013</a> na documentação de implantação</p></td>
</tr>
<tr class="odd">
<td><p><strong>Implantar Servidor de Chat Persistente</strong></p></td>
<td><p>Execute a instalação do Lync Server em todos os computadores que executam o servidor de chat persistente. A configuração do servidor de chat persistente está integrada ao assistente de implantação do Lync Server 2013 que fornece as instruções a seguir:</p>
<ul>
<li><p>Implantar repositório de gerenciamento local</p></li>
<li><p>Instalar serviços persistentes do servidor de chat</p></li>
<li><p>Solicitar e assinar certificados</p></li>
<li><p>Executar e iniciar os serviços</p></li>
</ul></td>
<td><p>Qualquer usuário que seja membro do grupo Administradores locais.</p></td>
<td><p><a href="lync-server-2013-deploying-persistent-chat-server.md">Implantando o servidor de chat persistente no Lync Server 2013</a> na documentação de implantação</p></td>
</tr>
<tr class="even">
<td><p><strong>Criar um administrador de Chat Persistente</strong></p></td>
<td><p>Adicionar usuários ao grupo de segurança CsPersistentChatAdministrator.</p></td>
<td><p>Qualquer usuário que seja membro dos administradores de domínio.</p></td>
<td><p><a href="lync-server-2013-adding-a-persistent-chat-administrator.md">Adicionar um administrador de chat persistente no Lync Server 2013</a> na documentação de implantação</p></td>
</tr>
<tr class="odd">
<td><p><strong>Configurar o Servidor de Chat Persistente</strong></p></td>
<td><p>Configurar usuários:</p>
<ul>
<li><p>O usuário deve ser habilitado pela política para acessar o servidor de chat persistente. Por padrão, a política está desativada para todos os usuários e pode ser definida nos escopos global/site/pool/usuário.</p></li>
<li><p>Definir configurações</p></li>
</ul></td>
<td><p>O usuário deve ser membro do CsPersistentChatAdministrator. Para alterar a política, o usuário deve estar no CsUserAdministrator, no mínimo.</p></td>
<td><p><a href="lync-server-2013-configuring-persistent-chat-server.md">Configurando o servidor de chat persistente no Lync Server 2013</a> na documentação de implantação</p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> Você pode implantar um ou mais pools de servidores de chat persistentes. Oferecemos suporte a vários pools de servidores de chat persistentes por motivos regulatórios nos quais os dados gerados em determinada região são necessários para permanecer nessa região. Por exemplo, se você implantar um pool de servidores de chat persistente em Chicago e outro em Zurique para ficar em conformidade com as normas de dados na Suíça, os usuários poderão se conectar a salas nos pools de servidores de chat persistentes, contanto que tenham acesso.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

