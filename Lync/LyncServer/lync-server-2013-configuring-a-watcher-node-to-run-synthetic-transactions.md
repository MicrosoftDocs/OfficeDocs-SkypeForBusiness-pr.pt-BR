---
title: 'Lync Server 2013: Configurando um nó de inspetor para executar transações sintéticas'
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
ms.openlocfilehash: 19211c786c288326d5769824524f5571e5df2f00
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763415"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-to-run-synthetic-transactions-in-lync-server-2013"></a>Configurando um nó de inspetor para executar transações sintéticas no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-02-07_

Após a instalação dos arquivos do agente do System Center, você deve configurar o próprio nó do Inspetor. As etapas que você seguir para configurar um nó de Inspetor variam de acordo com o fato de o computador do nó do Inspetor estar dentro da sua rede de perímetro ou de fora da sua rede de perímetro.

Ao configurar um nó do observador, você também deve escolher o tipo de método de autenticação a ser implantado neste nó. O Lync Server 2013 permite que você escolha um dos dois métodos de autenticação: servidor confiável ou autenticação de credenciais. As diferenças entre esses dois métodos são descritas na tabela a seguir:


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
<th>Locais com suporte</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Servidor confiável</p></td>
<td><p>Usa uma certificação para personificar um servidor interno e desafios de autenticação de bypass.</p>
<p>Isso é útil para administradores que preferem gerenciar um único certificado em vez de muitas senhas de usuário em cada nó de Inspetor.</p></td>
<td><p>Dentro da empresa.</p>
<p>Observe que, com esse método, o nó do Inspetor deve estar no mesmo domínio que os pools sendo monitorados. Se o nó do Inspetor e os pools monitorados estiverem em domínios diferentes, use a autenticação de credenciais em vez disso.</p></td>
</tr>
<tr class="even">
<td><p>Autenticação de credenciais</p></td>
<td><p>Armazena os nomes de usuário e senhas com segurança no Gerenciador de Credencial do Windows no nó do observador.</p>
<p>Esse modo requer mais gerenciamento de senha, mas é a única opção para nós de Inspetor localizados fora da empresa. Estes nós do observador não podem ser tratados como um ponto de extremidade confiável para autenticação.</p></td>
<td><p>Fora da empresa.</p>
<p>Dentro da empresa.</p></td>
</tr>
</tbody>
</table>


Você também deve verificar se o seu firewall tem regras de entrada para MonitoringHost. exe e PowerShell. exe. Se esses processos estiverem bloqueados pelo firewall, suas transações sintéticas falharão com um erro 504 (tempo limite do servidor).

</div>

<span> </span>

</div>

</div>

</div>

