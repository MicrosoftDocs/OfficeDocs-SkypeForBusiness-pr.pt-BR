---
title: 'Lync Server 2013: configurar um servidor de gerenciamento central existente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure an existing Central Management Server
ms:assetid: d715b24a-1256-4a7c-a5ef-1cee41d6b733
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205315(v=OCS.15)
ms:contentKeyID: 48185584
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7bfcd872f765e4a2ee69b09c4f1328125bc581d1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522998"
---
# <a name="configure-an-existing-central-management-server-in-lync-server-2013"></a>Configurar um servidor de gerenciamento central existente no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-21_

Se você reutilizar um servidor de gerenciamento central de uma implantação existente do Lync Server 2013, deverá executar o procedimento descrito abaixo para garantir que o painel de controle do Lync Server e o Windows PowerShell funcionem corretamente.

<div>

## <a name="to-configure-an-existing-central-management-server"></a>Para configurar um servidor de gerenciamento central existente

1.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

2.  Use o cmdlet **Update-CsAdminRole** para atualizar as funções RBAC (controle de acesso baseado em função) armazenadas no servidor de gerenciamento central.
    
    <div>
    

    > [!NOTE]  
    > Nenhum resultado é esperado a não ser que haja um erro.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

