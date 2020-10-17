---
title: 'Lync Server 2013: relatório de diagnóstico'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Diagnostic Report
ms:assetid: b389dbd9-f2e8-4184-93d0-2e504796ac16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615445(v=OCS.15)
ms:contentKeyID: 48185159
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a6eb6de7f2ba23d52a7b508869dbb25c9c5e3802
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514488"
---
# <a name="diagnostic-report-in-lync-server-2013"></a>Relatório de diagnóstico no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-02-07_

O Relatório de diagnóstico fornece diagnósticos e informações para a solução de problemas de uma sessão com falha. Essas informações incluem a ID de diagnóstico e o cabeçalho de Diagnóstico que foram importados quando a sessão falhou. A ID de diagnóstico é um identificador exclusivo (na forma de um cabeçalho ms-diagnostics) que é anexado a uma mensagem SIP, enquanto a cabeçalho de Diagnóstico fornece uma descrição da ID de diagnóstico. O relatório também pode conter detalhes importantes para a solução de problemas e que são conhecidos pelo componente de relatório. Por exemplo:

  - O código de motivo fornecido pelo gateway da PSTN que gerou a falha. Quando uma chamada de saída falha na rede PSTN, um código de causa ISUP (parte de usuário ISDN, em inglês) é gerado automaticamente. Por exemplo, um gateway PSTN pode enviar o código de causa 34 para indicar que nenhum circuito ou canal estava disponível para completar a chamada.

  - FQDN do par, porta e erros de Winsock para falhas de conectividade.

  - Nomes pesquisados por falhas de resolução de DNS. A resolução DNS ocorre sempre que um cliente entra em contato com um servidor de nomes e solicita o endereço IP que corresponde ao nome de dispositivo especificado.

<div>

## <a name="accessing-the-diagnostic-report"></a>Acessando o relatório de diagnósticos

O relatório de diagnóstico pode ser acessado clicando na métrica relatório de diagnóstico (detalhe) no [relatório de detalhes de sessão ponto a ponto no Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) ou no relatório de detalhes da conferência.

</div>

<div>

## <a name="filters"></a>Filtros

Nenhum. Não é possível filtrar o Relatório de Diagnóstico.

</div>

<div>

## <a name="metrics"></a>Métrica

A tabela a seguir lista as informações fornecidas no Relatório de Diagnóstico para cada sessão.

### <a name="diagnostic-report-metrics"></a>Métricas do Relatório de Diagnóstico

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome</th>
<th>É possível classificar este item?</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Hora do relatório</strong></p></td>
<td><p>Não</p></td>
<td><p>Data e hora do registro do relatório.</p></td>
</tr>
<tr class="even">
<td><p><strong>Código da resposta</strong></p></td>
<td><p>Não</p></td>
<td><p>Código da resposta SIP enviado quando a sessão falhou.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tipo de solicitação</strong></p></td>
<td><p>Não</p></td>
<td><p>Tipo de solicitação SIP que falhou. Por exemplo, CONVIDAR, ATÉ LOGO ou SERVIÇO.</p></td>
</tr>
<tr class="even">
<td><p><strong>Fonte</strong></p></td>
<td><p>Não</p></td>
<td><p>Origem do erro.</p></td>
</tr>
<tr class="odd">
<td><p><strong>URI do usuário de origem</strong></p></td>
<td><p>Não</p></td>
<td><p>Endereço SIP do usuário que iniciou a sessão.</p></td>
</tr>
<tr class="even">
<td><p><strong>Representante do usuário de origem</strong></p></td>
<td><p>Não</p></td>
<td><p>Software usado pelo ponto de extremidade do usuário que iniciou a sessão.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ID do Diagnóstico</strong></p></td>
<td><p>Não</p></td>
<td><p>Identificador exclusivo (no formato de um cabeçalho ms-diagnostics) anexado a uma mensagem SIP que frequentemente oferece informações úteis para resolução de erros.</p></td>
</tr>
<tr class="even">
<td><p><strong>Tipo de conteúdo</strong></p></td>
<td><p>Não</p></td>
<td><p>Tipo de conteúdo de mídia que falhou. Por exemplo, um tipo de conteúdo comum é Application/sdp. SDP (Protocolo de descrição de sessão) é um protocolo padrão de Internet usado para anúncios de sessão, convites de sessão e outras formas de início de sessão multimídia.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Aplicação</strong></p></td>
<td><p>Não</p></td>
<td><p>Aplicativo envolvido no erro.</p></td>
</tr>
<tr class="even">
<td><p><strong>URI do usuário de destino</strong></p></td>
<td><p>Não</p></td>
<td><p>Endereço SIP do usuário convidado para a sessão.</p></td>
</tr>
<tr class="odd">
<td><p>Hora de ingresso de conferência (ms)</p></td>
<td><p>Não</p></td>
<td><p>Tempo (em milissegundos) que o usuário precisou para ingressar na conferência.</p></td>
</tr>
<tr class="even">
<td><p><strong>Cabeçalho do diagnóstico</strong></p></td>
<td><p>Não</p></td>
<td><p>Descrição do ID de diagnóstico.</p></td>
</tr>
</tbody>
</table>


Uma lista de erros de diagnóstico pode ser encontrada na [página de cabeçalho MS-Diagnostics](https://msdn.microsoft.com/library/gg132446\(v=office.12\).aspx).

</div>

</div>

<span> </span>

</div>

</div>

</div>

