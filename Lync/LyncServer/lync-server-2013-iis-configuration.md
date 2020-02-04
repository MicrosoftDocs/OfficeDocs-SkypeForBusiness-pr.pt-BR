---
title: 'Lync Server 2013: Configuração de IIS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IIS configuration
ms:assetid: b458babf-bf64-43f0-8a8e-612f5096b63c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412871(v=OCS.15)
ms:contentKeyID: 48185169
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0cb8fe023d872ff19e29beb329488304048895b2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729321"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="iis-configuration-in-lync-server-2013"></a>Configuração de IIS no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-02-17_

Para concluir esse procedimento com êxito, você deve estar conectado ao servidor minimamente como um administrador local e um usuário do domínio.

Antes de configurar e instalar o servidor front-end para o Lync Server 2013, Standard Edition ou o primeiro servidor front-end em um pool, instale e configure a função do servidor e os serviços Web para serviços de informações da Internet (IIS).

<div class=" ">


> [!IMPORTANT]  
> Se a sua organização exigir que você localize o IIS e todos os serviços Web em uma unidade diferente da unidade do sistema, você poderá alterar o caminho do local de instalação dos arquivos do Lync Server 2013 na caixa de diálogo Configurar ao instalar inicialmente o Lync Server 2013 Ferramentas administrativas. Instale as ferramentas administrativas antes de instalar o IIS. Se você instalar os arquivos de instalação nesse caminho, incluindo OCSCore. msi, o restante dos arquivos do Lync Server 2013 também será implantado nessa unidade. Para o dtails, confira <A href="lync-server-2013-install-lync-server-administrative-tools.md">instalar as ferramentas administrativas do Lync Server 2013</A>. Para obter detalhes sobre como realocar o INETPUB implantado pelo Windows Server Manager ao instalar <A href="http://go.microsoft.com/fwlink/p/?linkid=216888">http://go.microsoft.com/fwlink/p/?linkId=216888</A>o IIS, consulte.



</div>

A tabela a seguir indica os serviços de função do IIS 7,5 necessários.

### <a name="iis-75-role-services"></a>Serviços de função do IIS 7,5

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Título da função</th>
<th>Serviço de função</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Recursos comuns de HTTP instalados</p></td>
<td><p>Conteúdo estático</p></td>
</tr>
<tr class="even">
<td><p>Recursos comuns de HTTP instalados</p></td>
<td><p>Documento padrão</p></td>
</tr>
<tr class="odd">
<td><p>Recursos comuns de HTTP instalados</p></td>
<td><p>Erros de HTTP</p></td>
</tr>
<tr class="even">
<td><p>Desenvolvimento de aplicativos</p></td>
<td><p>ASP.NET</p>
<p>O Windows Server 2012 também requer o ASP. NET 4.5</p></td>
</tr>
<tr class="odd">
<td><p>Desenvolvimento de aplicativos</p></td>
<td><p>Extensibilidade .NET</p></td>
</tr>
<tr class="even">
<td><p>Desenvolvimento de aplicativos</p></td>
<td><p>Extensões da API de servidor da Internet (ISAPI)</p></td>
</tr>
<tr class="odd">
<td><p>Desenvolvimento de aplicativos</p></td>
<td><p>Filtros ISAPI</p></td>
</tr>
<tr class="even">
<td><p>Integridade e diagnóstico</p></td>
<td><p>Log HTTP</p></td>
</tr>
<tr class="odd">
<td><p>Integridade e diagnóstico</p></td>
<td><p>Ferramentas de log</p></td>
</tr>
<tr class="even">
<td><p>Integridade e diagnóstico</p></td>
<td><p>Rastreamento</p></td>
</tr>
<tr class="odd">
<td><p>Segurança</p></td>
<td><p>Autenticação anônima (instalada e habilitada por padrão)</p></td>
</tr>
<tr class="even">
<td><p>Segurança</p></td>
<td><p>Autenticação do Windows</p></td>
</tr>
<tr class="odd">
<td><p>Segurança</p></td>
<td><p>Autenticação de mapeamento de certificado do cliente</p></td>
</tr>
<tr class="even">
<td><p>Segurança</p></td>
<td><p>Filtragem de solicitações</p></td>
</tr>
<tr class="odd">
<td><p>Desempenho</p></td>
<td><p>Compactação de conteúdo estático</p>
<p>Compactação de conteúdo dinâmico</p></td>
</tr>
<tr class="even">
<td><p>Ferramentas de gerenciamento</p></td>
<td><p>Console de gerenciamento IIS</p></td>
</tr>
<tr class="odd">
<td><p>Ferramentas de gerenciamento</p></td>
<td><p>Ferramentas e scripts de gerenciamento IIS</p></td>
</tr>
</tbody>
</table>


