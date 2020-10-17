---
title: 'Lync Server 2013: cmdlets de segurança'
description: 'Lync Server 2013: cmdlets de segurança.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Security cmdlets
ms:assetid: 9a6c654d-287d-434e-8d93-409f0d623f5a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398799(v=OCS.15)
ms:contentKeyID: 48184968
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c35b3304f8cbb153466409f79bf554581d8aea22
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551437"
---
# <a name="security-cmdlets-in-lync-server-2013"></a>Cmdlets de segurança no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-09_

Os cmdlets de segurança incluídos no Microsoft Lync Server 2013 são usados principalmente para gerenciar a autenticação e os direitos e permissões do usuário. Uma ampla variedade de cmdlets está disponível para o gerenciamento da autenticação, incluindo cmdlets para autenticação de certificado e de PIN (número de identificação pessoal). Além disso, vários cmdlets permitem que você use o novo recurso RBAC (controle de acesso baseado em função) para delegar o controle administrativo do Lync Server.

<div>

## <a name="security-cmdlets"></a>Cmdlets de segurança

Muitas tarefas de gerenciamento que se aplicam às configurações de segurança podem ser realizadas no painel de controle do Lync Server. Uma exceção importante são os cmdlets de permissão do usuário. No entanto, todas as tarefas de gerenciamento de segurança podem ser executadas usando cmdlets do Shell de gerenciamento do Lync Server ou de dentro de um script; o uso de um script permite automatizar determinadas tarefas. Veja a seguir uma lista de cmdlets relacionados diretamente ao gerenciamento de configurações de segurança:

