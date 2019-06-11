---
title: Requisitos de IIS para pools Front-End pools e servidores Standard Edition
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: IIS requirements for Front End pools and Standard Edition servers
ms:assetid: e8a6c7ac-b6d5-4c7e-abe9-d8ea5eedbc62
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399038(v=OCS.15)
ms:contentKeyID: 48185888
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d804df614eab49eeabe82cca9d304e082d9ced3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829040"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="iis-requirements-for-front-end-pools-and-standard-edition-servers-in-lync-server-2013"></a>Requisitos de IIS para pools Front-End pools e servidores Standard Edition no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-06-19_

Para servidores padrão de edição e directors front-end, o instalador do Lync Server 2013 cria diretórios virtuais nos serviços de informações da Internet (IIS) para as seguintes finalidades:

  - Para permitir que os usuários baixem arquivos do serviço de catálogo de endereços

  - Para permitir que os clientes obtenham atualizações

  - Para habilitar a conferência

  - Para permitir que os usuários baixem o conteúdo da reunião

  - Para permitir que os usuários expandam os grupos de distribuição

  - Para habilitar a conferência telefônica

  - Para habilitar os recursos do grupo de resposta

Além disso, a atualização cumulativa do Lync Server 2010: instalador de novembro de 2011 cria diretórios virtuais no IIS para as seguintes finalidades:

  - Em servidores de front-end ou servidores Standard Edition para dar suporte à funcionalidade de mobilidade, como mensagens instantâneas (IM) e presença, em dispositivos móveis

  - Em servidores front-end ou servidores Standard Edition e em directors para permitir que dispositivos móveis descubram automaticamente os recursos de mobilidade



> [!NOTE]
> Se você estiver implantando a mobilidade, recomendamos que use o IIS 7,5. O instalador do serviço de mobilidade do Lync Server define alguns sinalizadores ASP.NET para melhorar o desempenho. O IIS 7,5 é instalado por padrão no Windows Server 2008 R2, e o instalador do serviço de mobilidade altera automaticamente as configurações do ASP.NET. Se você usa o IIS 7,0 no Windows Server 2008, é necessário alterar manualmente essas configurações.



O Lync Server exige a instalação dos seguintes módulos do IIS:


> [!IMPORTANT]
> Se a sua organização exigir que você localize o IIS e todos os serviços Web em uma unidade diferente da unidade do sistema, você poderá alterar o caminho do local de instalação dos arquivos do Lync Server na caixa de diálogo Configurar. Se você instalar os arquivos de instalação nesse caminho, incluindo OCSCore. msi, o restante dos arquivos do Lync Server também será implantado nessa unidade. Para obter detalhes sobre como realocar o INETPUB implantado pelo Windows Server Manager ao instalar <A href="http://go.microsoft.com/fwlink/p/?linkid=216888">http://go.microsoft.com/fwlink/p/?linkId=216888</A>o IIS, consulte.


  - Conteúdo estático

  - Documento padrão

  - Erros HTTP

  - ASP.NET

  - Extensibilidade .NET

  - Extensões da API de servidor da Internet (ISAPI)

  - Filtros ISAPI

  - Log HTTP

  - Ferramentas de log

  - Rastreamento

  - Autenticação do Windows

  - Requisição de filtro

  - Compressão de conteúdo estático

  - Compactação de conteúdo dinâmico

  - Console de gerenciamento IIS

  - Ferramentas e scripts de gerenciamento IIS

  - Autenticação anônima (instalada por padrão quando o IIS é instalado)

  - Autenticação de mapeamento de certificado de cliente

A tabela a seguir lista os URIs dos diretórios virtuais para acesso interno e os recursos do sistema de arquivos aos quais eles se referem.

