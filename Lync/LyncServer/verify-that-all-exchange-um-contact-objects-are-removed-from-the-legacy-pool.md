---
title: Verificar se todos os objetos de contato do UM do Exchange foram removidos do pool herdado
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify that all Exchange UM Contact objects are removed from the legacy pool
ms:assetid: 5a813169-0ed7-4f84-a242-ed2cd4ea5c43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688068(v=OCS.15)
ms:contentKeyID: 49733664
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7815f78dfa5f2b4aab3f09102a9948498c20cf10
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188844"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-that-all-exchange-um-contact-objects-are-removed-from-the-legacy-pool"></a>Verificar se todos os objetos de contato do UM do Exchange foram removidos do pool herdado

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-26_

Use a ferramenta **OCSUmUtil** ou o cmdlet **Get-CsExumContact** para verificar se os objetos de contato do um do Exchange foram removidos do pool herdado do Office Communications Server 2007 R2. **OCSUmUtil** está localizado na seguinte pasta:

% Arquivos de programa\\% arquivos\\comuns do Lync\\Server\\2013 suportam ocsumutil. exe

**OCSUmUtil** precisa ser executado a partir de uma conta de usuário que tenha:

  - Associação ao grupo RTCUniversalServerAdmins e RTCUniversalUserAdmins (que inclui direitos para ler as configurações da Unificação de Mensagens do Exchange Server).

  - Direitos no domínio para criar objetos de contato no contêiner de unidade organizacional (UO) especificado

Para obter detalhes sobre como usar o cmdlet **Get-CsExumContact** , consulte [Get-CsExumContact](https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact) na documentação do Shell de gerenciamento do Lync Server.

</div>

<span> </span>

</div>

</div>

</div>

