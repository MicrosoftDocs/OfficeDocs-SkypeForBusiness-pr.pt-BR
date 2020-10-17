---
title: Implantando um aparelho de filial persistente ou servidor-tarefas do site central
description: Implantando um aparelho de filial persistente ou tarefas do site central.
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
ms.openlocfilehash: 4460ea215d6fc80ee89f1ca9bc42f08ac5d14617
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558597"
---
# <a name="deploying-a-survivable-branch-appliance-or-server-with-lync-server-2013---central-site-tasks"></a>Implantando um servidor ou aparelho de filial persistente com o Lync Server 2013-tarefas do site central

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-18_

Conclua as tarefas seguintes no local central. Se você estiver implantando um servidor de filial persistente, pule a primeira tarefa.

<div>


> [!IMPORTANT]
> Antes de realizar as tarefas desta seção, as condições a seguir devem estar em vigor: 
> <UL>
> <LI>
> <P>O Lync Server deve ser configurado no site central.</P>
> <LI>
> <P>Um técnico de instalação do site de filial deve ser adicionado ao grupo  RTCUniversalSBATechnicians.</P></LI></UL>Além disso, recomendamos que você faça o seguinte:
> <UL>
> <LI>
> <P>Implantar um servidor DHCP no site de filial para permitir que os cliente obtenham os endereços IP.</P>
> <LI>
> <P>Como alternativa à implantação de um servidor DHCP em cada site de filial, habilite o DHCP do Lync Server no aparelho de filial persistente ou servidor de filial persistente usando o cmdlet do Shell de gerenciamento do Lync Server <STRONG>set-CsRegistrarConfiguration – EnableDHCPServer $true</STRONG>. Para obter detalhes, consulte a seção "requisitos de hardware e software" dos <A href="lync-server-2013-branch-site-resiliency-requirements.md">requisitos de resiliência de site de filial para o Lync Server 2013</A> na documentação de planejamento.</P></LI></UL>



</div>

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Adicionar um aparelho de filial persistente ao Active Directory no Lync Server 2013](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md)

  - [Adicionar sites de filial à sua topologia no Lync Server 2013](lync-server-2013-add-branch-sites-to-your-topology.md)

  - [Definir um servidor ou aparelho de filial persistente no Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

