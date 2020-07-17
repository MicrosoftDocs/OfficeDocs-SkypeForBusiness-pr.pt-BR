---
title: Instalar o pacote de compatibilidade com versões anteriores do WMI
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Install WMI Backward Compatibility package
ms:assetid: 38797fbd-06a0-4008-b099-158e7b5d7703
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204816(v=OCS.15)
ms:contentKeyID: 48183893
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 35be17aa08cf26f93a9d4002b23dacdfb35c5143
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756590"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="install-wmi-backward-compatibility-package"></a>Instalar o pacote de compatibilidade com versões anteriores do WMI

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-02_

Se você tentar executar o assistente de Fusão do Construtor de Topologias sem instalar o pacote de Compatibilidade com Versões Anteriores da WMI, você verá o seguinte erro:

![Mensagem de erro WMI](images/JJ204816.a007d2f2-fc85-430c-91eb-382b032469af(OCS.15).jpg "Mensagem de erro WMI")

Se tentar executar o cmdlet **Merge-CsLegacytopology** sem instalar o pacote de Compatibilidade com Versões Anteriores da WMI, você verá o seguinte erro:

![Erro do provedor WMI do Windows PowerShell](images/JJ204816.c510824e-1807-4c7e-bb28-c6cfea2eac1d(OCS.15).jpg "Erro do provedor WMI do Windows PowerShell")

Para instalar o pacote de Compatibilidade com Versões Anteriores da WMI

1.  Na mídia de instalação, navegue até \\ Setup \\ AMD64 \\ Setup \\OCSWMIBC.MSI.

2.  Instale o OCSWMIBC.MSI.
    
    <div>
    

    > [!IMPORTANT]  
    > O OCSWMIBC.msi deve ser instalado no computador em que o assistente de Fusão do Construtor de Topologias será executado. No entanto, é recomendável instalar o OCSWMIBC.msi em todos os servidores front-end de sua topologia.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > OCSWMIBC.msi pode ser instalado em qualquer computador no domínio que tenha os componentes principais do Lync Server 2013 e o Shell de gerenciamento do Lync Server 2013 instalado e tenha acesso à topologia do Office Communications Server 2007 R2 (provedor WMI para os serviços de domínio do Active Directory (AD DS) e ao SQL Server).

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

