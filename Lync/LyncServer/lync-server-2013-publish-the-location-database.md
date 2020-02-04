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
ms.openlocfilehash: d4e42d73a5b7ac36439aca673ff68c03cc13f50f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747081"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-the-location-database-from-lync-server-2013"></a>Publicar o banco de dados de localização do Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-30_

Os novos locais adicionados ao banco de dados de local não serão disponibilizados para o cliente até que sejam publicados.

Para obter detalhes, consulte a documentação do Shell de gerenciamento do Lync Server para o seguinte cmdlet:

  - **Publish-CsLisConfiguration**

Se você usar gateways ELIN, também é necessário carregar os ELINs para o banco de dados ALI da transportadora PSTN. Sua transportadora PSTN pode exigir que você use um formato específico para os registros ELIN. Entre em contato com sua transportadora PSTN para obter detalhes. Você pode exportar os registros do banco de dados do serviço de informações de localização e formatá-los conforme necessário.

<div>

## <a name="to-publish-the-location-database"></a>Para publicar o banco de dados local

  - Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

  - Execute o seguinte cmdlet para publicar o banco de dados local.
    
        Publish-CsLisConfiguration

</div>

</div>

<span> </span>

</div>

</div>

</div>

