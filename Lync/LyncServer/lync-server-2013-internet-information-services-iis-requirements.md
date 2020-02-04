---
title: 'Lync Server 2013: Requisitos de Serviços de Informações da Internet (IIS)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Internet Information Services (IIS) requirements
ms:assetid: 4f57a605-a8a9-4c5a-9a18-05ecb3d9ab6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398321(v=OCS.15)
ms:contentKeyID: 48184128
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f4b51ac4996e2556ced3ad91e15a6cc58a1623c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725801"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="internet-information-services-iis-requirements-in-lync-server-2013"></a>Requisitos de Serviços de Informações da Internet (IIS) no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-06-19_

Vários componentes do Lync Server 2013 exigem serviços de informações da Internet (IIS). Este tópico descreve os recursos específicos do IIS necessários para dar suporte ao Lync Server. Os tópicos desta seção descrevem os requisitos de componentes específicos para o IIS.

Quando a função servidor Web (IIS) estiver habilitada no Windows Server 2008, vários serviços de função serão instalados por padrão. A tabela a seguir descreve os serviços de função adicionais que devem ser instalados quando a função do servidor Web (IIS) estiver habilitada no Windows Server 2008.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Serviço de função</th>
<th>Recurso</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Recursos HTTP Comuns</p></td>
<td><p>Redirecionamento de HTTP</p></td>
</tr>
<tr class="even">
<td><p>Desenvolvimento do aplicativo</p></td>
<td><p>ASP.NET</p></td>
</tr>
<tr class="odd">
<td><p>Desenvolvimento do aplicativo</p></td>
<td><p>Extensibilidade .NET</p></td>
</tr>
<tr class="even">
<td><p>Desenvolvimento do aplicativo</p></td>
<td><p>Extensões ISAPI</p></td>
</tr>
<tr class="odd">
<td><p>Desenvolvimento do aplicativo</p></td>
<td><p>Filtros ISAPI</p></td>
</tr>
<tr class="even">
<td><p>Integridade e Diagnósticos</p></td>
<td><p>Ferramentas de log</p></td>
</tr>
<tr class="odd">
<td><p>Integridade e Diagnósticos</p></td>
<td><p>Rastreamento</p></td>
</tr>
<tr class="even">
<td><p>Segurança</p></td>
<td><p>Autenticação básica</p></td>
</tr>
<tr class="odd">
<td><p>Segurança</p></td>
<td><p>Autenticação do Windows</p></td>
</tr>
<tr class="even">
<td><p>Ferramentas de gerenciamento</p></td>
<td><p>Ferramentas e scripts de gerenciamento IIS</p></td>
</tr>
<tr class="odd">
<td><p>Ferramentas de gerenciamento</p></td>
<td><p>Compatibilidade com gerenciamento do IIS 6</p></td>
</tr>
</tbody>
</table>


<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="segurança" alt="security" />Observação de segurança:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Se você estiver usando o IIS 7,0 em um sistema operacional Windows Server 2008, a instalação do Lync Server desabilitará a autenticação do modo kernel no IIS.</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Requisitos de IIS para pools Front-End pools e servidores Standard Edition no Lync Server 2013](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

