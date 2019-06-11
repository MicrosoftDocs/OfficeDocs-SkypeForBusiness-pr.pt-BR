---
title: 'Lync Server 2013: Compreendendo os requisitos de firewall para Servidor SQL'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Understanding firewall requirements for SQL Server
ms:assetid: 31d7df2c-589f-465e-be74-cf6767db190d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425818(v=OCS.15)
ms:contentKeyID: 48183781
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 586985c3059e12d358249a71dc2435c3be9254f1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844570"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="understanding-firewall-requirements-for-sql-server-with-lync-server-2013"></a>Compreendendo os requisitos de firewall para Servidor SQL com Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-21_

Para uma implantação de edição padrão, as exceções de firewall são criadas automaticamente durante a instalação do Lync Server 2013. No entanto, para implantações do Enterprise Edition, você deve configurar as exceções de firewall manualmente no servidor back-end do SQL Server. O protocolo TCP/IP permite que uma determinada porta seja usada uma vez para um determinado endereço IP. Isso significa que, para o servidor baseado no SQL Server, você pode atribuir à instância de banco de dados padrão a porta TCP 1433. Para quaisquer outros casos, você precisará usar o Gerenciador de configuração do SQL Server para atribuir portas exclusivas e não utilizadas. Este tópico aborda:

  - Requisitos para uma exceção de firewall ao usar a instância padrão

  - Requisitos para uma exceção de firewall para o serviço do navegador do SQL Server

  - Requisitos para portas de escuta estática ao usar instâncias nomeadas

<div>

## <a name="requirements-for-a-firewall-exception-when-using-the-default-instance"></a>Requisitos para uma exceção de firewall ao usar a instância padrão

Se você estiver usando a instância padrão do SQL Server para qualquer banco de dados ao implantar o Lync Server 2013, os seguintes requisitos de regra de firewall são usados para ajudar a garantir a comunicação do pool de front-ends para a instância padrão do SQL Server.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Protocolo</th>
<th>Porta</th>
<th>Direção</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TCP</p></td>
<td><p>1433</p></td>
<td><p>Entrada do SQL Server</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="requirements-for-a-firewall-exception-for-the-sql-server-browser-service"></a>Requisitos para uma exceção de firewall para o serviço do navegador do SQL Server

O serviço de navegador do SQL Server localizará instâncias de banco de dados e comunicará a porta que a instância (nomeada ou padrão) está configurada para usar.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Protocolo</th>
<th>Porta</th>
<th>Direção</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>UDP</p></td>
<td><p>1434</p></td>
<td><p>Entrada</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="requirements-for-static-listening-ports-when-using-named-instances"></a>Requisitos para portas de escuta estática ao usar instâncias nomeadas

Ao usar instâncias nomeadas na configuração do SQL Server para bancos de dados que ofereçam suporte ao Lync Server 2013, você configura portas estáticas usando o Gerenciador de configuração do SQL Server. Após a atribuição das portas estáticas a cada instância nomeada, você cria exceções para cada porta estática do firewall.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Protocolo</th>
<th>Porta</th>
<th>Direção</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TCP</p></td>
<td><p>Definido estaticamente</p></td>
<td><p>Entrada</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="sql-server-documentation"></a>Documentação do SQL Server

A documentação do Microsoft SQL Server 2012 fornece orientações detalhadas sobre como configurar o acesso do firewall para bancos de dados. Para obter detalhes sobre o Microsoft SQL Server 2012, consulte "Configurando o Firewall do Windows para permitir [http://go.microsoft.com/fwlink/p/?linkId=218031](http://go.microsoft.com/fwlink/p/?linkid=218031)o acesso ao SQL Server" em.

</div>

</div>

<span> </span>

</div>

</div>

</div>

