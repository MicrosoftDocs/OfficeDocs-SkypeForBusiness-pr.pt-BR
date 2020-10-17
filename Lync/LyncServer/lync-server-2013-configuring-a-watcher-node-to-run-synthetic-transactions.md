---
title: 'Lync Server 2013: Configurando um nó do inspetor para executar transações sintéticas'
description: 'Lync Server 2013: Configurando um nó do inspetor para executar transações sintéticas.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a watcher node to run synthetic transactions
ms:assetid: cedda508-8881-4079-88d5-49798f342ddf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205314(v=OCS.15)
ms:contentKeyID: 48185578
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bd5fdb3d1a1499a6ef79e962a41d9eb3ee174c33
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567877"
---
# <a name="configuring-a-watcher-node-to-run-synthetic-transactions-in-lync-server-2013"></a>Configurando um nó do inspetor para executar transações sintéticas no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-02-07_

Após os arquivos do agente do Centro do Sistema terem sido instalados, você deve configurar o nó do observador sozinho. As etapas realizadas para configurar um nó do observador irá variar dependendo se seu computador do nó do observador está dentro da sua rede de perímetro ou fora.

Ao configurar um nó do observador, você também deve escolher o tipo de método de autenticação a ser implantado neste nó. O Lync Server 2013 permite que você escolha um dos dois métodos de autenticação: servidor confiável ou autenticação de credencial. As diferenças entre estes dois métodos são destacadas na tabela a seguir:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Configuração</th>
<th>Descrição</th>
<th>Locais suportados</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Servidor confiável</p></td>
<td><p>Usa uma certificação para personificar um servidor interno e desafios de autenticação de bypass.</p>
<p>Isto é útil para os administradores que preferem gerenciar um único certificado ao invés de várias senhas do usuário no nó do observador.</p></td>
<td><p>Dentro da empresa.</p>
<p>Observe que, com este método, o nó do observador deve estar no mesmo domínio que os pools sendo monitorados. Se o nó do observador e os pools monitorados estão em domínios diferentes, use a Autenticação de Credencial.</p></td>
</tr>
<tr class="even">
<td><p>Autenticação de Credencial</p></td>
<td><p>Armazena os nomes de usuário e senhas com segurança no Gerenciador de Credencial do Windows no nó do observador.</p>
<p>Este modo exige mais gerenciamento de senha, mas é a única opção para nós do observador fora da empresa. Estes nós do observador não podem ser tratados como um ponto de extremidade confiável para autenticação.</p></td>
<td><p>Fora da empresa.</p>
<p>Dentro da empresa.</p></td>
</tr>
</tbody>
</table>


Você também deve verificar se o firewall tem regras de entrada para MonitoringHost.exe e PowerShell.exe. Se esses processos forem bloqueados pelo firewall, suas transações sintéticas falharão com o erro 504 (tempo limite do servidor).

</div>

<span> </span>

</div>

</div>

</div>

