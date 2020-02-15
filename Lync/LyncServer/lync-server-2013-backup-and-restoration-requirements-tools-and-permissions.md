---
title: 'Lync Server 2013: requisitos de backup e restauração: ferramentas e permissões'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Backup and restoration requirements: tools and permissions'
ms:assetid: 35ec2e33-f33e-4f84-9e64-6550fd78aa52
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202171(v=OCS.15)
ms:contentKeyID: 51541465
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b86f283aae05985ea903a17dfb15dff83574c42f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029212"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-requirements-in-lync-server-2013-tools-and-permissions"></a>Requisitos de backup e restauração no Lync Server 2013: ferramentas e permissões

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-17_

Este tópico identifica as ferramentas que você pode usar para fazer o backup e restaurar o Lync Server 2013, as permissões necessárias e se é possível executar comandos remotamente ou localmente. Especificamente, este tópico se concentra nas ferramentas fornecidas com o Lync Server para backup e restauração.

<div>

## <a name="backups"></a>Fazer

Para fazer backup do Lync Server, use as ferramentas identificadas na tabela a seguir. Todos os comandos de que você precisa para fazer o backup do Lync Server podem ser executados em script e podem ser executados remotamente.

### <a name="tools-for-backing-up-lync-server"></a>Ferramentas para backup do Lync Server

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Para fazer o backup:</th>
<th>Use esta ferramenta ou cmdlet:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Dados de configuração da topologia (Xds.mdf)</p></td>
<td><p>Export-CsConfiguration</p></td>
</tr>
<tr class="even">
<td><p>Dados do serviço de informação da localização (E9-1-1) (Lis.mdf)</p></td>
<td><p>Export-CsLisConfiguration</p></td>
</tr>
<tr class="odd">
<td><p>Dados da configuração do Grupo de Respostas (RgsConfig.mdf)</p></td>
<td><p>Export-CsRgsConfiguration</p></td>
</tr>
<tr class="even">
<td><p>Dados de usuário persistente (banco de dados Rtcxds. MDF)</p>
<p>IDs de conferência</p></td>
<td><p>Export-CsUserData</p></td>
</tr>
<tr class="odd">
<td><ul>
<li><p>Banco de dados de arquivamento (LcsLog.mdf)</p></li>
<li><p>Banco de dados do registro de detalhes da chamada de monitoração (LcsCDR.mdf)</p></li>
<li><p>Banco de dados de QoE de monitoração (QoEMetrics.mdf)</p></li>
</ul></td>
<td><p>Ferramenta de banco de dados do SQL Server, como o SQL Server Management Studio</p></td>
</tr>
<tr class="even">
<td><p>Banco de dados de chat persistente (MGC. MDF)</p></td>
<td><p>Procedimentos de backup do SQL Server ou Export-CsPersistentChatData. Export-CsPersistentChatData exporta dados de chat persistente como um arquivo.</p></td>
</tr>
<tr class="odd">
<td><p>Todos os repositórios de arquivos: repositório de arquivos do Lync Server, repositório de arquivos de arquivamento</p>
<div>

> [!NOTE]  
> Não faça o backup dos arquivos com o nome <STRONG>Meeting.Active</STRONG>. Eles estão em uso e são bloqueados enquanto a reunião ocorre.


</div></td>
<td><p>Ferramenta de gerenciamento de sistema de arquivos padrão, como o Robocopy.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="restoration"></a>Tentativas

Para restaurar o Lync Server, use as ferramentas da tabela a seguir. Todos os comandos que você precisa para restaurar o Lync Server podem ser controlados. Alguns podem ser executados remotamente, mas outros precisam ser executados localmente, conforme especificado na tabela a seguir.

