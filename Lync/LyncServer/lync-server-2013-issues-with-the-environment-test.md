---
title: 'Lync Server 2013: problemas com o teste de ambiente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Issues with the environment test
ms:assetid: ff1fe0d3-35b2-41ef-87e7-6a61e9e1d2ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205421(v=OCS.15)
ms:contentKeyID: 48185970
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 65803ff396a9615787291de2d728fe63f3350d0b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765339"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="issues-with-the-environment-test-in-lync-server-2013"></a>Problemas com o teste de ambiente no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-21_

O analisador de práticas recomendadas fornece uma maneira de verificar se o ambiente do Lync Server 2013 é uma configuração compatível. Como parte da verificação dos serviços de domínio Active Directory, o analisador de práticas recomendadas faz o seguinte:

  - Verifica a floresta dos serviços de domínio Active Directory e a preparação do esquema.

  - Identifica o número de domínios e sites de serviços de domínio Active Directory na implantação.

  - Verifica os níveis da floresta e do domínio.

  - Verifica a versão do controlador de domínio.

  - Identifica o contexto de domínio, configuração e nomenclatura de esquema.

  - Identifica o número de usuários habilitados.

  - Verifica onde as configurações globais dos serviços de domínio Active Directory estão armazenadas.

  - Verifica os pontos de conexão de serviço (SCPs) do Lync Server.

  - Identifica a versão do banco de dados.

<div>

## <a name="resolving-issues-with-the-environment"></a>Solucionando problemas com o ambiente

Se o teste de ambiente encontrou problemas em seu ambiente, esses problemas provavelmente são causados por problemas com a configuração do Active Directory ou com o nível de software em execução em servidores específicos. Por exemplo, se o analisador de práticas recomendadas identificar os controladores de domínio em seu ambiente que executam o Windows Server 2000, ele emitirá um aviso e você precisará atualizar esses controladores de domínio para uma versão com suporte do Windows Server.

</div>

</div>

<span> </span>

</div>

</div>

</div>

