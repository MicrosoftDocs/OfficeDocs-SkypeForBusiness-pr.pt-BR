---
title: 'Lync Server 2013: lista de verificação de implantação de controle de admissão de chamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control deployment checklist
ms:assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398928(v=OCS.15)
ms:contentKeyID: 48185525
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e16c4c77876064ca0ab9210b96d7c13d68cc4218
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48537238"
---
# <a name="call-admission-control-deployment-checklist-for-lync-server-2013"></a>Lista de verificação de implantação do controle de admissão de chamadas para Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-22_

Consulte a lista de verificação para confirmar se você concluiu todas as tarefas de configuração necessárias para a implantação do controle de admissão de chamadas.

  - Se um ou mais Servidores de Borda for implantado, cada endereço IP de interface externa precisa ser adicionado à lista de subredes nas configurações de rede, com uma bitmask de 32. Associe também essa sub-rede (endereço IP) ao ID do site de rede para o local geográfico onde o serviço Borda A/V está implantado.
    
    <div>
    

    > [!NOTE]  
    > Os Servidores de Borda não são necessários para implementar o CAC.

    
    </div>

  - Certifique-se de que o CAC está habilitado, seja por meio do painel de controle do Lync Server ou executando o cmdlet conforme especificado em [habilitar controle de admissão de chamadas no Lync Server 2013](lync-server-2013-enable-call-admission-control.md).

  - Certifique-se de que o CAC está habilitado em todos os sites centrais. Isso pode ser feito por meio do construtor de topologias. Se um aviso é gerado ao publicar, *não* ignore-o.

  - Certifique-se de que todas as subredes gerenciadas na rede empresarial estão definidas nas configurações de rede. Também é essencial que todas as sub-redes estejam associadas a um site de rede, conforme explicado em [associar uma sub-rede a um site de rede no Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).

  - Certifique-se de que a subrede ou os endereços IP de todos os Servidores de Front-End, Aparelhos de Filial Persistentes (SBAs), Servidores de Conferência de Áudio/Vídeo (se estiverem em um pool separado) e Servidores de Mediação estejam definidos nas configurações de rede.

</div>

<span> </span>

</div>

</div>

</div>

