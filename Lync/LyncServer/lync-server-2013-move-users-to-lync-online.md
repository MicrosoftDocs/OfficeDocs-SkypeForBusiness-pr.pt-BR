---
title: 'Lync Server 2013: mover usuários para o Lync Online'
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
ms.openlocfilehash: 5106d4e27921d9407b2663410cc0872892479ebb
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43779848"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-users-to-lync-online-in-lync-server-2013"></a><span data-ttu-id="ea2d7-102">Mover usuários para o Lync Online no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ea2d7-102">Move users to Lync Online in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ea2d7-103">_**Última modificação do tópico:** 2014-05-29_</span><span class="sxs-lookup"><span data-stu-id="ea2d7-103">_**Topic Last Modified:** 2014-05-29_</span></span>

<span data-ttu-id="ea2d7-104">Antes de começar a migrar usuários para o Lync Online, você deve fazer backup dos dados do usuário associados às contas a serem movidas.</span><span class="sxs-lookup"><span data-stu-id="ea2d7-104">Before you start migrating users to Lync Online, you should backup the user data associated with the accounts to be moved.</span></span> <span data-ttu-id="ea2d7-105">Nem todos os dados do usuário são movidos com a conta do usuário.</span><span class="sxs-lookup"><span data-stu-id="ea2d7-105">Not all user data is moved with the user account.</span></span> <span data-ttu-id="ea2d7-106">Para obter informações, consulte [requisitos de backup e restauração no Lync Server 2013: data](lync-server-2013-backup-and-restoration-requirements-data.md).</span><span class="sxs-lookup"><span data-stu-id="ea2d7-106">For information, see [Backup and restoration requirements in Lync Server 2013: data](lync-server-2013-backup-and-restoration-requirements-data.md).</span></span>

<div>

## <a name="migrate-user-settings-to-lync-online"></a><span data-ttu-id="ea2d7-107">Migrar configurações do usuário para o Lync Online</span><span class="sxs-lookup"><span data-stu-id="ea2d7-107">Migrate User Settings to Lync Online</span></span>

<span data-ttu-id="ea2d7-108">As configurações de usuário são movidas com a conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="ea2d7-108">User settings are moved with the user account.</span></span> <span data-ttu-id="ea2d7-109">Algumas configurações locais não são movidas com a conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="ea2d7-109">Some on-premises settings are not moved with the user account.</span></span>

</div>

<div>

## <a name="moving-pilot-users-to-lync-online"></a><span data-ttu-id="ea2d7-110">Movendo usuários do piloto para o Lync Online</span><span class="sxs-lookup"><span data-stu-id="ea2d7-110">Moving Pilot Users to Lync Online</span></span>

<span data-ttu-id="ea2d7-111">Antes de começar a mover os usuários para o Lync Online, você pode querer mover alguns usuários do piloto para confirmar que seu ambiente está configurado corretamente.</span><span class="sxs-lookup"><span data-stu-id="ea2d7-111">Before you begin to move users to Lync Online, you may want to move a few pilot users to confirm that your environment is correctly configured.</span></span> <span data-ttu-id="ea2d7-112">Em seguida, você pode verificar se os recursos e serviços do Lync funcionam conforme o esperado antes de tentar mover usuários adicionais.</span><span class="sxs-lookup"><span data-stu-id="ea2d7-112">You can then verify that Lync features and services function as expected before attempting to move additional users.</span></span>

<span data-ttu-id="ea2d7-113">Para mover um usuário local para seu locatário do Lync Online, execute os seguintes cmdlets no Shell de gerenciamento do Lync Server, usando as credenciais de administrador da sua organização do Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="ea2d7-113">To move an on-premises user to your Lync Online tenant, run the following cmdlets in the Lync Server Management Shell, using the administrator credentials for your Microsoft Office 365 organization.</span></span> <span data-ttu-id="ea2d7-114">Substitua "username@contoso.com" com as informações do usuário que você deseja mover.</span><span class="sxs-lookup"><span data-stu-id="ea2d7-114">Replace "username@contoso.com" with the information for the user that you want to move.</span></span>

   ```PowerShell
    $creds=Get-Credential
   ```

   ```PowerShell
    Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>
   ```

<span data-ttu-id="ea2d7-115">O formato da URL especificada para o parâmetro **HostedMigrationOverrideUrl** deve ser a URL para o pool onde o serviço de migração hospedado está sendo executado, no seguinte formato: https://\<pool FQDN\>/HostedMigration/hostedmigrationService.svc.</span><span class="sxs-lookup"><span data-stu-id="ea2d7-115">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format: Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc.</span></span>

<span data-ttu-id="ea2d7-116">Você pode determinar a URL para o serviço de migração hospedado visualizando a URL do painel de controle do Lync Online para sua conta da organização do Office 365.</span><span class="sxs-lookup"><span data-stu-id="ea2d7-116">You can determine the URL to the Hosted Migration Service by viewing the URL for the Lync Online Control Panel for your Office 365 organization account.</span></span>