No sistema operacional Windows Server 2008 R2 SP1 x64, você pode usar o Windows PowerShell 2,0. Primeiro, você deve importar o módulo ServerManager e instalar os serviços de função e função do IIS 7,5.

   ```PowerShell
    Import-Module ServerManager
   ```

   ```PowerShell
    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Scripting-Tools, Web-Windows-Auth, Web-Asp-Net, Web-Log-Libraries, Web-Http-Tracing, Web-Stat-Compression, Web-Dyn-Compression, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Errors, Web-Http-Logging, Web-Net-Ext, Web-Client-Auth, Web-Filtering, Web-Mgmt-Console
   ```

<div class=" ">


> [!NOTE]  
> A autenticação anônima é instalada por padrão com a função de servidor IIS. Você pode gerenciar a autenticação anônima após a instalação do IIS. Para obter detalhes, consulte "habilitar autenticação anônima (IIS 7)" <A href="http://go.microsoft.com/fwlink/p/?linkid=203935">http://go.microsoft.com/fwlink/p/?linkId=203935</A>em.



</div>

A tabela a seguir indica os serviços de função do IIS 8,0 e do IIS 8,5 necessários para o Windows Server 2012 e o Windows Server 2012 R2.

<div class=" ">


> [!NOTE]  
> Para o Windows Server 2012 e o Windows Server 2012 R2, o cmdlet Add-WindowsFeature foi substituído pelo cmdlet Install-WindowsFeature. Para obter detalhes, consulte <A href="http://go.microsoft.com/fwlink/p/?linkid=392274">install-WindowsFeature</A>.



</div>

