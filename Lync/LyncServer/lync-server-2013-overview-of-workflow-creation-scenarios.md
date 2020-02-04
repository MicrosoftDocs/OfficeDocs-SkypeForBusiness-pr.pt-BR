---
title: 'Lync Server 2013: Visão geral dos cenários de criação do fluxo de trabalho'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of workflow creation scenarios
ms:assetid: 05e0c175-0f1a-4bb1-b048-c68584d00649
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204646(v=OCS.15)
ms:contentKeyID: 48183309
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 08ecb210ea937184039587d289c5c9c57cb4fa4d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755405"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-workflow-creation-scenarios-in-lync-server-2013"></a>Visão geral dos cenários de criação do fluxo de trabalho no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-17_

Ao criar um fluxo de trabalho, há duas possibilidades de cenário:

  - **O Administrador cria e configura o fluxo de trabalho** — O membro da função CsResponseGroupAdministrator (ou equivalente) cria e ativa o fluxo de trabalho e todos os elementos no fluxo de trabalho, tais como os grupos de agente, filas, férias e horário comercial, música de espera, etc.

  - **O Administrador cria o fluxo de trabalho e o Gerente configura as opções** — O membro da função CsResponseGroupAdministrator (ou equivalente) define o o URI do SIP principal, Nome de exibição, atribui um membro ou membros da função CsResponseGroupManager e seleciona uma fila e ativa o fluxo de trabalho. O CsResponseGroupManager pode então fazer logon e editar a configuração do fluxo de trabalho criando grupos de agente e também atribui o grupo à fila, configurando o número de telefone, férias e horário comercial, música de espera, etc.
    
    <div>
    

    > [!NOTE]  
    > Quando quiser criar um fluxo de trabalho gerenciado, é necessário criar o fluxo como ativo. Após salvar um fluxo gerenciado e ativo, é possível modificar e desativar o fluxo de trabalho.

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

