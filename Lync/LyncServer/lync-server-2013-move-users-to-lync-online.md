---
title: 'Lync Server 2013: mover usuários para o Lync Online'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Move users to Lync Online
ms:assetid: 6a523c86-2eac-4fa4-973a-4406872c9a7d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204969(v=OCS.15)
ms:contentKeyID: 48184392
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6172c526816a3572d6c364b714d5d4e7e5323cac
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991366"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-users-to-lync-online-in-lync-server-2013"></a>Mover usuários para o Lync Online no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-05-29_

Antes de começar a migrar usuários para o Lync Online, você deve fazer backup dos dados do usuário associados às contas a serem movidas. Nem todos os dados de usuário são movidos junto com a conta. Para obter informações, consulte [requisitos de backup e restauração no Lync Server 2013: dados](lync-server-2013-backup-and-restoration-requirements-data.md).

<div>

## <a name="migrate-user-settings-to-lync-online"></a>Migrar configurações de usuário para o Lync Online

As configurações do usuário são movidas com a conta do usuário. Algumas configurações locais não são movidas com a conta do usuário.

</div>

<div>

## <a name="moving-pilot-users-to-lync-online"></a>Movendo usuários piloto para o Lync Online

Antes de começar a mover usuários para o Lync Online, talvez você queira mover alguns usuários piloto para confirmar se o seu ambiente está configurado corretamente. Em seguida, você pode verificar se os recursos e serviços do Lync funcionam como esperado antes de tentar mover usuários adicionais.

Para mover um usuário local para o seu locatário do Lync Online, execute os seguintes cmdlets no Shell de gerenciamento do Lync Server usando as credenciais de administrador para o seu locatário do Microsoft Office 365. Substitua "username@contoso.com" pela informação do usuário que você deseja mover.

   ```PowerShell
    $creds=Get-Credential
   ```

   ```PowerShell
    Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>
   ```

O formato da URL especificada para o parâmetro **HostedMigrationOverrideUrl** deve ser a URL do pool em que o serviço de migração hospedada está em execução, no seguinte formato:\<https://pool\>FQDN/HostedMigration/hostedmigrationService.svc.

Você pode identificar a URL do serviço de migração hospedado visualizando a URL do Painel de Controle do Lync Online da sua conta de locatário do Office 365.

**Para identificar a URL do Serviço de Migração Hospedada do seu locatário do Office 365**

1.  Faça logon no seu inquilino do Office 365 como um administrador.

2.  Abra o **centro de administração do Lync**.

3.  Com o **centro de administração do Lync** exibido, selecione e copie a URL na barra de endereços até **Lync.com**. Uma URL de exemplo seria parecida com esta:
    
    `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`

4.  Substitua **webdir** na URL por **admin**, o que resulta no seguinte:
    
    `https://admin0a.online.lync.com`

5.  Anexe a cadeia de caracteres a seguir à URL: **/HostedMigration/hostedmigrationservice.svc**.
    
    A URL resultante, que tem o valor de **HostedMigrationOverrideUrl**, deverá ser parecida com esta:
    
    `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

</div>

<div>

## <a name="moving-users-to-lync-online"></a>Mover usuários para o Lync Online

Você pode mover vários usuários usando o cmdlet [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) com o parâmetro – Filter para selecionar os usuários com uma propriedade específica atribuída às contas de usuário, como RegistrarPool. Em seguida, você pode canalizar os usuários retornados para o cmdlet [move-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) , conforme mostrado no exemplo a seguir.

    Get-CsUser -Filter {UserProperty -eq "UserPropertyValue"} | Move-CsUser -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>

Você também pode usar o parâmetro -OU para recuperar todos os usuários no OU especificado, como mostrado no exemplo a seguir.

    Get-CsUser -OU "cn=hybridusers,cn=contoso.." | Move-CsUser -Target sipfed.online.lync.com -Credentials $creds -HostedMigrationOverrideUrl <URL>

</div>

<div>

## <a name="verify-lync-online-user-settings-and-features"></a>Verificar as configurações e os recursos do usuário do Lync Online

Você pode verificar que o usuário foi movido com sucesso das seguintes formas:

  - Exiba o status do usuário no painel de controle do Lync Online. O indicador visual para usuários no local e online é diferente.

  - Execute o seguinte cmdlet:
    
        Get-CsUser -Identity

</div>

</div>

<span> </span>

</div>

</div>

</div>

