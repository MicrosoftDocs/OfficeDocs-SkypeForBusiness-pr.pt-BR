---
title: 'Lync Server 2013: exibir configurações do servidor de borda'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View Edge Server settings
ms:assetid: 684154cc-cffc-4d2e-8baa-be52c625e5d7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn747890(v=OCS.15)
ms:contentKeyID: 63969612
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e978e28ea2c9d64a842c40237f1e5943c30d0a41
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051605"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-edge-server-settings-in-lync-server-2013"></a><span data-ttu-id="e9898-102">Exibir configurações do servidor de borda no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9898-102">View Edge Server settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e9898-103">_**Última modificação do tópico:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="e9898-103">_**Topic Last Modified:** 2014-05-20_</span></span>

<span data-ttu-id="e9898-104">As configurações de servidor de borda geral devem ser analisadas em relação aos dados do banco de dados de gerenciamento de configuração para ajudar a garantir que todas as alterações tenham sido documentadas de acordo com os procedimentos definidos de controle de alterações.</span><span class="sxs-lookup"><span data-stu-id="e9898-104">General Edge Server configurations should be reviewed against the data in the configuration management database—to help guarantee that all changes were documented as per the defined change control procedures.</span></span>

<span data-ttu-id="e9898-105">As verificações adicionais podem incluir as descritas nas seguintes seções:</span><span class="sxs-lookup"><span data-stu-id="e9898-105">Additional checks could include those that are described in the following sections:</span></span>

<div>

## <a name="verify-the-allow-and-block-lists"></a><span data-ttu-id="e9898-106">Verificar as listas de permissões e bloqueios</span><span class="sxs-lookup"><span data-stu-id="e9898-106">Verify the Allow and block lists</span></span>

<span data-ttu-id="e9898-107">Verifique o URI SIP "permitir" e "bloquear" listas para domínios federados, para determinar se os namespaces listados ainda são válidos.</span><span class="sxs-lookup"><span data-stu-id="e9898-107">Verify the SIP URI "Allow" and "Block" lists for Federated domains—to determine whether listed namespaces are still valid.</span></span>

<span data-ttu-id="e9898-108">Você pode usar o Windows PowerShell para exibir as listas permitidas e bloqueadas.</span><span class="sxs-lookup"><span data-stu-id="e9898-108">You can use Windows PowerShell to view the allowed and blocked lists.</span></span> <span data-ttu-id="e9898-109">Para revisar os domínios na lista de domínios permitidos, execute o seguinte comando do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e9898-109">To review the domains on the Allowed Domains list, run the following Windows PowerShell command:</span></span>

`Get-CsAllowedDomain`

<span data-ttu-id="e9898-110">Esse comando retorna informações semelhantes a estas para os domínios na lista de domínios permitidos:</span><span class="sxs-lookup"><span data-stu-id="e9898-110">That command returns information similar to this for the domains on the Allowed Domains list:</span></span>

<span data-ttu-id="e9898-111">Identidade: contoso.com</span><span class="sxs-lookup"><span data-stu-id="e9898-111">Identity : contoso.com</span></span>

<span data-ttu-id="e9898-112">Domínio: contoso.com</span><span class="sxs-lookup"><span data-stu-id="e9898-112">Domain : contoso.com</span></span>

<span data-ttu-id="e9898-113">ProxyFqdn</span><span class="sxs-lookup"><span data-stu-id="e9898-113">ProxyFqdn :</span></span>

<span data-ttu-id="e9898-114">Retire</span><span class="sxs-lookup"><span data-stu-id="e9898-114">Comment :</span></span>

<span data-ttu-id="e9898-115">MarkForMonitoring: falso</span><span class="sxs-lookup"><span data-stu-id="e9898-115">MarkForMonitoring : False</span></span>

<span data-ttu-id="e9898-116">Retire</span><span class="sxs-lookup"><span data-stu-id="e9898-116">Comment :</span></span>

<span data-ttu-id="e9898-117">Para revisar os domínios na lista de domínios bloqueados, use este comando:</span><span class="sxs-lookup"><span data-stu-id="e9898-117">To review the domains on the blocked domains list, use this command:</span></span>

`Get-CsBlockedDomain`

<span data-ttu-id="e9898-118">Por sua vez, você receberá informações como esta para cada domínio bloqueado:</span><span class="sxs-lookup"><span data-stu-id="e9898-118">In turn, you'll receive information such as this for each blocked domain:</span></span>

<span data-ttu-id="e9898-119">Identidade: tailspintoys.com</span><span class="sxs-lookup"><span data-stu-id="e9898-119">Identity : tailspintoys.com</span></span>

<span data-ttu-id="e9898-120">Domínio: tailspintoys.com</span><span class="sxs-lookup"><span data-stu-id="e9898-120">Domain : tailspintoys.com</span></span>

<span data-ttu-id="e9898-121">O Windows PowerShell também permite verificar se você pode se conectar aos domínios da sua lista de domínios permitidos.</span><span class="sxs-lookup"><span data-stu-id="e9898-121">Windows PowerShell also enables you to verify that you can connection to the domains on your Allowed Domains list.</span></span> <span data-ttu-id="e9898-122">Por exemplo, este comando verifica a conexão entre o servidor de borda (o TargetFqdn) e o domínio federado contoso.com:</span><span class="sxs-lookup"><span data-stu-id="e9898-122">For example, this command verifies the connection between your Edge Server (the TargetFqdn) and the federated domain contoso.com:</span></span>

`Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com"`

<span data-ttu-id="e9898-123">E este comando verifica a conexão entre o servidor de borda e todos os domínios encontrados na sua lista de domínios permitidos:</span><span class="sxs-lookup"><span data-stu-id="e9898-123">And this command verifies the connection between your Edge Server and all of the domains found on your Allowed Domains list:</span></span>

`Get-CsAllowedDomain | ForEach-Object {Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain $_.Domain}`

</div>

<div>

## <a name="verify-multiple-edge-servers-are-identical"></a><span data-ttu-id="e9898-124">Verificar se vários servidores de borda são idênticos</span><span class="sxs-lookup"><span data-stu-id="e9898-124">Verify multiple Edge Servers are identical</span></span>

<span data-ttu-id="e9898-125">Se vários servidores de borda forem implantados em uma matriz com balanceamento de carga, recomendamos verificar se todos os servidores de borda na matriz estão configurados da mesma maneira.</span><span class="sxs-lookup"><span data-stu-id="e9898-125">If multiple Edge Servers are deployed in a load balanced array, we recommend verifying that all Edge Servers in the array are configured in the same manner.</span></span>

<span data-ttu-id="e9898-126">Você pode exibir configurações para servidores de borda no painel de detalhes da extensão do Lync Server 2013 para o snap-in Gerenciamento do computador.</span><span class="sxs-lookup"><span data-stu-id="e9898-126">You can view settings for Edge Servers in the details pane of the Lync Server 2013 extension for the Computer Management snap-in.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e9898-127">Confira Também</span><span class="sxs-lookup"><span data-stu-id="e9898-127">See Also</span></span>


[<span data-ttu-id="e9898-128">Get-CsAllowedDomain</span><span class="sxs-lookup"><span data-stu-id="e9898-128">Get-CsAllowedDomain</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAllowedDomain)  
[<span data-ttu-id="e9898-129">Get-CsBlockedDomain</span><span class="sxs-lookup"><span data-stu-id="e9898-129">Get-CsBlockedDomain</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsBlockedDomain)  
[<span data-ttu-id="e9898-130">Test-CsFederatedPartner</span><span class="sxs-lookup"><span data-stu-id="e9898-130">Test-CsFederatedPartner</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

