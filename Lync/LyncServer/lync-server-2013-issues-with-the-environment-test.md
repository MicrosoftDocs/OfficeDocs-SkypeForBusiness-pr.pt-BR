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
ms.openlocfilehash: c96bae1a917efa52dfc25639d7e46fc1b7e2142e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186754"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="issues-with-the-environment-test-in-lync-server-2013"></a>Problemas com o teste de ambiente no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-21_

O Best Practices Analyzer oferece uma maneira de verificar se o seu ambiente do Lync Server 2013 é uma configuração suportada. Como parte da verificação de Serviços de Domínio do Active Directory, o analisador de práticas recomendadas realiza as seguintes tarefas:

  - Verifica os Serviços de Domínio Active Directory em preparo de esquema e floresta.

  - Identifica o número dos sites e domínios dos Serviços de Domínio Active Directory na implantação.

  - Verifica os níveis de floresta e domínio.

  - Verifica a versãod o controlador de domínio.

  - Identifica o domínio, a configuração e contexto de nomenclatura de esquema.

  - Identifica o número de usuários habilitados.

  - Verifica onde as definições globais dos Serviços de Domínio Active Directory estão armazenadas.

  - Verifica os pontos de conexão de serviço (SCPs) para o Lync Server.

  - Identifica a versão do banco de dados.

<div>

## <a name="resolving-issues-with-the-environment"></a>Resolve problemas com  oambiente

Se o teste de ambiente encontrou problemas com seu ambiente, esses problemas são provavelmente causados por problemas com sua configuração do Active Directory ou o nível do software executando em servidores específicos. Por exemplo, se o analisador de práticas recomendadas identificar quaisquer controladores de domínio em seu ambiente executando Windows Server 2000, ele emitirá o aviso e você deverá atualizar os controladores de domínio para uma versão suportada do Windows Server.

</div>

</div>

<span> </span>

</div>

</div>

</div>

