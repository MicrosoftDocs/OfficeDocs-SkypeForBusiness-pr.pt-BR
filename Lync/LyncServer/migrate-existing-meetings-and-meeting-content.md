---
title: Migrar reuniões existentes e conteúdo de reunião
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate existing meetings and meeting content
ms:assetid: 30516731-2ae1-4a6d-a7e1-d3f05778c954
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688011(v=OCS.15)
ms:contentKeyID: 49733599
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e9ac7b7851cf5862210c7b343bc80b72b92c08e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527538"
---
# <a name="migrate-existing-meetings-and-meeting-content"></a>Migrar reuniões existentes e conteúdo de reunião

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-22_

Quando uma conta de usuário é movida do Lync Server 2010 para um servidor do Lync Server 2013, as seguintes informações são movidas com essa conta de usuário:

  - **As reuniões já foram programadas pelo usuário**. Isto inclui mover os diretórios de conferência e dados de conferência.

  - **Número de identificação pessoal (PIN) do usuário**. O PIN atual do usuário continua a funcionar até vencer ou o usuário solicitar um novo PIN.

A seguinte informação de conta do usuário não é movida para o novo servidor.

  - **Conteúdo da reunião**. Para poder mover o conteúdo compartilhado durante uma reunião, por exemplo, PowerPoint, Quadro de Avisos, anexos ou dados do pool, use o parâmetro **-MoveConferenceData** como parte do cmdlet **Move-CsUser**.

</div>

<span> </span>

</div>

</div>

</div>

