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
ms.openlocfilehash: e768cdd11d92b3aab5ce849f91cc1a422f119407
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741751"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-deployment-checklist-for-lync-server-2013"></a>Lista de verificação de implantação de controle de admissão de chamadas para o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-22_

Use a lista de verificação a seguir para verificar se você concluiu todas as tarefas de configuração necessárias para implantar o controle de admissão de chamadas (CAC).

  - Se um ou mais servidores Edge estiverem implantados, cada endereço IP de interface externa precisará ser adicionado à lista de sub-rede nas configurações de configuração de rede, com uma máscara de bits de 32. Associe também essa sub-rede (endereço IP) ao ID do site da rede para o local geográfico onde o serviço de Borda A/V está implantado.
    
    <div>
    

    > [!NOTE]  
    > Os servidores de borda não precisam implementar o CAC.

    
    </div>

  - Verifique se o CAC está habilitado, seja por meio do painel de controle do Lync Server ou executando o cmdlet conforme especificado em [habilitar o controle de admissão de chamadas no Lync Server 2013](lync-server-2013-enable-call-admission-control.md).

  - Certifique-se de que o CAC está habilitado em todos os sites centrais. Isso pode ser feito por meio do construtor de topologias. Se um aviso for gerado durante a publicação, *não* ignore-o.

  - Certifique-se de que todas as subredes gerenciadas na rede corporativa estão definidas nas configurações de rede. Também é essencial que cada sub-rede seja associada a um site de rede, conforme explicado em [associar uma sub-rede a um site de rede no Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).

  - Certifique-se de que a subrede ou os endereços IP de todos os Servidores Front-End, Aparelhos de Filial Persistentes (SBAs), Servidores de Conferência de Áudio/Vídeo (se estiverem em um pool separado) e Servidores de Mediação estejam definidos nas configurações de rede.

</div>

<span> </span>

</div>

</div>

</div>

