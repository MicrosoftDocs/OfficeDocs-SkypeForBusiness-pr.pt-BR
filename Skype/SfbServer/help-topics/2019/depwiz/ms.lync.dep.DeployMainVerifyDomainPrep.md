---
title: Verificar Replicação no Domínio
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainVerifyDomainPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4846b787-d55e-4364-bdcd-2dee33f0251c
ROBOTS: NOINDEX, NOFOLLOW
description: 'Para verificar a replicação a preparação do domínio realizada na etapa 1: preparar esquema, é necessário executar um cmdlet a partir do Skype para Business Server Management Shell do Lync Server Management Shell. Para executar o cmdlet do Windows PowerShell, faça logon em um computador que seja membro do domínio que você preparou e como membro do grupo Administradores de domínio. Do the following:'
ms.openlocfilehash: 8adec80d9f0874e395150941cada02f58099bce9
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32216071"
---
# <a name="verify-replication-in-the-domain"></a><span data-ttu-id="6f17d-105">Verificar Replicação no Domínio</span><span class="sxs-lookup"><span data-stu-id="6f17d-105">Verify Replication in the Domain</span></span>
 
<span data-ttu-id="6f17d-106">Para verificar a replicação sobre a preparação de domínio realizada no **etapa 1: preparar esquema**, é necessário executar um cmdlet a partir do Skype para Business Server Management Shell do Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="6f17d-106">To verify replication of the domain preparation accomplished in **Step 1: Prepare Schema**, it is necessary to run a cmdlet from the Skype for Business Server Management Shell Lync Server Management Shell.</span></span> <span data-ttu-id="6f17d-107">Para executar o cmdlet do Windows PowerShell, faça logon em um computador que seja membro do domínio que você preparou e como membro do grupo Administradores de domínio.</span><span class="sxs-lookup"><span data-stu-id="6f17d-107">To run the Windows PowerShell cmdlet, log on to a computer that is a member of the domain that you have prepared, and as a member of the Domain Admins group.</span></span> <span data-ttu-id="6f17d-108">Do the following:</span><span class="sxs-lookup"><span data-stu-id="6f17d-108">Do the following:</span></span>
  
1. <span data-ttu-id="6f17d-109">Inicie o Skype do Shell de gerenciamento do servidor de negócios: clique em **Iniciar**, clique em **Todos os programas**, clique **Skype para negócios**e, em seguida, clique em **Skype do Shell de gerenciamento do servidor de negócios**.</span><span class="sxs-lookup"><span data-stu-id="6f17d-109">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="6f17d-110">No Windows PowerShell, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="6f17d-110">In Windows PowerShell, type the following:</span></span>
    
   ```
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
   ```

    <span data-ttu-id="6f17d-111">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="6f17d-111">For example:</span></span>
    
   ```
   Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
   ```

    > [!NOTE]
    > <span data-ttu-id="6f17d-112">O parâmetro GlobalSettingsDomainController permite que você indique onde as configurações globais estão armazenadas.</span><span class="sxs-lookup"><span data-stu-id="6f17d-112">The parameter GlobalSettingsDomainController enables you to indicate where global settings are stored.</span></span> <span data-ttu-id="6f17d-113">Se as configurações são armazenadas no contêiner do sistema (que é típico com implantações de atualização que não tiveram a configuração de global migrados para o contêiner configuração), você define um controlador de domínio na raiz da floresta do Active Directory Domain Services.</span><span class="sxs-lookup"><span data-stu-id="6f17d-113">If your settings are stored in the System container (which is typical with upgrade deployments that have not had the global setting migrated to the Configuration container), you define a domain controller in the root of your Active Directory Domain Services forest.</span></span> <span data-ttu-id="6f17d-114">Se as configurações globais estiverem no contêiner Configuração (o que é normal em implantações novas ou em implantações de atualização nas quais as configurações foram migradas para o contêiner Configuração), defina qualquer controlador de domínio na floresta.</span><span class="sxs-lookup"><span data-stu-id="6f17d-114">If the global settings are in the Configuration container (which is typical with new deployments or upgrade deployments where the settings have been migrated to the Configuration container), you define any domain controller in the forest.</span></span> <span data-ttu-id="6f17d-115">Se você não especificar esse parâmetro, o cmdlet assumirá que as configurações estão armazenadas no contêiner Configuração e fará referência a qualquer controlador de domínio no Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6f17d-115">If you do not specify this parameter, the cmdlet assumes that the settings are stored in the Configuration container and refers to any domain controller in Active Directory.</span></span> 
  
    <span data-ttu-id="6f17d-116">Se você não especificar o parâmetro Domínio, o valor será definido como o domínio local.</span><span class="sxs-lookup"><span data-stu-id="6f17d-116">If you do not specify the Domain parameter, the value is set to the local domain.</span></span> <span data-ttu-id="6f17d-117">Esse cmdlet retorna um valor de **LC_DOMAIN_SETTINGS_STATE_READY** se a preparação do domínio tiver êxito.</span><span class="sxs-lookup"><span data-stu-id="6f17d-117">This cmdlet returns a value of **LC_DOMAIN_SETTINGS_STATE_READY** if domain preparation was successful.</span></span>
    

