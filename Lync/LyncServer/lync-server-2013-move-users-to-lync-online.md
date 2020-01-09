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

# <a name="move-users-to-lync-online-in-lync-server-2013"></a><span data-ttu-id="090b5-102">Mover usuários para o Lync Online no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="090b5-102">Move users to Lync Online in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="090b5-103">_**Tópico da última modificação:** 2014-05-29_</span><span class="sxs-lookup"><span data-stu-id="090b5-103">_**Topic Last Modified:** 2014-05-29_</span></span>

<span data-ttu-id="090b5-104">Antes de começar a migrar usuários para o Lync Online, você deve fazer backup dos dados do usuário associados às contas a serem movidas.</span><span class="sxs-lookup"><span data-stu-id="090b5-104">Before you start migrating users to Lync Online, you should backup the user data associated with the accounts to be moved.</span></span> <span data-ttu-id="090b5-105">Nem todos os dados de usuário são movidos junto com a conta.</span><span class="sxs-lookup"><span data-stu-id="090b5-105">Not all user data is moved with the user account.</span></span> <span data-ttu-id="090b5-106">Para obter informações, consulte [requisitos de backup e restauração no Lync Server 2013: dados](lync-server-2013-backup-and-restoration-requirements-data.md).</span><span class="sxs-lookup"><span data-stu-id="090b5-106">For information, see [Backup and restoration requirements in Lync Server 2013: data](lync-server-2013-backup-and-restoration-requirements-data.md).</span></span>

<div>

## <a name="migrate-user-settings-to-lync-online"></a><span data-ttu-id="090b5-107">Migrar configurações de usuário para o Lync Online</span><span class="sxs-lookup"><span data-stu-id="090b5-107">Migrate User Settings to Lync Online</span></span>

<span data-ttu-id="090b5-108">As configurações do usuário são movidas com a conta do usuário.</span><span class="sxs-lookup"><span data-stu-id="090b5-108">User settings are moved with the user account.</span></span> <span data-ttu-id="090b5-109">Algumas configurações locais não são movidas com a conta do usuário.</span><span class="sxs-lookup"><span data-stu-id="090b5-109">Some on-premises settings are not moved with the user account.</span></span>

</div>

<div>

## <a name="moving-pilot-users-to-lync-online"></a><span data-ttu-id="090b5-110">Movendo usuários piloto para o Lync Online</span><span class="sxs-lookup"><span data-stu-id="090b5-110">Moving Pilot Users to Lync Online</span></span>

<span data-ttu-id="090b5-111">Antes de começar a mover usuários para o Lync Online, talvez você queira mover alguns usuários piloto para confirmar se o seu ambiente está configurado corretamente.</span><span class="sxs-lookup"><span data-stu-id="090b5-111">Before you begin to move users to Lync Online, you may want to move a few pilot users to confirm that your environment is correctly configured.</span></span> <span data-ttu-id="090b5-112">Em seguida, você pode verificar se os recursos e serviços do Lync funcionam como esperado antes de tentar mover usuários adicionais.</span><span class="sxs-lookup"><span data-stu-id="090b5-112">You can then verify that Lync features and services function as expected before attempting to move additional users.</span></span>

<span data-ttu-id="090b5-113">Para mover um usuário local para o seu locatário do Lync Online, execute os seguintes cmdlets no Shell de gerenciamento do Lync Server usando as credenciais de administrador para o seu locatário do Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="090b5-113">To move an on-premises user to your Lync Online tenant, run the following cmdlets in the Lync Server Management Shell, using the administrator credentials for your Microsoft Office 365 tenant.</span></span> <span data-ttu-id="090b5-114">Substitua "username@contoso.com" pela informação do usuário que você deseja mover.</span><span class="sxs-lookup"><span data-stu-id="090b5-114">Replace "username@contoso.com" with the information for the user that you want to move.</span></span>

   ```PowerShell
    $creds=Get-Credential
   ```

   ```PowerShell
    Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>
   ```

<span data-ttu-id="090b5-115">O formato da URL especificada para o parâmetro **HostedMigrationOverrideUrl** deve ser a URL do pool em que o serviço de migração hospedada está em execução, no seguinte formato:\<https://pool\>FQDN/HostedMigration/hostedmigrationService.svc.</span><span class="sxs-lookup"><span data-stu-id="090b5-115">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format: Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc.</span></span>

<span data-ttu-id="090b5-116">Você pode identificar a URL do serviço de migração hospedado visualizando a URL do Painel de Controle do Lync Online da sua conta de locatário do Office 365.</span><span class="sxs-lookup"><span data-stu-id="090b5-116">You can determine the URL to the Hosted Migration Service by viewing the URL for the Lync Online Control Panel for your Office 365 tenant account.</span></span>

