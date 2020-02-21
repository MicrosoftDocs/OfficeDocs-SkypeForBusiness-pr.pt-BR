---
title: 'Lync Server 2013: (opcional) verificar a implantação do estacionamento de chamada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Verify Call Park deployment
ms:assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413076(v=OCS.15)
ms:contentKeyID: 48185952
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1526c05245ea35f794664d8d64f90b60022b2be2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216477"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="optional-verify-call-park-deployment-in-lync-server-2013"></a>Opcion Verificar a implantação do estacionamento de chamada no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-11_

Após instalar e configurar o estacionamento de chamadas, você precisa verificar a configuração para garantir que o estacionamento e a recuperação de chamadas funcione conforme o esperado. No mínimo, verifique o seguinte:

  - Ligue para um usuário que tem o estacionamento de chamadas habilitado e faça com que o usuário disquem a chamada.
    
    <div>
    

    > [!NOTE]  
    > Se você habilitou o estacionamento de chamada na política de voz antes de executar esse teste, o usuário que estiver estacionando a chamada precisa sair do Lync Server e entrar novamente para poder ver a opção de estacionamento de chamada na lista de chamadas de transferência.

    
    </div>

  - Disque o número de órbita para recuperar a chamada.

  - Estacione outra chamada, permita que o tempo da chamada estacionada esgote e não pegue o retorno de chamada. Verifique se a chamada que atingiu o tempo limite será corretamente roteada para o destino de fallback especificado para **OnTimeoutURI **.

</div>

<span> </span>

</div>

</div>

</div>