**[Cmdlets de certificado e autenticação no Lync Server 2013](lync-server-2013-certificate-and-authentication-cmdlets.md)**

  - <span></span>  
    [Get-CsCertificate](https://technet.microsoft.com/library/Gg398227(v=OCS.15))

  - <span></span>  
    [Import-CsCertificate](https://technet.microsoft.com/library/Gg398688(v=OCS.15))

  - <span></span>  
    [Remove-CsCertificate](https://technet.microsoft.com/library/Gg412895(v=OCS.15))

  - <span></span>  
    [Request-CsCertificate](https://technet.microsoft.com/library/Gg425723(v=OCS.15))

  - <span></span>  
    [Set-CsCertificate](https://technet.microsoft.com/library/Gg398518(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsCertificateConfiguration](https://technet.microsoft.com/library/Gg398647(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsClientCertificate](https://technet.microsoft.com/library/Gg398143(v=OCS.15))

  - <span></span>  
    [REVOKE-CsClientCertificate](https://technet.microsoft.com/library/Gg425748(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Lock-CsClientPin](https://technet.microsoft.com/library/Gg398650(v=OCS.15))

  - <span></span>  
    [Set-CsClientPin](https://technet.microsoft.com/library/Gg398929(v=OCS.15))

  - <span></span>  
    [Unlock-CsClientPin](unhttps://technet.microsoft.com/library/Gg398650(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsClientPinInfo](https://technet.microsoft.com/library/Gg425947(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-CsKerberosAccount](https://technet.microsoft.com/library/Gg398485(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg398526(v=OCS.15))

  - <span></span>  
    [New-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg398074(v=OCS.15))

  - <span></span>  
    [Remove-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg413052(v=OCS.15))

  - <span></span>  
    [Set-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg398232(v=OCS.15))

  - <span></span>  
    [Test-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Set-CsKerberosAccountPassword](https://technet.microsoft.com/library/Gg398659(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsPinPolicy](https://technet.microsoft.com/library/Gg398262(v=OCS.15))

  - <span></span>  
    [Grant-CsPinPolicy](https://technet.microsoft.com/library/Gg398871(v=OCS.15))

  - <span></span>  
    [New-CsPinPolicy](https://technet.microsoft.com/library/Gg398935(v=OCS.15))

  - <span></span>  
    [Remove-CsPinPolicy](https://technet.microsoft.com/library/Gg398431(v=OCS.15))

  - <span></span>  
    [Set-CsPinPolicy](https://technet.microsoft.com/library/Gg412997(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsProxyConfiguration](https://technet.microsoft.com/library/Gg399011(v=OCS.15))

  - <span></span>  
    [New-CsProxyConfiguration](https://technet.microsoft.com/library/Gg398335(v=OCS.15))

  - <span></span>  
    [Remove-CsProxyConfiguration](https://technet.microsoft.com/library/Gg398553(v=OCS.15))

  - <span></span>  
    [Set-CsProxyConfiguration](https://technet.microsoft.com/library/Gg425796(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsSipDomain](https://technet.microsoft.com/library/Gg398701(v=OCS.15))

  - <span></span>  
    [New-CsSipDomain](https://technet.microsoft.com/library/Gg425857(v=OCS.15))

  - <span></span>  
    [Remove-CsSipDomain](https://technet.microsoft.com/library/Gg398865(v=OCS.15))

  - <span></span>  
    [Set-CsSipDomain](https://technet.microsoft.com/library/Gg412949(v=OCS.15))

**[Cmdlets de direitos de usuário e permissões no Lync Server 2013](lync-server-2013-user-rights-and-permissions-cmdlets.md)**

  - <span></span>  
    [Get-CsAdminRole](https://technet.microsoft.com/library/Gg399050(v=OCS.15))

  - <span></span>  
    [New-CsAdminRole](https://technet.microsoft.com/library/Gg398271(v=OCS.15))

  - <span></span>  
    [Remove-CsAdminRole](https://technet.microsoft.com/library/Gg413036(v=OCS.15))

  - <span></span>  
    [Set-CsAdminRole](https://technet.microsoft.com/library/Gg399066(v=OCS.15))

  - <span></span>  
    [Update-CsAdminRole](https://technet.microsoft.com/library/JJ204851(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsAdminRoleAssignment](https://technet.microsoft.com/library/Gg398434(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Grant-CsOUPermission](https://technet.microsoft.com/library/Gg425739(v=OCS.15))

  - <span></span>  
    [REVOKE-CsOUPermission](https://technet.microsoft.com/library/Gg398977(v=OCS.15))

  - <span></span>  
    [Test-CsOUPermission](https://technet.microsoft.com/library/Gg398787(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Grant-CsSetupPermission](https://technet.microsoft.com/library/Gg398569(v=OCS.15))

  - <span></span>  
    [REVOKE-CsSetupPermission](https://technet.microsoft.com/library/Gg425834(v=OCS.15))

  - <span></span>  
    [Test-CsSetupPermission](https://technet.microsoft.com/library/Gg398428(v=OCS.15))

**[Cmdlets de interoperabilidade no Lync Server 2013](lync-server-2013-interoperability-cmdlets.md)**

  - [Get-CsOAuthConfiguration](https://technet.microsoft.com/library/JJ205155(v=OCS.15))

  - [Set-CsOAuthConfiguration](https://technet.microsoft.com/library/JJ204841(v=OCS.15))

<!-- end list -->

  - [Get-CsOAuthServer](https://technet.microsoft.com/library/JJ205238(v=OCS.15))

  - [New-CsOAuthServer](https://technet.microsoft.com/library/JJ205206(v=OCS.15))

  - [Remove-CsOAuthServer](https://technet.microsoft.com/library/JJ205408(v=OCS.15))

  - [Set-CsOAuthServer](https://technet.microsoft.com/library/JJ204896(v=OCS.15))

<!-- end list -->

  - [Get-CsPartnerApplication](https://technet.microsoft.com/library/JJ205128(v=OCS.15))

  - [New-CsPartnerApplication](https://technet.microsoft.com/library/JJ204628(v=OCS.15))

  - [Remove-CsPartnerApplication](https://technet.microsoft.com/library/JJ204820(v=OCS.15))

  - [Set-CsPartnerApplication](https://technet.microsoft.com/library/JJ204755(v=OCS.15))

</div>

<div>

## <a name="see-also"></a>Confira também


[Blog do PowerShell do Lync Server](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

