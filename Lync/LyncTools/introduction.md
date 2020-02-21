---
title: Apresentação
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Introduction
ms:assetid: 276395be-93df-4a16-97e2-cb468cd0f2e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945588(v=OCS.15)
ms:contentKeyID: 51541414
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 912c6a1704438106a3ffbb178d9f03a536489757
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204557"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="introduction"></a>Introdução

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-24_

A ferramenta de desempenho e stress do Lync Server 2013 (chamada de LyncPerfTool) pode simular a carga de usuário dos seguintes tipos:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Mensagens instantâneas (IM) e presença</p></td>
<td><p>Audioconferência</p></td>
</tr>
<tr class="even">
<td><p>Compartilhamento de aplicativos</p></td>
<td><p>Voz sobre IP (VoIP), incluindo simulação de rede telefônica pública comutada (PSTN)</p></td>
</tr>
<tr class="odd">
<td><p>Conferência de cliente de acesso Web</p></td>
<td><p>Microsoft Lync 2013 Attendant</p></td>
</tr>
<tr class="even">
<td><p>Grupos de resposta</p></td>
<td><p>Expansão de lista de distribuição</p></td>
</tr>
<tr class="odd">
<td><p>Consulta catálogo de endereços e catálogo de endereços</p></td>
<td><p>Enhanced 9-1-1 (E9-1-1) chamadas e perfil de local (plano de discagem)</p></td>
</tr>
<tr class="even">
<td><p>Múltipla</p></td>
<td><p>Exibir vários fluxos de uma conferência</p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
</tr>
</tbody>
</table>


A ferramenta de desempenho e stress do Lync Server 2013 oferece suporte à geração e à Federação de carga entre pools por meio de uma configuração avançada apenas.

A ferramenta também não simula a carga do usuário para os seguintes clientes:

  - Office Live Meeting 2007

  - Chat persistente do Lync 2013

Como resultado, a ferramenta de estresse e desempenho do Lync Server 2013 não dará suporte ao teste dos seguintes componentes:

  - Chat persistente do Lync 2013

  - Cenários de integração do Exchange

<div>

## <a name="applications-and-files-included-with-the-lync-server-2013-stress-and-performance-tool"></a>Aplicativos e arquivos incluídos na ferramenta de estresse e desempenho do Lync Server 2013

Os seguintes aplicativos estão incluídos na ferramenta de estresse e desempenho do Lync Server 2013:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Ferramenta</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>UserProvisioningTool. exe</p></td>
<td><p>A ferramenta de provisionamento de usuário do Lync Server 2013. Essa ferramenta é usada para criar usuários e contatos.</p></td>
</tr>
<tr class="even">
<td><p>UserProfileGenerator. exe</p></td>
<td><p>A ferramenta de configuração de carregamento do Lync Server 2013. Essa ferramenta é usada para configurar as características da carga de usuário para simular.</p></td>
</tr>
<tr class="odd">
<td><p>LyncPerfTool. exe</p></td>
<td><p>A ferramenta de desempenho e stress do Lync Server 2013. LyncPerfTool é a ferramenta que simula a carga do usuário.</p></td>
</tr>
<tr class="even">
<td><p>Default. TMX</p></td>
<td><p>O default. TMX é necessário para usar a ferramenta de registro em log do Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p>Exemplo de scripts de provisionamento</p></td>
<td><p>Estes exemplos são usados para configurar a topologia para executar testes de carga, com base em cenários específicos</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

