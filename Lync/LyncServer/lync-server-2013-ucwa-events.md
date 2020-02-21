---
title: 'Lync Server 2013: eventos do UCWA'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UCWA events
ms:assetid: 26cb409d-f4e4-43c7-873f-b694702d491d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945621(v=OCS.15)
ms:contentKeyID: 51541461
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 950d52dfe86ebf4d5b8b53677248528f1ef49047
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193244"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="ucwa-events-in-lync-server-2013"></a>Eventos do UCWA no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-15_

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

O Lync Server 2013 usa a UCWA (Unified Communications Web API) para várias finalidades, desde o acesso ao Microsoft Exchange para pesquisas de contato até a atualização de presença para clientes móveis.

O UCWA gravará registros de comportamento operacional como tipos de eventos informativos, avisos e erros. A tabela a seguir descreve os eventos que podem ser gravados pelos componentes do UCWA.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>ID de evento</th>
<th>Tipo de Evento</th>
<th>Resumo</th>
<th>Causa e resolução</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>20001</p></td>
<td><p>Informativa</p></td>
<td><p>UCWA inicializado</p></td>
<td><p>Não disponível</p>
<p>Não disponível</p></td>
</tr>
<tr class="even">
<td><p>20002</p></td>
<td><p>Error</p></td>
<td><p>UCWA encontrou uma exceção inesperada durante a inicialização</p></td>
<td><p>Ocorreu um erro inesperado durante a inicialização</p>
<p>Examine os detalhes da exceção na entrada do log de eventos associada para determinar a possível causa</p></td>
</tr>
<tr class="odd">
<td><p>20003</p></td>
<td><p>Error</p></td>
<td><p>UCWA encontrou uma exceção não manipulada</p></td>
<td><p>Ocorreu uma exceção não manipulada</p>
<p>Reiniciar o servidor. Se o problema persistir, contate o suporte ao produto</p></td>
</tr>
<tr class="even">
<td><p>20004</p></td>
<td><p>Error</p></td>
<td><p>Não é possível acessar o Exchange para foto HD</p></td>
<td><p>A conexão com o Exchange não está disponível</p>
<p>Certifique-se de que a conexão com o Exchange esteja disponível</p></td>
</tr>
<tr class="odd">
<td><p>20005</p></td>
<td><p>Informativa</p></td>
<td><p>Recuperação de falha ao acessar o Exchange para foto HD</p></td>
<td><p>Não disponível</p></td>
</tr>
<tr class="even">
<td><p>20006</p></td>
<td><p>Error</p></td>
<td><p>Não é possível acessar o Exchange para pesquisa de contato</p></td>
<td><p>A conexão com o Exchange não está disponível</p>
<p>Certifique-se de que a conexão com o Exchange esteja disponível</p></td>
</tr>
<tr class="odd">
<td><p>20007</p></td>
<td><p>Informativa</p></td>
<td><p>Recuperado da falha ao pesquisar o contato no Exchange</p></td>
<td><p>Não disponível</p></td>
</tr>
<tr class="even">
<td><p>20008</p></td>
<td><p>Aviso</p></td>
<td><p>Tentativa de inscrever mais do que as assinaturas de presença permitidas por aplicativo</p></td>
<td><p>Tentativa de inscrever mais do que as assinaturas de presença permitidas por aplicativo</p>
<p>Verifique se há assinaturas desnecessárias nos clientes</p></td>
</tr>
<tr class="odd">
<td><p>20009</p></td>
<td><p>Aviso</p></td>
<td><p>Tentativa de inscrever mais do que as assinaturas de presença permitidas por lote</p></td>
<td><p>Tentativa de inscrever mais do que as assinaturas de presença permitidas por lote</p>
<p>Verifique se há assinaturas desnecessárias nos clientes</p></td>
</tr>
<tr class="even">
<td><p>20010</p></td>
<td><p>Error</p></td>
<td><p>Não é possível recuperar dados de inband</p></td>
<td><p>Não é possível recuperar dados de inband</p>
<p>Se o problema persistir, contate o suporte ao produto</p></td>
</tr>
<tr class="odd">
<td><p>20011</p></td>
<td><p>Error</p></td>
<td><p>Não é possível assinar a presença</p></td>
<td><p>Não é possível assinar a presença</p>
<p>Se o problema persistir, contate o suporte ao produto</p></td>
</tr>
<tr class="even">
<td><p>20012</p></td>
<td><p>Error</p></td>
<td><p>Falha ao registrar o ponto de extremidade</p></td>
<td><p>Falha ao registrar o ponto de extremidade</p>
<p>Se o problema persistir, contate o suporte ao produto</p></td>
</tr>
<tr class="odd">
<td><p>20013</p></td>
<td><p>Error</p></td>
<td><p>IM MCU não está disponível</p></td>
<td><p>IM MCU não está disponível</p>
<p>Veja se o IM MCU está em execução</p></td>
</tr>
<tr class="even">
<td><p>20014</p></td>
<td><p>Informativa</p></td>
<td><p>Recuperação de falha na conexão com a MCU de IM</p></td>
<td><p>Não disponível</p></td>
</tr>
<tr class="odd">
<td><p>20015</p></td>
<td><p>Error</p></td>
<td><p>AV MCU não está disponível</p></td>
<td><p>AV MCU não está disponível</p>
<p>Veja se o AV MCU está em execução</p></td>
</tr>
<tr class="even">
<td><p>20016</p></td>
<td><p>Informativa</p></td>
<td><p>Recuperação de falha na conexão com o AV MCU</p></td>
<td><p>Não disponível</p></td>
</tr>
<tr class="odd">
<td><p>20017</p></td>
<td><p>Error</p></td>
<td><p>À medida que a MCU não está disponível</p></td>
<td><p>À medida que a MCU não está disponível</p>
<p>Confira se a MCU está sendo executada</p></td>
</tr>
<tr class="even">
<td><p>20018</p></td>
<td><p>Informativa</p></td>
<td><p>Recuperação de falha na conexão com a MCU</p></td>
<td><p>Não disponível</p></td>
</tr>
<tr class="odd">
<td><p>20019</p></td>
<td><p>Error</p></td>
<td><p>Data MCU não está disponível</p></td>
<td><p>Data MCU não está disponível</p>
<p>Ver se os dados MCU estão sendo executados</p></td>
</tr>
<tr class="even">
<td><p>20020</p></td>
<td><p>Informativa</p></td>
<td><p>Recuperação de falha na conexão com o data MCU</p></td>
<td><p>Não disponível</p></td>
</tr>
<tr class="odd">
<td><p>20021</p></td>
<td><p>Error</p></td>
<td><p>Não é possível ingressar no IM MCU</p></td>
<td><p>Não é possível ingressar no IM MCU</p>
<p>Veja se o IM MCU está em execução</p></td>
</tr>
<tr class="even">
<td><p>20022</p></td>
<td><p>Error</p></td>
<td><p>Não é possível ingressar no AV MCU</p></td>
<td><p>Não é possível ingressar no AV MCU</p>
<p>Veja se o AV MCU está em execução</p></td>
</tr>
<tr class="odd">
<td><p>20023</p></td>
<td><p>Error</p></td>
<td><p>Não é possível entrar como MCU</p></td>
<td><p>Não é possível entrar como MCU</p>
<p>Confira se a MCU está sendo executada</p></td>
</tr>
<tr class="even">
<td><p>20024</p></td>
<td><p>Error</p></td>
<td><p>Não é possível participar dos dados MCU</p></td>
<td><p>Não é possível participar dos dados MCU</p>
<p>Ver se os dados MCU estão sendo executados</p></td>
</tr>
<tr class="odd">
<td><p>20025</p></td>
<td><p>Error</p></td>
<td><p>Não é possível acessar o Active Directory para a foto</p></td>
<td><p>A conexão com o Active Directory não está disponível</p>
<p>Certifique-se de que a conexão com o Active Directory está disponível</p></td>
</tr>
<tr class="even">
<td><p>20026</p></td>
<td><p>Informativa</p></td>
<td><p>Recuperação de falha ao acessar o Active Directory para foto</p></td>
<td><p>Não disponível</p></td>
</tr>
<tr class="odd">
<td><p>20027</p></td>
<td><p>Aviso</p></td>
<td><p>Não é possível desserializar</p></td>
<td><p>Não é possível desserializar</p>
<p>Se o problema persistir, contate o suporte ao produto</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