<span data-ttu-id="090b5-117">**Para identificar a URL do Serviço de Migração Hospedada do seu locatário do Office 365**</span><span class="sxs-lookup"><span data-stu-id="090b5-117">**To determine the Hosted Migration Service URL for your Office 365 tenant**</span></span>

1.  <span data-ttu-id="090b5-118">Faça logon no seu inquilino do Office 365 como um administrador.</span><span class="sxs-lookup"><span data-stu-id="090b5-118">Login to your Office 365 tenant as an administrator.</span></span>

2.  <span data-ttu-id="090b5-119">Abra o **centro de administração do Lync**.</span><span class="sxs-lookup"><span data-stu-id="090b5-119">Open the **Lync admin center**.</span></span>

3.  <span data-ttu-id="090b5-120">Com o **centro de administração do Lync** exibido, selecione e copie a URL na barra de endereços até **Lync.com**.</span><span class="sxs-lookup"><span data-stu-id="090b5-120">With the **Lync admin center** displayed, select and copy the URL in the address bar up to **lync.com**.</span></span> <span data-ttu-id="090b5-121">Uma URL de exemplo seria parecida com esta:</span><span class="sxs-lookup"><span data-stu-id="090b5-121">An example URL looks similar to the following:</span></span>
    
    `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`

4.  <span data-ttu-id="090b5-122">Substitua **webdir** na URL por **admin**, o que resulta no seguinte:</span><span class="sxs-lookup"><span data-stu-id="090b5-122">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span>
    
    `https://admin0a.online.lync.com`

5.  <span data-ttu-id="090b5-123">Anexe a cadeia de caracteres a seguir à URL: **/HostedMigration/hostedmigrationservice.svc**.</span><span class="sxs-lookup"><span data-stu-id="090b5-123">Append the following string to the URL: **/HostedMigration/hostedmigrationservice.svc**.</span></span>
    
    <span data-ttu-id="090b5-124">A URL resultante, que tem o valor de **HostedMigrationOverrideUrl**, deverá ser parecida com esta:</span><span class="sxs-lookup"><span data-stu-id="090b5-124">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>
    
    `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

</div>

<div>

## <a name="moving-users-to-lync-online"></a><span data-ttu-id="090b5-125">Mover usuários para o Lync Online</span><span class="sxs-lookup"><span data-stu-id="090b5-125">Moving Users to Lync Online</span></span>

<span data-ttu-id="090b5-126">Você pode mover vários usuários usando o cmdlet [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) com o parâmetro – Filter para selecionar os usuários com uma propriedade específica atribuída às contas de usuário, como RegistrarPool.</span><span class="sxs-lookup"><span data-stu-id="090b5-126">You can move multiple users by using the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) cmdlet with the –Filter parameter to select the users with a specific property assigned to the user accounts, such as RegistrarPool.</span></span> <span data-ttu-id="090b5-127">Em seguida, você pode canalizar os usuários retornados para o cmdlet [move-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) , conforme mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="090b5-127">You can then pipe the returned users to the [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) cmdlet, as shown in the following example.</span></span>

    Get-CsUser -Filter {UserProperty -eq "UserPropertyValue"} | Move-CsUser -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>

<span data-ttu-id="090b5-128">Você também pode usar o parâmetro -OU para recuperar todos os usuários no OU especificado, como mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="090b5-128">You can also use the –OU parameter to retrieve all users in the specified OU, as shown in the following example.</span></span>

    Get-CsUser -OU "cn=hybridusers,cn=contoso.." | Move-CsUser -Target sipfed.online.lync.com -Credentials $creds -HostedMigrationOverrideUrl <URL>

</div>

<div>

## <a name="verify-lync-online-user-settings-and-features"></a><span data-ttu-id="090b5-129">Verificar as configurações e os recursos do usuário do Lync Online</span><span class="sxs-lookup"><span data-stu-id="090b5-129">Verify Lync Online User Settings and Features</span></span>

<span data-ttu-id="090b5-130">Você pode verificar que o usuário foi movido com sucesso das seguintes formas:</span><span class="sxs-lookup"><span data-stu-id="090b5-130">You can verify that the user was moved successfully in the following ways:</span></span>

  - <span data-ttu-id="090b5-131">Exiba o status do usuário no painel de controle do Lync Online.</span><span class="sxs-lookup"><span data-stu-id="090b5-131">View the status of the user in the Lync Online Control Panel.</span></span> <span data-ttu-id="090b5-132">O indicador visual para usuários no local e online é diferente.</span><span class="sxs-lookup"><span data-stu-id="090b5-132">The visual indicator for on-premises users and online users is different.</span></span>

  - <span data-ttu-id="090b5-133">Execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="090b5-133">Run the following cmdlet:</span></span>
    
        Get-CsUser -Identity

</div>

</div>

<span> </span>

</div>

</div>

</div>

