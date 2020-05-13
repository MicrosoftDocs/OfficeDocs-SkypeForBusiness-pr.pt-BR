---
title: 'Lync Server 2013: administrar usuários em uma implantação híbrida'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Administering users in a hybrid deployment
ms:assetid: 6924ed7b-30a9-4be7-b952-90655625f2c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204967(v=OCS.15)
ms:contentKeyID: 48184381
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 906018941b00d8ef2cbb5e37aef8d1245ad93f00
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221435"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="administering-users-in-a-hybrid-lync-server-2013-deployment"></a>Administrar usuários em uma implantação híbrida do Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-05-29_

Você pode gerenciar as configurações e políticas de usuário para usuários migrados para o Lync Online usando os recursos de gerenciamento de usuário disponíveis no centro de administração do Microsoft 365. Você deve entrar usando sua conta de administrador de locatários para executar tarefas de administração.

<div>

## <a name="moving-users-back-to-on-premises"></a>Movendo usuários de volta para o local

<div class="">


> [!IMPORTANT]  
> Esta seção se aplica somente aos usuários que foram criados e habilitados para o Lync local e depois movidos de uma implantação local para o Lync Online. Se você deseja mover os usuários que foram criados no Lync Online (e que já não foram habilitados para o Lync em uma implantação local), confira, <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">movendo usuários do Lync Online para o Lync local no Lync Server 2013</A>.



</div>

  - Execute os cmdlets a seguir para mover um usuário do Lync Online de volta para o Lync local:
    
       ```PowerShell
        $cred=Get-Credential
       ```
    
       ```PowerShell
        Move-CsUser -Identity username@contoso.com -Target localpool.contoso.com -Credential $cred -HostedMigrationOverrideUrl <URL>
       ```

O formato da URL especificada para o parâmetro **HostedMigrationOverrideUrl** deve ser a URL para o pool onde o serviço de migração hospedado está sendo executado, no seguinte formato:

\<FQDN do Pool https:// \> /HostedMigration/hostedmigrationService.svc. Você pode determinar a URL para o serviço de migração hospedado visualizando a URL do painel de controle do Lync Online para sua conta de organização do Microsoft 365 ou do Office 365.

**Para determinar a URL do serviço de migração hospedado para sua organização do Microsoft 365 ou do Office 365**

1.  Faça logon em sua organização como administrador.

2.  Abra o **centro de administração do Lync**.

3.  Com o **centro de administração do Lync** exibido, selecione e copie a URL na barra de endereços até **Lync.com**. Uma URL de exemplo é semelhante à seguinte:
    
    `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`

4.  Substitua **Webdir** na URL por **admin**, resultando no seguinte:
    
    `https://admin0a.online.lync.com`

5.  Acrescente a seguinte cadeia de caracteres à URL: **/HostedMigration/hostedmigrationservice.svc**.
    
    A URL resultante, que é o valor do **HostedMigrationOverrideUrl**, deve ter a seguinte aparência:
    
    `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

</div>

</div>

<span> </span>

</div>

</div>

</div>

