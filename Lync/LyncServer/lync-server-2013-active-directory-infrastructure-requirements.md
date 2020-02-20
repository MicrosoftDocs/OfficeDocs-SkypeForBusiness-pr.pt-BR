---
title: 'Lync Server 2013: requisitos de infraestrutura do Active Directory'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory infrastructure requirements
ms:assetid: c2086f7b-662f-4179-ab99-2c0311ebd903
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412955(v=OCS.15)
ms:contentKeyID: 48185318
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de375bd11a0cf515745b0a64fb4aef7aa32113d9
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145059"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="active-directory-infrastructure-requirements-for-lync-server-2013"></a>Requisitos de infraestrutura do Active Directory para o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-11-07_

Antes de iniciar o processo de preparação dos serviços de domínio do Active Directory para o Lync Server 2013, verifique se a sua infraestrutura do Active Directory atende aos seguintes pré-requisitos:

  - Todos os controladores de domínio (que incluem todos os servidores de catálogo global) na floresta onde você implanta o Lync Server executam um dos seguintes sistemas operacionais:
    
      - Sistema operacional Windows Server 2012 R2
    
      - Sistema operacional Windows Server 2012
    
      - Windows Server 2008 R2 operating system
    
      - Sistema operacional Windows Server 2008
    
      - Windows Server 2008 Enterprise de 32 bits
    
      - versões de 32 bits ou 64 bits do sistema operacional Windows Server 2003 R2
    
      - versões de 32 bits ou 64 bits do sistema operacional Windows Server 2003

  - Todos os domínios nos quais você implanta o Lync Server são gerados para um nível funcional de domínio do Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 ou pelo menos Windows Server 2003.

  - A floresta na qual você implanta o Lync Server é elevada para um nível funcional de floresta do Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 ou pelo menos Windows Server 2003.
    
    <div>
    

    > [!NOTE]  
    > Para alterar o nível funcional da floresta ou domínio, consulte "elevando os níveis funcionais do domínio e da floresta" <A href="https://go.microsoft.com/fwlink/p/?linkid=263775">https://go.microsoft.com/fwlink/p/?LinkId=263775</A>na biblioteca do TechNet em.

    
    </div>

  - Um catálogo global é implantado em todos os domínios onde você implanta computadores ou usuários do Lync Server.

O Lync Server 2013 oferece suporte aos grupos universais nos sistemas operacionais Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 e Windows Server 2003. Os membros de grupos universais podem incluir outros grupos e contas de qualquer domínio na árvore ou floresta de domínios e podem receber permissões em qualquer domínio na árvore ou floresta de domínios. O suporte a grupos universais, combinado com a delegação de administrador, simplifica o gerenciamento de uma implantação do Lync Server. Por exemplo, não é necessário adicionar um domínio para outro para permitir que um administrador gerencie os dois.

</div>

<span> </span>

</div>

</div>

</div>

