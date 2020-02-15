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
ms.openlocfilehash: a82cb5ae505db5db3bbd8dd216ad61256368814e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "41998736"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="administering-users-in-a-hybrid-lync-server-2013-deployment"></a><span data-ttu-id="8b374-102">Administrar usuários em uma implantação híbrida do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8b374-102">Administering users in a hybrid Lync Server 2013 deployment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8b374-103">_**Última modificação do tópico:** 2014-05-29_</span><span class="sxs-lookup"><span data-stu-id="8b374-103">_**Topic Last Modified:** 2014-05-29_</span></span>

<span data-ttu-id="8b374-104">Você pode gerenciar as configurações e políticas de usuário para usuários migrados para o Lync Online usando os recursos de gerenciamento de usuários disponíveis no portal online do Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="8b374-104">You can manage user settings and policies for users migrated to Lync Online by using the User Management features available in the Microsoft Office 365 online portal.</span></span> <span data-ttu-id="8b374-105">Você deve entrar usando sua conta de administrador de locatários para executar tarefas de administração.</span><span class="sxs-lookup"><span data-stu-id="8b374-105">You must sign in by using your tenant administrator account to perform administration tasks.</span></span>

<div>

## <a name="moving-users-back-to-on-premises"></a><span data-ttu-id="8b374-106">Movendo usuários de volta para o local</span><span class="sxs-lookup"><span data-stu-id="8b374-106">Moving Users Back to On-premises</span></span>

<div class="">


> [!IMPORTANT]  
> <span data-ttu-id="8b374-107">Esta seção se aplica somente aos usuários que foram criados e habilitados para o Lync local e depois movidos de uma implantação local para o Lync Online.</span><span class="sxs-lookup"><span data-stu-id="8b374-107">This section applies only to users that were created and enabled for Lync on-premises and then moved from an on-premises deployment to Lync Online.</span></span> <span data-ttu-id="8b374-108">Se você deseja mover os usuários que foram criados no Lync Online (e que já não foram habilitados para o Lync em uma implantação local), confira, <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">movendo usuários do Lync Online para o Lync local no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="8b374-108">If you want to move users that were created in Lync Online (and not ever enabled for Lync in an on-premises deployment) see, <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">Moving users from Lync Online to Lync on-premises in Lync Server 2013</A>.</span></span>



</div>

  - <span data-ttu-id="8b374-109">Execute os cmdlets a seguir para mover um usuário do Lync Online de volta para o Lync local:</span><span class="sxs-lookup"><span data-stu-id="8b374-109">Run the following cmdlets to move a user from Lync Online back to Lync on-premises:</span></span>
    
       ```PowerShell
        $cred=Get-Credential
       ```
    
       ```PowerShell
        Move-CsUser -Identity username@contoso.com -Target localpool.contoso.com -Credential $cred -HostedMigrationOverrideUrl <URL>
       ```

<span data-ttu-id="8b374-110">O formato da URL especificada para o parâmetro **HostedMigrationOverrideUrl** deve ser a URL para o pool onde o serviço de migração hospedado está sendo executado, no seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="8b374-110">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format:</span></span>

<span data-ttu-id="8b374-111">FQDN\<\>do pool https:///HostedMigration/hostedmigrationService.svc.</span><span class="sxs-lookup"><span data-stu-id="8b374-111">Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc.</span></span> <span data-ttu-id="8b374-112">Você pode determinar a URL para o serviço de migração hospedado visualizando a URL do painel de controle do Lync Online para sua conta de locatário do Office 365.</span><span class="sxs-lookup"><span data-stu-id="8b374-112">You can determine the URL to the Hosted Migration Service by viewing the URL for the Lync Online Control Panel for your Office 365 tenant account.</span></span>

<span data-ttu-id="8b374-113">**Para determinar a URL do serviço de migração hospedado para seu locatário do Office 365**</span><span class="sxs-lookup"><span data-stu-id="8b374-113">**To determine the Hosted Migration Service URL for your Office 365 tenant**</span></span>

1.  <span data-ttu-id="8b374-114">Faça logon no seu locatário do Office 365 como administrador.</span><span class="sxs-lookup"><span data-stu-id="8b374-114">Login to your Office 365 tenant as an administrator.</span></span>

2.  <span data-ttu-id="8b374-115">Abra o **centro de administração do Lync**.</span><span class="sxs-lookup"><span data-stu-id="8b374-115">Open the **Lync admin center**.</span></span>

3.  <span data-ttu-id="8b374-116">Com o **centro de administração do Lync** exibido, selecione e copie a URL na barra de endereços até **Lync.com**.</span><span class="sxs-lookup"><span data-stu-id="8b374-116">With the **Lync admin center** displayed, select and copy the URL in the address bar up to **lync.com**.</span></span> <span data-ttu-id="8b374-117">Uma URL de exemplo é semelhante à seguinte:</span><span class="sxs-lookup"><span data-stu-id="8b374-117">An example URL looks similar to the following:</span></span>
    
    `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`

4.  <span data-ttu-id="8b374-118">Substitua **Webdir** na URL por **admin**, resultando no seguinte:</span><span class="sxs-lookup"><span data-stu-id="8b374-118">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span>
    
    `https://admin0a.online.lync.com`

5.  <span data-ttu-id="8b374-119">Acrescente a seguinte cadeia de caracteres à URL: **/HostedMigration/hostedmigrationservice.svc**.</span><span class="sxs-lookup"><span data-stu-id="8b374-119">Append the following string to the URL: **/HostedMigration/hostedmigrationservice.svc**.</span></span>
    
    <span data-ttu-id="8b374-120">A URL resultante, que é o valor do **HostedMigrationOverrideUrl**, deve ter a seguinte aparência:</span><span class="sxs-lookup"><span data-stu-id="8b374-120">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>
    
    `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

</div>

</div>

<span> </span>

</div>

</div>

</div>