### <a name="iis-80-and-iis-85-role-services"></a>Serviços de função do IIS 8,0 e do IIS 8,5

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Título da função</th>
<th>Serviço de função</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Servidor Web (IIS)</p></td>
<td><p>Servidor Web</p></td>
</tr>
<tr class="even">
<td><p>Recursos HTTP Comuns</p></td>
<td><p>Documento padrão</p></td>
</tr>
<tr class="odd">
<td><p>Recursos HTTP Comuns</p></td>
<td><p>Pesquisa de diretório</p></td>
</tr>
<tr class="even">
<td><p>Recursos HTTP Comuns</p></td>
<td><p>Erros HTTP</p></td>
</tr>
<tr class="odd">
<td><p>Recursos HTTP Comuns</p></td>
<td><p>Conteúdo estático</p></td>
</tr>
<tr class="even">
<td><p>Recursos HTTP Comuns</p></td>
<td><p>Redirecionamento de HTTP</p></td>
</tr>
<tr class="odd">
<td><p>Integridade e Diagnósticos</p></td>
<td><p>Log HTTP</p></td>
</tr>
<tr class="even">
<td><p>Integridade e Diagnósticos</p></td>
<td><p>Ferramentas de log</p></td>
</tr>
<tr class="odd">
<td><p>Integridade e Diagnósticos</p></td>
<td><p>Monitor de solicitação</p></td>
</tr>
<tr class="even">
<td><p>Integridade e Diagnósticos</p></td>
<td><p>Rastreamento</p></td>
</tr>
<tr class="odd">
<td><p>Segurança</p></td>
<td><p>Requisição de filtro</p></td>
</tr>
<tr class="even">
<td><p>Segurança</p></td>
<td><p>Autenticação básica</p></td>
</tr>
<tr class="odd">
<td><p>Segurança</p></td>
<td><p>Autenticação de mapeamento de certificado de cliente</p></td>
</tr>
<tr class="even">
<td><p>Segurança</p></td>
<td><p>Autenticação do Windows</p></td>
</tr>
<tr class="odd">
<td><p>Desenvolvimento do aplicativo</p></td>
<td><p>.Net Extensibility 3,5</p></td>
</tr>
<tr class="even">
<td><p>Desenvolvimento do aplicativo</p></td>
<td><p>.Net Extensibility 4,5</p></td>
</tr>
<tr class="odd">
<td><p>Desenvolvimento do aplicativo</p></td>
<td><p>ASP.Net 3,5</p></td>
</tr>
<tr class="even">
<td><p>Desenvolvimento do aplicativo</p></td>
<td><p>ASP.Net 4,5</p></td>
</tr>
<tr class="odd">
<td><p>Desenvolvimento do aplicativo</p></td>
<td><p>Extensões ISAPI</p></td>
</tr>
<tr class="even">
<td><p>Desenvolvimento do aplicativo</p></td>
<td><p>Filtros ISAPI</p></td>
</tr>
<tr class="odd">
<td><p>Desenvolvimento do aplicativo</p></td>
<td><p>Inclusões do lado do servidor</p></td>
</tr>
<tr class="even">
<td><p>Ferramentas de gerenciamento</p></td>
<td><p>Console de gerenciamento IIS</p></td>
</tr>
<tr class="odd">
<td><p>Ferramentas de gerenciamento</p></td>
<td><p>Compatibilidade de metabase do IIS 6</p></td>
</tr>
<tr class="even">
<td><p>Ferramentas de gerenciamento</p></td>
<td><p>Ferramentas e scripts de gerenciamento IIS</p></td>
</tr>
<tr class="odd">
<td><p>Recursos da .net 3,5 Framework</p></td>
<td><p>.Net 3,5 Framework</p></td>
</tr>
<tr class="even">
<td><p>Recursos da .NET 4,5 Framework</p></td>
<td><p>.NET Framework 4,5</p></td>
</tr>
<tr class="odd">
<td><p>Recursos da .NET 4,5 Framework</p></td>
<td><p>ASP.Net 4,5</p></td>
</tr>
<tr class="even">
<td><p>Recursos da .NET 4,5 Framework</p></td>
<td><p>Ativação HTTP</p></td>
</tr>
<tr class="odd">
<td><p>Recursos da .NET 4,5 Framework</p></td>
<td><p>Compartilhamento de porta TCP</p></td>
</tr>
<tr class="even">
<td><p>Serviço de transferência inteligente em segundo plano</p></td>
<td><p>Extensões de servidor IIS</p></td>
</tr>
<tr class="odd">
<td><p>Serviços de tinta e manuscrito</p></td>
<td><p>Serviços de tinta e manuscrito</p></td>
</tr>
<tr class="even">
<td><p>Media Foundation</p></td>
<td><p>Media Foundation</p></td>
</tr>
<tr class="odd">
<td><p>Interfaces do usuário e infraestrutura</p></td>
<td><p>Infraestrutura e ferramentas de gerenciamento gráfico</p></td>
</tr>
<tr class="even">
<td><p>Interfaces do usuário e infraestrutura</p></td>
<td><p>Experiência Desktop</p></td>
</tr>
<tr class="odd">
<td><p>Interfaces do usuário e infraestrutura</p></td>
<td><p>Shell gráfico do servidor</p></td>
</tr>
<tr class="even">
<td><p>Windows Identity Foundation 3.5</p></td>
<td><p>Windows Identity Foundation 3.5</p></td>
</tr>
<tr class="odd">
<td><p>Serviço de ativação de processos do Windows</p></td>
<td><p>Modelo de processo</p></td>
</tr>
<tr class="even">
<td><p>Serviço de ativação de processos do Windows</p></td>
<td><p>APIs de configuração</p></td>
</tr>
</tbody>
</table>


No Windows Server 2012 e no Windows Server 2012 R2, você pode usar o Windows PowerShell 3,0 para instalar os requisitos do IIS. Usando o módulo ServerManager no Windows PowerShell 3,0, digite:

   ```PowerShell
    Import-Module ServerManager
   ```

   ```PowerShell
    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-Framework-45-Core, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Console, Web-Mgmt-Compat, Windows-Identity-Foundation, Server-Media-Foundation, BITS -Source D:\sources\sxs
   ```

<div class=" ">


> [!IMPORTANT]  
> Novo com o Windows Server 2012 é o parâmetro-source que define onde a mídia de origem do Windows Server 2012 pode ser encontrada. A mídia pode ser definida como uma unidade de DVD (por exemplo, D:\Sources\Sxs) ou em um compartilhamento de rede em que os arquivos de mídia foram copiados ( \\por exemplo, fileserver\windows2012\sources\Sxs).



</div>

<div>

## <a name="see-also"></a>Confira também


[Requisitos de IIS para pools Front-End pools e servidores Standard Edition no Lync Server 2013](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