### <a name="virtual-directories-for-internal-access"></a>Diretórios virtuais para acesso interno

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Recurso</th>
<th>URI do diretório virtual</th>
<th>Refere-se a</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Servidor de Catálogo de Endereços</p></td>
<td><p>https://&lt;interno FQDN&gt;/ABS/int/Handler</p></td>
<td><p>Local do servidor de catálogo de endereços baixar arquivos para usuários internos.</p></td>
</tr>
<tr class="even">
<td><p>Serviço de descoberta automática</p></td>
<td><p>https://&lt;interno FQDN&gt;/autodiscover</p></td>
<td><p>Localização do serviço de descoberta automática do Lync Server que localiza recursos de mobilidade para usuários de dispositivos móveis internos.</p></td>
</tr>
<tr class="odd">
<td><p>Atualizações de cliente</p></td>
<td><p>http://&lt;interno FQDN&gt;/AutoUpdate/int</p></td>
<td><p>Localização de arquivos de atualização para clientes internos baseados em computador.</p></td>
</tr>
<tr class="even">
<td><p>Conferência</p></td>
<td><p>http://&lt;interno FQDN&gt;/conf/int</p></td>
<td><p>Localização de recursos de conferência para usuários internos.</p></td>
</tr>
<tr class="odd">
<td><p>Atualizações de dispositivo</p></td>
<td><p>http://&lt;interno FQDN&gt;/DeviceUpdateFiles_Int</p></td>
<td><p>Localização de arquivos de atualização de dispositivos de comunicação unificada (UC) para dispositivos de comunicação unificada.</p></td>
</tr>
<tr class="even">
<td><p>Reunião</p></td>
<td><p>http://&lt;interno FQDN&gt;/etc/Place/NULL</p></td>
<td><p>Local do conteúdo da reunião para usuários internos.</p></td>
</tr>
<tr class="odd">
<td><p>Serviço de mobilidade</p></td>
<td><p>https://&lt;interno FQDN&gt;/MCX</p></td>
<td><p>Localização de recursos de serviço de mobilidade para usuários de dispositivos móveis internos.</p></td>
</tr>
<tr class="even">
<td><p>Serviço de consulta na Web de expansão de grupo e de catálogo de endereços</p></td>
<td><p>http://&lt;interno FQDN&gt;/GroupExpansion/int/Service.asmx</p></td>
<td><p>Localização do serviço Web que permite a expansão de grupo para usuários internos. Além disso, o local do serviço de consulta à Web do catálogo de endereços que fornece informações da lista de endereços global para clientes móveis internos do Lync móvel Microsoft Lync 2010.</p></td>
</tr>
<tr class="odd">
<td><p>Conferência telefônica</p></td>
<td><p>http://&lt;interno FQDN&gt;/PhoneConferencing/int</p></td>
<td><p>Local dos dados de conferência telefônica para usuários internos.</p></td>
</tr>
<tr class="even">
<td><p>Atualizações de dispositivo</p></td>
<td><p>http://&lt;interno FQDN&gt;/RequestHandler</p></td>
<td><p>Localização do manipulador de solicitação de serviço Web de atualização de dispositivo que permite que dispositivos de comunicação unificada internos carreguem logs e verifiquem se há atualizações.</p></td>
</tr>
<tr class="odd">
<td><p>Aplicativo Grupo de Resposta</p></td>
<td><p>http://&lt;interno FQDN&gt;/RgsConfig</p>
<p>http://&lt;interno FQDN&gt;/RgsClients</p></td>
<td><p>Local da ferramenta de configuração de grupo de resposta.</p></td>
</tr>
</tbody>
</table>


> [!NOTE]
> Para pools front-ends em uma configuração consolidada, você deve implantar o IIS antes de adicionar servidores ao pool.


<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="segurança" alt="security" />Observação de segurança:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Você deve usar o snap-in administrativo do IIS para atribuir o certificado usado pelo servidor do componente da Web do IIS.</td>
</tr>
</tbody>
</table>



</div>

<span> </span>

</div>

</div>

</div>

