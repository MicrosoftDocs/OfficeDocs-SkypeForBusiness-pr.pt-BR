---
title: 'Lync Server 2013: publicar o banco de dados de localização'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish the location database
ms:assetid: dd032b5b-df0e-4017-ac46-e17570c1ab1e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398974(v=OCS.15)
ms:contentKeyID: 48185598
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 481a8406eeeec6fce25c19336519c4a9bf19da82
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512368"
---
# <a name="publish-the-location-database-from-lync-server-2013"></a>Publicar o banco de dados de localização do Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-30_

Os novos locais adicionados ao banco de dados de local não serão disponibilizados para o cliente até que sejam publicados.

Para obter detalhes, consulte a documentação do Shell de gerenciamento do Lync Server para o seguinte cmdlet:

  - **Publish-CsLisConfiguration**

Se você usar gateways do número de identificação de local de emergência (ELIN), também precisará carregar o ELINs para o banco de dados de identificação automática de local da sua operadora de rede telefônica pública comutada (ALI). Sua operadora PSTN pode exigir que você use um formato específico para os registros do ELIN. Entre em contato com a operadora PSTN para obter detalhes. Você pode exportar os registros do banco de dados do serviço de informações de local e formatá-los conforme necessário.

<div>

## <a name="to-publish-the-location-database"></a>Para publicar o banco de dados de local

  - Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

  - Execute o cmdlet a seguir para publicar o banco de dados de localização.
    
        Publish-CsLisConfiguration

</div>

</div>

<span> </span>

</div>

</div>

</div>

