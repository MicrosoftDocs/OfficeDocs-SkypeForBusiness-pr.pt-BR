---
title: Requisitos de IIS para pools de front-ends e servidores Standard Edition
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IIS requirements for Front End pools and Standard Edition servers
ms:assetid: e8a6c7ac-b6d5-4c7e-abe9-d8ea5eedbc62
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399038(v=OCS.15)
ms:contentKeyID: 48185888
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc92cc4c27f7af395a8e41bec26679a27010562d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037863"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="iis-requirements-for-front-end-pools-and-standard-edition-servers-in-lync-server-2013"></a>Requisitos de IIS para pools front-end e servidores Standard Edition no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-06-19_

Para servidores Standard Edition e servidores front-end, o instalador do Lync Server 2013 cria diretórios virtuais no IIS (serviços de informações da Internet) para as seguintes finalidades:

  - Para permitir que usuários baixem arquivos do Serviço de Catálogo de Endereços

  - Para permitir que os clientes obtenham atualizações

  - Para habilitar a conferência

  - Para permitir que usuários baixem o conteúdo das reuniões

  - Para permitir que usuários expandam grupos de distribuição

  - Para habilitar a conferência telefônica

  - Para habilitar recursos do grupo de resposta

Além disso, a atualização cumulativa para Lync Server 2010: instalador de novembro de 2011 cria diretórios virtuais no IIS para os seguintes objetivos:

  - Em servidores front-end ou servidores Standard Edition para suportar a funcionalidade de mobilidade, como mensagens instantâneas (IM) e presença, em dispositivos móveis

  - Em servidores front-end ou servidores Standard Edition e em diretores para permitir que os dispositivos móveis descubram automaticamente os recursos de mobilidade



> [!NOTE]
> Se você estiver implantando a mobilidade, recomendamos o uso do IIS 7.5. O instalador do serviço de mobilidade do Lync Server define alguns sinalizadores do ASP.NET para melhorar o desempenho. O IIS 7.5 é instalado por padrão no Windows Server 2008 R2 e o instalador do Serviço de Mobilidade altera automaticamente as configurações do ASP.NET. Se você usar o IIS 7.0 no Windows Server 2008, será necessário alterar manualmente essas configurações.



O Lync Server requer a instalação dos seguintes módulos do IIS:


> [!IMPORTANT]
> Se sua organização exigir que você localize o IIS e todos os serviços Web em uma unidade diferente da unidade do sistema, você poderá alterar o caminho do local de instalação dos arquivos do Lync Server na caixa de diálogo Configurar. Se você instalar os arquivos de instalação nesse caminho, incluindo o OCSCore. msi, o restante dos arquivos do Lync Server também será implantado nessa unidade. Para obter detalhes sobre como realocar o INETPUB implantado pelo Windows Server Manager ao instalar <A href="http://go.microsoft.com/fwlink/p/?linkid=216888">http://go.microsoft.com/fwlink/p/?linkId=216888</A>o IIS, consulte.


  - Conteúdo estático

  - Documento padrão

  - Erros HTTP

  - ASP.NET

  - Extensibilidade .NET

  - Extensões Internet Server API (ISAPI)

  - Filtros ISAPI

  - Log HTTP

  - Ferramentas de log

  - Rastreia

  - Autenticação do Windows

  - Requisição de filtro

  - Compressão de conteúdo estático

  - Compactação de conteúdo dinâmico

  - Console de gerenciamento IIS

  - Ferramentas e scripts de gerenciamento IIS

  - Autenticação anônima (instalada por padrão quando o IIS é instalado)

  - Autenticação de mapeamento de certificado de cliente

A tabela a seguir relaciona os URIs dos diretórios virtuais para acesso interno e os recursos do sistema de arquivos a que se referem.

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
<th>URI de diretório virtual</th>
<th>Refere-se a</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Servidor de Catálogo de Endereços</p></td>
<td><p>https://&lt;interno FQDN&gt;/ABS/int/Handler</p></td>
<td><p>Localização de arquivos de download do Serviço de Catálogo de Endereços para usuários internos.</p></td>
</tr>
<tr class="even">
<td><p>Serviço de descoberta automática</p></td>
<td><p>https://&lt;interno FQDN&gt;/autodiscover</p></td>
<td><p>Local do serviço de descoberta automática do Lync Server que localiza recursos de mobilidade para usuários de dispositivos móveis internos.</p></td>
</tr>
<tr class="odd">
<td><p>Atualizações de cliente</p></td>
<td><p>http://&lt;interno FQDN&gt;/AutoUpdate/int</p></td>
<td><p>Localização de arquivos de atualização para clientes baseados em computador interno.</p></td>
</tr>
<tr class="even">
<td><p>Fere</p></td>
<td><p>http://&lt;interno FQDN&gt;/conf/int</p></td>
<td><p>Localização de recursos de conferência para usuários internos.</p></td>
</tr>
<tr class="odd">
<td><p>Atualizações de dispositivos</p></td>
<td><p>http://&lt;/FQDN&gt;interno/DeviceUpdateFiles_Int</p></td>
<td><p>Localização de arquivos de atualização de dispositivo de UC para dispositivos internos de UC.</p></td>
</tr>
<tr class="even">
<td><p>Atenda</p></td>
<td><p>http://&lt;interno FQDN&gt;/etc/Place/NULL</p></td>
<td><p>Localização do conteúdo de reunião para usuários internos.</p></td>
</tr>
<tr class="odd">
<td><p>Serviço de Mobilidade</p></td>
<td><p>https://&lt;interno FQDN&gt;/MCX</p></td>
<td><p>Localização dos recursos do Serviço de Mobilidade para usuários de dispositivo móvel internos.</p></td>
</tr>
<tr class="even">
<td><p>Serviço de Consulta na Web ao Catálogo de Endereços e Expansão de Grupo</p></td>
<td><p>http://&lt;interno FQDN&gt;/GroupExpansion/int/Service.asmx</p></td>
<td><p>Localização do serviço web que permite a expansão de grupos para usuários internos. Além disso, o local do serviço de consulta à Web do catálogo de endereços que fornece informações de lista de endereços global para clientes móveis internos do Lync Mobile Microsoft Lync 2010.</p></td>
</tr>
<tr class="odd">
<td><p>Conferência por telefone</p></td>
<td><p>http://&lt;interno FQDN&gt;/PhoneConferencing/int</p></td>
<td><p>Localização de dados de conferência por telefone para usuários internos.</p></td>
</tr>
<tr class="even">
<td><p>Atualizações de dispositivos</p></td>
<td><p>http://&lt;interno FQDN&gt;/RequestHandler</p></td>
<td><p>Localização do Manipulador de Solicitações do Serviço Web de Atualização de Dispositivo que permite aos dispositivos de UC internos carregar logs e verificar a existência de atualizações.</p></td>
</tr>
<tr class="odd">
<td><p>Aplicativo Grupo de Resposta</p></td>
<td><p>http://&lt;interno FQDN&gt;/RgsConfig</p>
<p>http://&lt;interno FQDN&gt;/RgsClients</p></td>
<td><p>Localização da Ferramenta de Configuração de Grupo de Resposta.</p></td>
</tr>
</tbody>
</table>


> [!NOTE]
> Para pools de front-ends em uma configuração consolidada, você deve implantar o IIS para poder adicionar servidores ao pool.


<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="segurança" alt="security" />Observação de segurança:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Você deve usar o snap-in administrativo do IIS para atribuir o certificado usado pelo servidor de componente da web do IIS.</td>
</tr>
</tbody>
</table>



</div>

<span> </span>

</div>

</div>

</div>