<span data-ttu-id="ea2d7-117">**Para determinar a URL do serviço de migração hospedado para sua organização do Office 365**</span><span class="sxs-lookup"><span data-stu-id="ea2d7-117">**To determine the Hosted Migration Service URL for your Office 365 organization**</span></span>

1.  <span data-ttu-id="ea2d7-118">Faça logon na sua organização do Office 365 como administrador.</span><span class="sxs-lookup"><span data-stu-id="ea2d7-118">Login to your Office 365 organization as an administrator.</span></span>

2.  <span data-ttu-id="ea2d7-119">Abra o **centro de administração do Lync**.</span><span class="sxs-lookup"><span data-stu-id="ea2d7-119">Open the **Lync admin center**.</span></span>

3.  <span data-ttu-id="ea2d7-120">Com o **centro de administração do Lync** exibido, selecione e copie a URL na barra de endereços até **Lync.com**.</span><span class="sxs-lookup"><span data-stu-id="ea2d7-120">With the **Lync admin center** displayed, select and copy the URL in the address bar up to **lync.com**.</span></span> <span data-ttu-id="ea2d7-121">Uma URL de exemplo é semelhante à seguinte:</span><span class="sxs-lookup"><span data-stu-id="ea2d7-121">An example URL looks similar to the following:</span></span>
    
    `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`

4.  <span data-ttu-id="ea2d7-122">Substitua **Webdir** na URL por **admin**, resultando no seguinte:</span><span class="sxs-lookup"><span data-stu-id="ea2d7-122">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span>
    
    `https://admin0a.online.lync.com`

5.  <span data-ttu-id="ea2d7-123">Acrescente a seguinte cadeia de caracteres à URL: **/HostedMigration/hostedmigrationservice.svc**.</span><span class="sxs-lookup"><span data-stu-id="ea2d7-123">Append the following string to the URL: **/HostedMigration/hostedmigrationservice.svc**.</span></span>
    
    <span data-ttu-id="ea2d7-124">A URL resultante, que é o valor do **HostedMigrationOverrideUrl**, deve ter a seguinte aparência:</span><span class="sxs-lookup"><span data-stu-id="ea2d7-124">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>
    
    `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

</div>

<div>

## <a name="moving-users-to-lync-online"></a><span data-ttu-id="ea2d7-125">Movendo usuários para o Lync Online</span><span class="sxs-lookup"><span data-stu-id="ea2d7-125">Moving Users to Lync Online</span></span>

<span data-ttu-id="ea2d7-126">Você pode mover vários usuários usando o cmdlet [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) com o parâmetro – Filter para selecionar os usuários com uma propriedade específica atribuída às contas de usuário, como RegistrarPool.</span><span class="sxs-lookup"><span data-stu-id="ea2d7-126">You can move multiple users by using the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) cmdlet with the –Filter parameter to select the users with a specific property assigned to the user accounts, such as RegistrarPool.</span></span> <span data-ttu-id="ea2d7-127">Você pode canalizar os usuários retornados para o cmdlet [move-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) , conforme mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="ea2d7-127">You can then pipe the returned users to the [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) cmdlet, as shown in the following example.</span></span>

    Get-CsUser -Filter {UserProperty -eq "UserPropertyValue"} | Move-CsUser -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>

<span data-ttu-id="ea2d7-128">Você também pode usar o parâmetro – OU para recuperar todos os usuários na OU especificada, conforme mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="ea2d7-128">You can also use the –OU parameter to retrieve all users in the specified OU, as shown in the following example.</span></span>

    Get-CsUser -OU "cn=hybridusers,cn=contoso.." | Move-CsUser -Target sipfed.online.lync.com -Credentials $creds -HostedMigrationOverrideUrl <URL>

</div>

<div>

## <a name="verify-lync-online-user-settings-and-features"></a><span data-ttu-id="ea2d7-129">Verificar as configurações e os recursos do usuário do Lync Online</span><span class="sxs-lookup"><span data-stu-id="ea2d7-129">Verify Lync Online User Settings and Features</span></span>

<span data-ttu-id="ea2d7-130">Você pode verificar se o usuário foi movido com êxito das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="ea2d7-130">You can verify that the user was moved successfully in the following ways:</span></span>

  - <span data-ttu-id="ea2d7-131">Exibir o status do usuário no painel de controle do Lync Online.</span><span class="sxs-lookup"><span data-stu-id="ea2d7-131">View the status of the user in the Lync Online Control Panel.</span></span> <span data-ttu-id="ea2d7-132">O indicador visual para usuários locais e usuários online é diferente.</span><span class="sxs-lookup"><span data-stu-id="ea2d7-132">The visual indicator for on-premises users and online users is different.</span></span>

  - <span data-ttu-id="ea2d7-133">Execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="ea2d7-133">Run the following cmdlet:</span></span>
    
        Get-CsUser -Identity

</div>

</div>

<span> </span>

</div>

</div>

</div>