### <a name="tools-for-restoring-lync-server"></a>Ferramentas para restaurar o Lync Server

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Para fazer isso:</th>
<th>Use esta ferramenta ou cmdlet:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Crie um computador novo ou limpo</p></td>
<td><ul>
<li><p>Software de instalação do sistema operacional Windows</p></li>
<li><p>Software de instalação do SQL Server</p></li>
<li><p>Certifica o snap-in do Console de Gerenciamento Microsoft (MMC), se estiver restaurando certificados com uma chave privada exportável</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Restaure os dados do repositório de arquivos</p></td>
<td><p>Ferramenta padrão de gerenciamento de sistema de arquivos, como o Robocopy</p></td>
</tr>
<tr class="odd">
<td><p>Recrie bancos de dados vazios e defina permissões para o seguinte:</p>
<ul>
<li><p>Repositório de Gerenciamento Central</p></li>
<li><p>Servidor de Back-End</p></li>
<li><p>Banco de dados de monitoração</p></li>
<li><p>Banco de dados de arquivamento</p></li>
</ul></td>
<td><p>Install-CsDatabase</p></td>
</tr>
<tr class="even">
<td><p>Restaurar o ponteiro dos serviços de domínio do Active Directory para o repositório de gerenciamento central</p>
<div>

> [!NOTE]  
> Se você perder o ponto de conexão de serviço a qualquer momento, você pode executar este cmdlet novamente.


</div></td>
<td><p>Set-CsConfigurationStoreLocation</p></td>
</tr>
<tr class="odd">
<td><p>Importar a topologia, as políticas e as definições de configuração para o repositório de gerenciamento central (XDS. MDF)</p></td>
<td><p>Import-CsConfiguration</p></td>
</tr>
<tr class="even">
<td><p>Publicar e habilitar a topologia</p></td>
<td><p>Construtor de Topologias</p>
<p>- ou -</p>
<p>Publish-CsTopology e Enable-CsTopology</p></td>
</tr>
<tr class="odd">
<td><p>Ative a última topologia publicada</p></td>
<td><p>Enable-CsTopology</p></td>
</tr>
<tr class="even">
<td><p>Reinstalar componentes do Lync Server</p></td>
<td><p>Instalação do Lync Server</p>
<div>

> [!NOTE]  
> Localizado na pasta de instalação do Lync Server ou na mídia em \setup\amd64\Setup.exe.


</div></td>
</tr>
<tr class="odd">
<td><p>Restaure os dados informação da localização (E9-1-1) (Lis.mdf)</p></td>
<td><p>Import-CsLisConfiguration</p></td>
</tr>
<tr class="even">
<td><p>Restaurar dados persistentes do usuário (Rtcxds. MDF)</p></td>
<td><p>Import-CsUserData</p></td>
</tr>
<tr class="odd">
<td><p>Dados da configuração do Grupo de Respostas (RgsConfig.mdf)</p></td>
<td><p>Import-CsRgsConfiguration</p>
<div>

> [!NOTE]  
> Se a configuração estiver sendo restaurada em um pool recentemente implantado que não tenha dados de grupo de resposta no banco de dados, use a opção – OverwriteOwner. Use essa opção mesmo se os dados que estão sendo restaurados estiverem em um pool com o mesmo FQDN (nome de domínio totalmente qualificado). Caso contrário, a importação não terá êxito, devido aos objetos de contato para os grupos de resposta já existentes no Active Directory.


</div></td>
</tr>
<tr class="even">
<td><p>Restaure os bancos de dados a seguir:</p>
<ul>
<li><p>Banco de dados de arquivamento (LcsLog.mdf)</p></li>
<li><p>Bancos de dados de monitoração: banco de dados de registro de detalhes da chamada (LcsCDR.mdf) e banco de dados de QoE (QoEMetrics.mdf)</p></li>
</ul></td>
<td><p>Ferramentas de gerenciamento de banco de dados do SQL Server</p></td>
</tr>
<tr class="odd">
<td><p>Banco de dados de chat persistente (MGS. MDF)</p></td>
<td><p>Procedimentos de restauração do SQL Server ou Import-CsPersistentChatData. Você pode usar Import-CsPersistentChatData com um arquivo criado por Export-CsPersistentChatData, e os dados serão importados para o banco de dados de chat persistente.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="required-permissions"></a>Permissões exigidas

Os usuários devem ser membros do grupo **RTCUniversalServerAdmins** para executar todos os comandos descritos neste tópico. A maioria dos comandos de backup e restauração não oferece suporte ao controle de acesso baseado em função (RBAC). Duas exceções são os cmdlets de chat persistente Export-CsPersistentChatData e Import-CsPersistentChatData, que devem ser executados por um usuário que seja membro do grupo CsPersistentChatAdministrator. Para executar o assistente de implantação do Lync Server, um usuário também deve ser um membro do grupo de administradores locais.

</div>

</div>

<span> </span>

</div>

</div>

</div>

