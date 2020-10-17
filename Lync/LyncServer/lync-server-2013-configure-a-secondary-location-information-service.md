---
title: 'Lync Server 2013: configurar um serviço de informações de local secundário'
description: 'Lync Server 2013: configurar um serviço de informações de local secundário.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a secondary Location Information service
ms:assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398138(v=OCS.15)
ms:contentKeyID: 48183334
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1721299a0c70535dff8dd05e31712ee6a8d93691
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551704"
---
# <a name="configure-a-secondary-location-information-service-in-lync-server-2013"></a>Configurar um serviço de informações de local secundário no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-30_

O Lync Server 2013 fornece uma interface de serviço Web que você pode usar para apontar o serviço de informações de local para um banco de dados de endereço de origem de local secundário (SLS). A interface de serviço Web que se conecta ao banco de dados de SLS deve estar de acordo com o serviço de informações de local WSDL. Se um banco de dados de local e um banco de dados de local secundário estiverem configurados, o serviço de informações de local consulta primeiro o banco de dados de local e, se nenhuma correspondência for encontrada, envia a solicitação de local do cliente para o banco de dados SLS. Se o local existir no SLS, o serviço de informações de local enviará o local de volta para o cliente.

Para obter detalhes, consulte a documentação do Shell de gerenciamento do Lync Server para o seguinte cmdlet:

  - **Set-CsWebServiceConfiguration**

<div>

## <a name="to-configure-secondary-location-database"></a>Para configurar o banco de dados de localização secundária

1.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

2.  Execute o cmdlet a seguir para configurar o URL para a localização do banco de dados de localização secundária.
    
        Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 

</div>

</div>

<span> </span>

</div>

</div>

</div>

