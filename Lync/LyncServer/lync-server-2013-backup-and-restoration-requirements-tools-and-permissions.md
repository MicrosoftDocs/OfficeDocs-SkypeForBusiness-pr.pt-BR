---
title: 'Lync Server 2013: requisitos de backup e restauração: ferramentas e permissões'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: 'Backup and restoration requirements: tools and permissions'
ms:assetid: 35ec2e33-f33e-4f84-9e64-6550fd78aa52
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202171(v=OCS.15)
ms:contentKeyID: 51541465
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 53128d99abfd438c174b98544889781b5f29b57b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836751"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-requirements-in-lync-server-2013-tools-and-permissions"></a>Requisitos de backup e restauração no Lync Server 2013: ferramentas e permissões

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-17_

Este tópico identifica as ferramentas que você pode usar para fazer backup e restaurar o Lync Server 2013, as permissões necessárias e se pode executar comandos remotamente ou localmente. Especificamente, este tópico se concentra em ferramentas fornecidas com o Lync Server para backup e restauração.

<div>

## <a name="backups"></a>Fazer

Para fazer backup do Lync Server, use as ferramentas identificadas na tabela a seguir. Todos os comandos de que você precisa para fazer backup do Lync Server podem ser executados em script e podem ser executados remotamente.

### <a name="tools-for-backing-up-lync-server"></a>Ferramentas para fazer backup do Lync Server

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Para fazer backup do seguinte:</th>
<th>Use esta ferramenta ou cmdlet:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Dados de configuração de topologia (XDS. MDF)</p></td>
<td><p>Export-CsConfiguration</p></td>
</tr>
<tr class="even">
<td><p>Dados do serviço de informações de localização (E9-1-1) (LIS. MDF)</p></td>
<td><p>Export-CsLisConfiguration</p></td>
</tr>
<tr class="odd">
<td><p>Dados de configuração de grupo de resposta (RgsConfig. MDF)</p></td>
<td><p>Export-CsRgsConfiguration</p></td>
</tr>
<tr class="even">
<td><p>Dados de usuário persistente (banco de dados Rtcxds. MDF)</p>
<p>IDs de conferência</p></td>
<td><p>Export-CsUserData</p></td>
</tr>
<tr class="odd">
<td><ul>
<li><p>Banco de dados de arquivamento (LcsLog. MDF)</p></li>
<li><p>Monitorando o banco de dados de registros de detalhes de chamadas (LcsCDR. MDF)</p></li>
<li><p>Monitorando o banco de dados de QoE (QoEMetrics. MDF)</p></li>
</ul></td>
<td><p>Ferramenta de banco de dados do SQL Server, como o SQL Server Management Studio</p></td>
</tr>
<tr class="even">
<td><p>Banco de dados de chat persistente (MGC. MDF)</p></td>
<td><p>Procedimentos de backup do SQL Server ou Export-CsPersistentChatData. Export-CsPersistentChatData exporta dados de chat persistente como um arquivo.</p></td>
</tr>
<tr class="odd">
<td><p>Todas as lojas de arquivos: repositório de arquivos do Lync Server, arquivando repositório de arquivos</p>
<div>

> [!NOTE]  
> Arquivos chamados <STRONG>Meeting. Active</STRONG> não devem ser backups. Esses arquivos estão em uso e são bloqueados durante o momento em que uma reunião ocorre.


</div></td>
<td><p>Ferramenta padrão de gerenciamento do sistema de arquivos, como Robocopy.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="restoration"></a>Recuperação

Para restaurar o Lync Server, use as ferramentas da tabela a seguir. Todos os comandos que você precisa para restaurar o Lync Server podem ser script. Alguns podem ser executados remotamente, mas outros precisam ser executados localmente, conforme especificado na tabela a seguir.

