---
title: Implantando um servidor ou aparelho de filial persistente - Tarefas do site central
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying a Survivable Branch Appliance or Server - central site tasks
ms:assetid: 0f631a36-fc2e-41cd-8a0d-f27e84f4a89e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398189(v=OCS.15)
ms:contentKeyID: 48183422
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a9aa6d38ec873652feae6ef6a374ee5b771520b1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729621"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-a-survivable-branch-appliance-or-server-with-lync-server-2013---central-site-tasks"></a>Implantando um servidor ou aparelho de filial persistente com o Lync Server 2013 - Tarefas do site central

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-18_

Conclua as tarefas nesta seção no site central. Se você estiver implantando um servidor de ramificação sobreviventes, pule a primeira tarefa.

<div>


> [!IMPORTANT]
> Antes de executar as tarefas nesta seção, as seguintes condições devem estar em vigor: 
> <UL>
> <LI>
> <P>O Lync Server deve ser configurado no site central.</P>
> <LI>
> <P>Um técnico de instalação no site de filial deve ser adicionado ao grupo RTCUniversalSBATechnicians.</P></LI></UL>Além disso, recomendamos que você faça o seguinte:
> <UL>
> <LI>
> <P>Implante um servidor DHCP em cada site de ramificação para permitir que os clientes obtenham endereços IP.</P>
> <LI>
> <P>Como uma alternativa para implantar um servidor DHCP em cada site de ramificação, habilite o DHCP do Lync Server no aparelho de ramificação ou servidor de ramificação sobreviventes usando o cmdlet Set-CsRegistrarConfiguration-do Shell de gerenciamento do Lync Server <STRONG>-EnableDHCPServer $true</STRONG>. Para obter detalhes, consulte a seção "requisitos de hardware e software" dos <A href="lync-server-2013-branch-site-resiliency-requirements.md">requisitos de resiliência de site para o Lync Server 2013</A> na documentação de planejamento.</P></LI></UL>



</div>

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Adicionar um Aplicativo de Filial Persistente ao Active Directory no Lync Server 2013](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md)

  - [Adicionar sites de filial a sua topologia no Lync Server 2013](lync-server-2013-add-branch-sites-to-your-topology.md)

  - [Definir um Servidor ou Aparelho de Filial Persistente no Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

