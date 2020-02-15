---
title: 'Lync Server 2013: visão geral dos cenários de criação de fluxo de trabalho'
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
ms.openlocfilehash: 27383db13176150078bf4855dee4df57cb1615af
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "41989876"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-workflow-creation-scenarios-in-lync-server-2013"></a>Visão geral dos cenários de criação de fluxo de trabalho no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-17_

Ao criar um fluxo de trabalho, há duas possibilidades de cenário:

  - **O Administrasdor cria e configura o fluxo de trabalho** — O membro de função CsResponseGroupAdministrator (ou equivalente) cria e ativa o fluxo de trabalho e todos os elementos no fluxo de trabalho, tais como os grupos de agente, filas, férias e horário comercial, música de espera, etc.

  - **O Administrador cria o fluxo de trabalho e oGerente configura as opções** — O membro de função CsResponseGroupAdministrator (ou equivalente) define o SIP URI primário, Nome de exibição, designa um mebro ou membros da função CsResponseGroupManager e seleciona uma fila e ativa o fluxo de trabalho. O CsResponseGroupManager pode então fazer o log e editar a configuração do fluxo de trabalho criando grupos de agente e também designando o grupo à fila, configurando o número de telefone, férias e horário comercial, música de espera, etc.
    
    <div>
    

    > [!NOTE]  
    > Quando quiser criar um fluxo de trabalho gerenciado, é necessário criar o fluxo como ativo. Após salvar um fluxo gerenciado e ativo, é possível modificar e desativar o fluxo de trabalho.

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

