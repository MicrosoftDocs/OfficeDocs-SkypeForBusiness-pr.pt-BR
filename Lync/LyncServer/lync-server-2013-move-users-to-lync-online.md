---
title: 'Lync Server 2013: mover usuários para o Lync Online'
description: 'Lync Server 2013: mover usuários para o Lync Online.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move users to Lync Online
ms:assetid: 6a523c86-2eac-4fa4-973a-4406872c9a7d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204969(v=OCS.15)
ms:contentKeyID: 48184392
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 501eda3a76cec3226831c0af3631317377cd82cb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48541978"
---
# <a name="move-users-to-lync-online-in-lync-server-2013"></a>Mover usuários para o Lync Online no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-05-29_

Antes de começar a migrar usuários para o Lync Online, você deve fazer backup dos dados do usuário associados às contas a serem movidas. Nem todos os dados do usuário são movidos com a conta do usuário. Para obter informações, consulte [requisitos de backup e restauração no Lync Server 2013: data](lync-server-2013-backup-and-restoration-requirements-data.md).

<div>

## <a name="migrate-user-settings-to-lync-online"></a>Migrar configurações do usuário para o Lync Online

As configurações de usuário são movidas com a conta de usuário. Algumas configurações locais não são movidas com a conta de usuário.

</div>

<div>

## <a name="moving-pilot-users-to-lync-online"></a>Movendo usuários do piloto para o Lync Online

Antes de começar a mover os usuários para o Lync Online, você pode querer mover alguns usuários do piloto para confirmar que seu ambiente está configurado corretamente. Em seguida, você pode verificar se os recursos e serviços do Lync funcionam conforme o esperado antes de tentar mover usuários adicionais.

Para mover um usuário local para seu locatário do Lync Online, execute os seguintes cmdlets no Shell de gerenciamento do Lync Server, usando as credenciais de administrador da sua organização do Microsoft 365 ou do Office 365. Substitua "username@contoso.com" com as informações do usuário que você deseja mover.

   ```PowerShell
    $creds=Get-Credential
   ```

   ```PowerShell
    Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>
   ```

O formato da URL especificada para o parâmetro **HostedMigrationOverrideUrl** deve ser a URL para o pool onde o serviço de migração hospedado está sendo executado, no seguinte formato: https:// \<Pool FQDN\> /HostedMigration/hostedmigrationService.svc.

Você pode determinar a URL para o serviço de migração hospedado visualizando a URL do painel de controle do Lync Online para sua conta de organização do Microsoft 365 ou do Office 365.

**Para determinar a URL do serviço de migração hospedado para sua organização**

1.  Faça logon na sua organização do Microsoft 365 ou do Office 365 como administrador.

2.  Abra o **centro de administração do Lync**.

3.  Com o **centro de administração do Lync** exibido, selecione e copie a URL na barra de endereços até **Lync.com**. Uma URL de exemplo é semelhante à seguinte:
    
    `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`

4.  Substitua **Webdir** na URL por **admin**, resultando no seguinte:
    
    `https://admin0a.online.lync.com`

5.  Acrescente a seguinte cadeia de caracteres à URL: **/HostedMigration/hostedmigrationservice.svc**.
    
    A URL resultante, que é o valor do **HostedMigrationOverrideUrl**, deve ter a seguinte aparência:
    
    `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

</div>

<div>

## <a name="moving-users-to-lync-online"></a>Movendo usuários para o Lync Online

Você pode mover vários usuários usando o cmdlet [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) com o parâmetro – Filter para selecionar os usuários com uma propriedade específica atribuída às contas de usuário, como RegistrarPool. Você pode canalizar os usuários retornados para o cmdlet [move-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) , conforme mostrado no exemplo a seguir.

    Get-CsUser -Filter {UserProperty -eq "UserPropertyValue"} | Move-CsUser -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>

Você também pode usar o parâmetro – OU para recuperar todos os usuários na OU especificada, conforme mostrado no exemplo a seguir.

    Get-CsUser -OU "cn=hybridusers,cn=contoso.." | Move-CsUser -Target sipfed.online.lync.com -Credentials $creds -HostedMigrationOverrideUrl <URL>

</div>

<div>

## <a name="verify-lync-online-user-settings-and-features"></a>Verificar as configurações e os recursos do usuário do Lync Online

Você pode verificar se o usuário foi movido com êxito das seguintes maneiras:

  - Exibir o status do usuário no painel de controle do Lync Online. O indicador visual para usuários locais e usuários online é diferente.

  - Execute o seguinte cmdlet:
    
        Get-CsUser -Identity

</div>

</div>

<span> </span>

</div>

</div>

</div>

