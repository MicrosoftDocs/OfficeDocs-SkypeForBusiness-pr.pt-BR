---
title: Instalar o pacote de compatibilidade com versões anteriores do WMI
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Install WMI Backward Compatibility package
ms:assetid: 38797fbd-06a0-4008-b099-158e7b5d7703
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204816(v=OCS.15)
ms:contentKeyID: 48183893
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b61d34ce8809f06156f4d4dca61c39cc4aff0f1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836982"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-wmi-backward-compatibility-package"></a>Instalar o pacote de compatibilidade com versões anteriores do WMI

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-02_

Se você tentar executar o assistente de mesclagem do construtor de topologia sem instalar o pacote de compatibilidade com versões anteriores do WMI, o seguinte erro será exibido:

![Mensagem de erro WMI] (images/JJ204816.a007d2f2-fc85-430c-91eb-382b032469af(OCS.15).jpg "Mensagem de erro WMI")

Se você tentar executar o cmdlet **Merge-CsLegacytopology** sem instalar o pacote de compatibilidade com versões anteriores do WMI, o seguinte erro será exibido:

![Erro do provedor WMI do Windows PowerShell] (images/JJ204816.c510824e-1807-4c7e-bb28-c6cfea2eac1d(OCS.15).jpg "Erro do provedor WMI do Windows PowerShell")

Para instalar o pacote de compatibilidade com versões anteriores do WMI

1.  Na mídia de instalação, navegue até \\Setup\\AMD64\\Setup\\OCSWMIBC. MSI.

2.  Instale o OCSWMIBC. MSI.
    
    <div>
    

    > [!IMPORTANT]  
    > O OCSWMIBC. msi deve estar instalado no computador em que o assistente de mesclagem do construtor de topologias é executado. No entanto, recomendamos instalar o OCSWMIBC. msi em todos os servidores de front-end na sua topologia.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > O OCSWMIBC. msi pode ser instalado em qualquer computador do domínio que tenha os componentes principais do Lync Server 2013 e o Shell de gerenciamento do Lync Server 2013 instalado e tenha acesso à topologia do Office Communications Server 2007 R2 (provedor WMI para o domínio do Active Directory Services (AD DS) e SQL Server).

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

