---
title: 'Lync Server 2013: Configurar um Servidor de Gerenciamento Central existente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure an existing Central Management Server
ms:assetid: d715b24a-1256-4a7c-a5ef-1cee41d6b733
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205315(v=OCS.15)
ms:contentKeyID: 48185584
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eec9193d8c40a26179c5dfe1f142740abdda8bc4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836433"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-an-existing-central-management-server-in-lync-server-2013"></a>Configurar um Servidor de Gerenciamento Central existente no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-21_

Se você reutilizar um servidor central de gerenciamento de uma implantação existente do Lync Server 2013, será necessário executar o procedimento descrito abaixo para garantir que o painel de controle do Lync Server e o Windows PowerShell funcionem corretamente.

<div>

## <a name="to-configure-an-existing-central-management-server"></a>Para configurar um servidor de gerenciamento central existente

1.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

2.  Use o cmdlet **Update-CsAdminRole** para atualizar as funções de controle de acesso baseado em função (RBAC) armazenadas no servidor de gerenciamento central.
    
    <div>
    

    > [!NOTE]  
    > Nenhuma saída é esperada, a menos que haja um erro.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

