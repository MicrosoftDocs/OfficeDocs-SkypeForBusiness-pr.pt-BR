---
title: 'Lync Server 2013: administrando usuários em uma implantação híbrida'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Administering users in a hybrid deployment
ms:assetid: 6924ed7b-30a9-4be7-b952-90655625f2c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204967(v=OCS.15)
ms:contentKeyID: 48184381
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0dd4f53eaa611d130291b1a42c798a8d5589968c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837020"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="administering-users-in-a-hybrid-lync-server-2013-deployment"></a>Administrando usuários em uma implantação híbrida do Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-05-29_

Você pode gerenciar configurações de usuário e políticas para usuários migrados para o Lync Online usando os recursos de gerenciamento de usuários disponíveis no portal online do Microsoft Office 365. Faça login usando sua conta de administrador do locatário para executar tarefas administrativas.

<div>

## <a name="moving-users-back-to-on-premises"></a>Movendo usuários de volta para o local

<div class="">


> [!IMPORTANT]  
> Esta seção se aplica somente aos usuários que foram criados e habilitados para o Lync local e depois movidos de uma implantação local para o Lync Online. Se você quiser mover os usuários que foram criados no Lync Online (e ainda não habilitou o Lync em uma implantação local), consulte <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">movendo usuários do Lync Online para o Lync local no Lync Server 2013</A>.



</div>

  - Execute os seguintes cmdlets para mover um usuário do Lync Online de volta para o Lync local:
    
       ```
        $cred=Get-Credential
       ```
    
       ```
        Move-CsUser -Identity username@contoso.com -Target localpool.contoso.com -Credential $cred -HostedMigrationOverrideUrl <URL>
       ```

O formato da URL especificada para o parâmetro **HostedMigrationOverrideUrl** deve ser a URL para o pool no qual o Serviço de Migração Hospedada está sendo executado, no seguinte formato:

Https://\<pool FQDN\>/HostedMigration/hostedmigrationService.svc. Você pode identificar a URL do serviço de migração hospedado visualizando a URL do Painel de Controle do Lync Online da sua conta de locatário do Office 365.

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

</div>

<span> </span>

</div>

</div>

</div>

