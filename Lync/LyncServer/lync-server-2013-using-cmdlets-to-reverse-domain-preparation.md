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

# <a name="using-cmdlets-to-reverse-domain-preparation-for-lync-server-2013"></a><span data-ttu-id="d4a6c-102">Usando cmdlets para reverter a preparação do domínio para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d4a6c-102">Using cmdlets to reverse domain preparation for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d4a6c-103">_**Tópico da última modificação:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="d4a6c-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="d4a6c-104">Use o cmdlet **Disable-CsAdDomain** para reverter a etapa de preparação do domínio.</span><span class="sxs-lookup"><span data-stu-id="d4a6c-104">Use the **Disable-CsAdDomain** cmdlet to reverse the domain preparation step.</span></span>

<div>

## <a name="to-use-cmdlets-to-reverse-domain-preparation"></a><span data-ttu-id="d4a6c-105">Para usar cmdlets para reverter a preparação do domínio</span><span class="sxs-lookup"><span data-stu-id="d4a6c-105">To use cmdlets to reverse domain preparation</span></span>

1.  <span data-ttu-id="d4a6c-106">Faça logon em qualquer servidor do domínio como membro do grupo Domain admins.</span><span class="sxs-lookup"><span data-stu-id="d4a6c-106">Log on to any server in the domain as a member of the Domain Admins group.</span></span>

2.  <span data-ttu-id="d4a6c-107">Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="d4a6c-107">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="d4a6c-108">Execute:</span><span class="sxs-lookup"><span data-stu-id="d4a6c-108">Run:</span></span>
    
        Disable-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-Force <SwitchParameter>] 
        [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>] 
    
    <span data-ttu-id="d4a6c-109">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="d4a6c-109">For example:</span></span>
    
        Disable-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.net -Force
    
    <span data-ttu-id="d4a6c-110">Se o parâmetro Force estiver presente, a preparação do domínio será revertida, mesmo se um ou mais servidores front-end ou servidores de conferência A/V do domínio estiverem ativados.</span><span class="sxs-lookup"><span data-stu-id="d4a6c-110">If the Force parameter is present, domain preparation is rolled back, even if one or more Front End Servers or A/V Conferencing Servers in the domain are activated.</span></span> <span data-ttu-id="d4a6c-111">Se o parâmetro Force não estiver presente, a reversão de preparação do domínio será terminada se qualquer servidor front-end ou servidores de conferência a/V do domínio estiverem ativados.</span><span class="sxs-lookup"><span data-stu-id="d4a6c-111">If the Force parameter is not present, domain preparation rollback is terminated if any Front End Servers or A/V Conferencing Servers in the domain are activated.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d4a6c-112">O parâmetro GlobalSettingsDomainController permite que você indique onde as configurações globais são armazenadas.</span><span class="sxs-lookup"><span data-stu-id="d4a6c-112">The parameter GlobalSettingsDomainController allows you to indicate where global settings are stored.</span></span> <span data-ttu-id="d4a6c-113">Se as configurações estiverem armazenadas no contêiner do sistema (que é típico com implantações de atualização que não tiveram a configuração global migrada para o contêiner de configuração), defina um controlador de domínio na raiz da sua floresta do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d4a6c-113">If your settings are stored in the System container (which is typical with upgrade deployments that have not had the global setting migrated to the Configuration container), you define a domain controller in the root of your Active Directory forest.</span></span> <span data-ttu-id="d4a6c-114">Se as configurações globais estiverem no contêiner Configuração (o que é normal em implantações novas ou em implantações de atualização nas quais as configurações foram migradas para o contêiner Configuração), defina qualquer controlador de domínio na floresta.</span><span class="sxs-lookup"><span data-stu-id="d4a6c-114">If the global settings are in the Configuration container (which is typical with new deployments or upgrade deployments where the settings have been migrated to the Configuration container), you define any domain controller in the forest.</span></span> <span data-ttu-id="d4a6c-115">Se você não especificar esse parâmetro, o cmdlet pressupõe que as configurações são armazenadas no contêiner de configuração e se refere a qualquer controlador de domínio no&nbsp;AD DS.</span><span class="sxs-lookup"><span data-stu-id="d4a6c-115">If you do not specify this parameter, the cmdlet assumes that the settings are stored in the Configuration container and refers to any domain controller in AD&nbsp;DS.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d4a6c-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="d4a6c-116">See Also</span></span>


[<span data-ttu-id="d4a6c-117">Executando preparação de domínio para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d4a6c-117">Running domain preparation for Lync Server 2013</span></span>](lync-server-2013-running-domain-preparation.md)  


[<span data-ttu-id="d4a6c-118">Preparando domínios para Server 2013</span><span class="sxs-lookup"><span data-stu-id="d4a6c-118">Preparing domains for Lync Server 2013</span></span>](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

