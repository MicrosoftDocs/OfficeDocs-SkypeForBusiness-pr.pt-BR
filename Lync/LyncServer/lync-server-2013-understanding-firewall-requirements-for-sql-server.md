---
title: 'Lync Server 2013: Noções básicas sobre requisitos de firewall para o SQL Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Understanding firewall requirements for SQL Server
ms:assetid: 31d7df2c-589f-465e-be74-cf6767db190d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425818(v=OCS.15)
ms:contentKeyID: 48183781
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f836c71023defd6c826ab763d36e395a1240d3da
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527738"
---
# <a name="understanding-firewall-requirements-for-sql-server-with-lync-server-2013"></a>Noções básicas sobre requisitos de firewall para o SQL Server com o Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-21_

Para uma implantação do Standard Edition, as exceções de firewall são criadas automaticamente durante a instalação do Lync Server 2013. No entanto, para implantações Enterprise Edition, você deve configurar as exceções de firewall manualmente no servidor back-end do SQL Server. O protocolo TCP/IP permite o uso de determinada porta uma vez para um certo endereço IP. Isso significa que, para o servidor baseado no SQL Server, é possível atribuir a instância de banco de dados padrão à porta TCP padrão 1433. Para qualquer outra instância, você precisa usar o SQL Server Configuration Manager para atribuir portas exclusivas e não usadas. Este tópico aborda:

  - Requisitos para uma exceção de firewall ao usar a instância padrão

  - Requisitos para uma exceção de firewall para o serviço SQL Server Browser

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
<td><p>Entrada para SQL Server</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="requirements-for-a-firewall-exception-for-the-sql-server-browser-service"></a>Requisitos para uma exceção de firewall para o serviço SQL Server Browser

O serviço SQL Server Browser localizará as instâncias do banco de dados e comunicará a porta que a instância (nomeada ou padrão) está configurada para usar.


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
<td><p>VIA</p></td>
<td><p>1434</p></td>
<td><p>Entrada</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="requirements-for-static-listening-ports-when-using-named-instances"></a>Requisitos para portas de escuta estáticas ao usar instâncias nomeadas

Ao usar instâncias nomeadas na configuração do SQL Server para bancos de dados que dão suporte ao Lync Server 2013, configure as portas estáticas usando o SQL Server Configuration Manager. Após a atribuição das portas estáticas a cada instância nomeada, crie exceções para cada porta estática no firewall.


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

A documentação do Microsoft SQL Server 2012 fornece orientação detalhada sobre como configurar o acesso de firewall para os bancos de dados. Para obter detalhes sobre o Microsoft SQL Server 2012, consulte "Configurando o Firewall do Windows para permitir o acesso ao SQL Server" em [https://go.microsoft.com/fwlink/p/?linkId=218031](https://go.microsoft.com/fwlink/p/?linkid=218031) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

