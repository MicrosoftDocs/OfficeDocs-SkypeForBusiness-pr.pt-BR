---
title: 'Lync Server 2013: usando cmdlets para reverter a preparação do domínio'
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
ms.openlocfilehash: ac26e17ad9e0ab13529da438bc2e12bec210808d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212897"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-cmdlets-to-reverse-domain-preparation-for-lync-server-2013"></a><span data-ttu-id="4e589-102">Usando cmdlets para reverter a preparação do domínio para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e589-102">Using cmdlets to reverse domain preparation for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4e589-103">_**Última modificação do tópico:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="4e589-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="4e589-104">Use o cmdlet **Disable-CsAdDomain** para reverter a etapa de preparação do domínio.</span><span class="sxs-lookup"><span data-stu-id="4e589-104">Use the **Disable-CsAdDomain** cmdlet to reverse the domain preparation step.</span></span>

<div>

## <a name="to-use-cmdlets-to-reverse-domain-preparation"></a><span data-ttu-id="4e589-105">Para usar cmdlets para reverter a preparação de domínio</span><span class="sxs-lookup"><span data-stu-id="4e589-105">To use cmdlets to reverse domain preparation</span></span>

1.  <span data-ttu-id="4e589-106">Faça logon em qualquer servidor no domínio como um membro do grupo de Administradores de Domínio.</span><span class="sxs-lookup"><span data-stu-id="4e589-106">Log on to any server in the domain as a member of the Domain Admins group.</span></span>

2.  <span data-ttu-id="4e589-107">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="4e589-107">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="4e589-108">Sejam</span><span class="sxs-lookup"><span data-stu-id="4e589-108">Run:</span></span>
    
        Disable-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-Force <SwitchParameter>] 
        [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>] 
    
    <span data-ttu-id="4e589-109">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="4e589-109">For example:</span></span>
    
        Disable-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.net -Force
    
    <span data-ttu-id="4e589-110">Se o parâmetro Force estiver presente, a preparação do domínio será revertida, mesmo que um ou mais servidores front-end ou servidores de conferência A/V no domínio estejam ativados.</span><span class="sxs-lookup"><span data-stu-id="4e589-110">If the Force parameter is present, domain preparation is rolled back, even if one or more Front End Servers or A/V Conferencing Servers in the domain are activated.</span></span> <span data-ttu-id="4e589-111">Se o parâmetro Force não estiver presente, a reversão de preparação do domínio será encerrada se qualquer servidor front-end ou servidores de conferência A/V no domínio estiver ativado.</span><span class="sxs-lookup"><span data-stu-id="4e589-111">If the Force parameter is not present, domain preparation rollback is terminated if any Front End Servers or A/V Conferencing Servers in the domain are activated.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4e589-112">O parâmetro GlobalSettingsDomainController permite indicar onde as configurações globais estão armazenadas.</span><span class="sxs-lookup"><span data-stu-id="4e589-112">The parameter GlobalSettingsDomainController allows you to indicate where global settings are stored.</span></span> <span data-ttu-id="4e589-113">Se estiverem armazenadas no contêiner Sistema (o que é típico, quando as importações de atualização não tiveram a configuração global migrada para o contêiner Configuração), você define um controlador de domínio na raiz da sua floresta do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4e589-113">If your settings are stored in the System container (which is typical with upgrade deployments that have not had the global setting migrated to the Configuration container), you define a domain controller in the root of your Active Directory forest.</span></span> <span data-ttu-id="4e589-114">Se as configurações globais estiverem no contêiner Configuração (o que é típico nas novas implantações ou nas atualizadas, onde as configurações foram migradas para o contêiner Configuração), você define qualquer controlador de domínio na floresta.</span><span class="sxs-lookup"><span data-stu-id="4e589-114">If the global settings are in the Configuration container (which is typical with new deployments or upgrade deployments where the settings have been migrated to the Configuration container), you define any domain controller in the forest.</span></span> <span data-ttu-id="4e589-115">Se você não especificar esse parâmetro, o cmdlet assumirá que as configurações são armazenadas no contêiner de configuração e se refere a qualquer controlador de domínio&nbsp;no AD DS.</span><span class="sxs-lookup"><span data-stu-id="4e589-115">If you do not specify this parameter, the cmdlet assumes that the settings are stored in the Configuration container and refers to any domain controller in AD&nbsp;DS.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4e589-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="4e589-116">See Also</span></span>


[<span data-ttu-id="4e589-117">Executando a preparação do domínio para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e589-117">Running domain preparation for Lync Server 2013</span></span>](lync-server-2013-running-domain-preparation.md)  


[<span data-ttu-id="4e589-118">Preparando domínios para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e589-118">Preparing domains for Lync Server 2013</span></span>](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

