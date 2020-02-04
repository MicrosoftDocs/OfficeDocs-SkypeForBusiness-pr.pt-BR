---
title: 'Lync Server 2013: Usando cmdlets para reverter a preparação do domínio'
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
ms.openlocfilehash: d72c135e7daccd677f8e42ea93a2aace8d7cafb8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744191"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-cmdlets-to-reverse-domain-preparation-for-lync-server-2013"></a>Usando cmdlets para reverter a preparação do domínio para o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-29_

Use o cmdlet **Disable-CsAdDomain** para reverter a etapa de preparação do domínio.

<div>

## <a name="to-use-cmdlets-to-reverse-domain-preparation"></a>Para usar cmdlets para reverter a preparação do domínio

1.  Faça logon em qualquer servidor do domínio como membro do grupo Domain admins.

2.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

3.  Execute:
    
        Disable-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-Force <SwitchParameter>] 
        [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>] 
    
    Por exemplo:
    
        Disable-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.net -Force
    
    Se o parâmetro Force estiver presente, a preparação do domínio será revertida, mesmo se um ou mais servidores front-end ou servidores de conferência A/V do domínio estiverem ativados. Se o parâmetro Force não estiver presente, a reversão de preparação do domínio será terminada se qualquer servidor front-end ou servidores de conferência a/V do domínio estiverem ativados.
    
    <div>
    

    > [!NOTE]  
    > O parâmetro GlobalSettingsDomainController permite que você indique onde as configurações globais são armazenadas. Se as configurações estiverem armazenadas no contêiner do sistema (que é típico com implantações de atualização que não tiveram a configuração global migrada para o contêiner de configuração), defina um controlador de domínio na raiz da sua floresta do Active Directory. Se as configurações globais estiverem no contêiner Configuração (o que é normal em implantações novas ou em implantações de atualização nas quais as configurações foram migradas para o contêiner Configuração), defina qualquer controlador de domínio na floresta. Se você não especificar esse parâmetro, o cmdlet pressupõe que as configurações são armazenadas no contêiner de configuração e se refere a qualquer controlador de domínio no&nbsp;AD DS.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Confira também


[Executando preparação de domínio para Lync Server 2013](lync-server-2013-running-domain-preparation.md)  


[Preparando domínios para Server 2013](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