### <a name="tools-for-restoring-lync-server"></a>Ferramentas para restaurar o Lync Server

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Para fazer isto:</th>
<th>Use esta ferramenta ou cmdlet:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Criar um computador novo ou limpo</p></td>
<td><ul>
<li><p>Software de instalação do sistema operacional Windows</p></li>
<li><p>Software de instalação do SQL Server</p></li>
<li><p>Snap-in de certificados do console de gerenciamento Microsoft (MMC), se estiver restaurando certificados com uma chave privada exportável</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Restaurar dados de armazenamento de arquivos</p></td>
<td><p>Ferramenta padrão de gerenciamento do sistema de arquivos, como Robocopy</p></td>
</tr>
<tr class="odd">
<td><p>Recrie bancos de dados vazios e defina permissões para o seguinte:</p>
<ul>
<li><p>Repositório de Gerenciamento Central</p></li>
<li><p>Servidor Back-End</p></li>
<li><p>Banco de dados de monitoramento</p></li>
<li><p>Banco de dados de arquivamento</p></li>
</ul></td>
<td><p>Install-CsDatabase</p></td>
</tr>
<tr class="even">
<td><p>Restaurar o ponteiro dos serviços de domínio Active Directory para o repositório de gerenciamento central</p>
<div>

> [!NOTE]  
> Se você perder o ponto de conexão do serviço a qualquer momento, poderá executar novamente esse cmdlet.


</div></td>
<td><p>Set-CsConfigurationStoreLocation</p></td>
</tr>
<tr class="odd">
<td><p>Importar as configurações de topologia, políticas e configuração para o repositório de gerenciamento central (XDS. MDF)</p></td>
<td><p>Import-CsConfiguration</p></td>
</tr>
<tr class="even">
<td><p>Publicar e habilitar a topologia</p></td>
<td><p>Construtor de Topologias</p>
<p>or</p>
<p>Publicar-CsTopology e habilitar-CsTopology</p></td>
</tr>
<tr class="odd">
<td><p>Habilitar a última topologia publicada</p></td>
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
<td><p>Restaurar informações de localização (E9-1-1) dados (LIS. MDF)</p></td>
<td><p>Import-CsLisConfiguration</p></td>
</tr>
<tr class="even">
<td><p>Restaurar dados persistentes do usuário (Rtcxds. MDF)</p></td>
<td><p>Import-CsUserData</p></td>
</tr>
<tr class="odd">
<td><p>Restaurar dados de configuração de grupo de resposta (RgsConfig. MDF)</p></td>
<td><p>Import-CsRgsConfiguration</p>
<div>

> [!NOTE]  
> Se a configuração estiver sendo restaurada em um pool recém implantado sem dados de grupo de resposta no banco de dados, você deve usar a opção – OverwriteOwner. Use essa opção mesmo se os dados que estão sendo restaurados estiverem em um pool com o mesmo nome de domínio totalmente qualificado (FQDN). Caso contrário, a importação não terá êxito, devido aos objetos de contato para os grupos de resposta já existentes no Active Directory.


</div></td>
</tr>
<tr class="even">
<td><p>Restaure os seguintes bancos de dados:</p>
<ul>
<li><p>Banco de dados de arquivamento (LcsLog. MDF)</p></li>
<li><p>Monitorando bancos de dados: banco de dados de registros de detalhes de chamadas (LcsCDR. MDF) e banco de dados de QoE (QoEMetrics. MDF)</p></li>
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

## <a name="required-permissions"></a>Permissões necessárias

Os usuários devem ser membros do grupo **RTCUniversalServerAdmins** para executar todos os comandos descritos neste tópico. A maioria dos comandos de backup e restauração não oferece suporte ao controle de acesso baseado em função (RBAC). Duas exceções são os cmdlets de chat persistente Export-CsPersistentChatData e Import-CsPersistentChatData, que devem ser executados por um usuário que seja membro do grupo CsPersistentChatAdministrator. Para executar o assistente de implantação do Lync Server, um usuário também deve ser um membro do grupo Administradores locais.

</div>

</div>

<span> </span>

</div>

</div>

</div>

