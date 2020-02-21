---
title: 'Lync Server 2013: usando cmdlets para reverter a preparação do domínio'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using cmdlets to reverse domain preparation
ms:assetid: 014dba5d-fcb3-44c9-9d63-ae0755276dac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398071(v=OCS.15)
ms:contentKeyID: 48183227
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac26e17ad9e0ab13529da438bc2e12bec210808d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212897"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-cmdlets-to-reverse-domain-preparation-for-lync-server-2013"></a>Usando cmdlets para reverter a preparação do domínio para o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-29_

Use o cmdlet **Disable-CsAdDomain** para reverter a etapa de preparação do domínio.

<div>

## <a name="to-use-cmdlets-to-reverse-domain-preparation"></a>Para usar cmdlets para reverter a preparação de domínio

1.  Faça logon em qualquer servidor no domínio como um membro do grupo de Administradores de Domínio.

2.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

3.  Sejam
    
        Disable-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-Force <SwitchParameter>] 
        [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>] 
    
    Por exemplo:
    
        Disable-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.net -Force
    
    Se o parâmetro Force estiver presente, a preparação do domínio será revertida, mesmo que um ou mais servidores front-end ou servidores de conferência A/V no domínio estejam ativados. Se o parâmetro Force não estiver presente, a reversão de preparação do domínio será encerrada se qualquer servidor front-end ou servidores de conferência A/V no domínio estiver ativado.
    
    <div>
    

    > [!NOTE]  
    > O parâmetro GlobalSettingsDomainController permite indicar onde as configurações globais estão armazenadas. Se estiverem armazenadas no contêiner Sistema (o que é típico, quando as importações de atualização não tiveram a configuração global migrada para o contêiner Configuração), você define um controlador de domínio na raiz da sua floresta do Active Directory. Se as configurações globais estiverem no contêiner Configuração (o que é típico nas novas implantações ou nas atualizadas, onde as configurações foram migradas para o contêiner Configuração), você define qualquer controlador de domínio na floresta. Se você não especificar esse parâmetro, o cmdlet assumirá que as configurações são armazenadas no contêiner de configuração e se refere a qualquer controlador de domínio&nbsp;no AD DS.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Confira também


[Executando a preparação do domínio para o Lync Server 2013](lync-server-2013-running-domain-preparation.md)  


[Preparando domínios para o Lync Server 2013](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

