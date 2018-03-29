---
title: Verificar Replicação no Domínio
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainVerifyDomainPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4846b787-d55e-4364-bdcd-2dee33f0251c
description: 'Para verificar a replicação a preparação do domínio realizada na etapa 1: preparar esquema, é necessário executar um cmdlet a partir do Skype para Business Server Management Shell do Lync Server Management Shell. Para executar o cmdlet do Windows PowerShell, faça logon em um computador que seja membro do domínio que você preparou e como membro do grupo Administradores de domínio. Faça o seguinte:'
ms.openlocfilehash: e3dca892ccb4937bcd84148a954270b4bd1362f5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="verify-replication-in-the-domain"></a><span data-ttu-id="39e0d-105">Verificar Replicação no Domínio</span><span class="sxs-lookup"><span data-stu-id="39e0d-105">Verify Replication in the Domain</span></span>
 
<span data-ttu-id="39e0d-106">Para verificar a replicação sobre a preparação de domínio realizada no **etapa 1: preparar esquema**, é necessário executar um cmdlet a partir do Skype para Business Server Management Shell do Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="39e0d-106">To verify replication of the domain preparation accomplished in **Step 1: Prepare Schema**, it is necessary to run a cmdlet from the Skype for Business Server Management Shell Lync Server Management Shell.</span></span> <span data-ttu-id="39e0d-107">Para executar o cmdlet do Windows PowerShell, faça logon em um computador que seja membro do domínio que você preparou e como membro do grupo Administradores de domínio.</span><span class="sxs-lookup"><span data-stu-id="39e0d-107">To run the Windows PowerShell cmdlet, log on to a computer that is a member of the domain that you have prepared, and as a member of the Domain Admins group.</span></span> <span data-ttu-id="39e0d-108">Faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="39e0d-108">Do the following:</span></span>
  
1. <span data-ttu-id="39e0d-109">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="39e0d-109">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="39e0d-110">No Windows PowerShell, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="39e0d-110">In Windows PowerShell, type the following:</span></span>
    
  ```
  Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
  ```

    <span data-ttu-id="39e0d-111">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="39e0d-111">For example:</span></span>
    
  ```
  Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
  ```

    > [!NOTE]
    > <span data-ttu-id="39e0d-112">O parâmetro GlobalSettingsDomainController permite que você indique onde as configurações globais estão armazenadas.</span><span class="sxs-lookup"><span data-stu-id="39e0d-112">The parameter GlobalSettingsDomainController enables you to indicate where global settings are stored.</span></span> <span data-ttu-id="39e0d-113">Se as configurações são armazenadas no contêiner do sistema (que é típico com implantações de atualização que não tiveram a configuração de global migrados para o contêiner configuração), você define um controlador de domínio na raiz da floresta do Active Directory Domain Services.</span><span class="sxs-lookup"><span data-stu-id="39e0d-113">If your settings are stored in the System container (which is typical with upgrade deployments that have not had the global setting migrated to the Configuration container), you define a domain controller in the root of your Active Directory Domain Services forest.</span></span> <span data-ttu-id="39e0d-114">Se as configurações globais estiverem no contêiner Configuração (o que é normal em implantações novas ou em implantações de atualização nas quais as configurações foram migradas para o contêiner Configuração), defina qualquer controlador de domínio na floresta.</span><span class="sxs-lookup"><span data-stu-id="39e0d-114">If the global settings are in the Configuration container (which is typical with new deployments or upgrade deployments where the settings have been migrated to the Configuration container), you define any domain controller in the forest.</span></span> <span data-ttu-id="39e0d-115">Se você não especificar esse parâmetro, o cmdlet assumirá que as configurações estão armazenadas no contêiner Configuração e fará referência a qualquer controlador de domínio no Active Directory.</span><span class="sxs-lookup"><span data-stu-id="39e0d-115">If you do not specify this parameter, the cmdlet assumes that the settings are stored in the Configuration container and refers to any domain controller in Active Directory.</span></span> 
  
    <span data-ttu-id="39e0d-116">Se você não especificar o parâmetro Domínio, o valor será definido como o domínio local.</span><span class="sxs-lookup"><span data-stu-id="39e0d-116">If you do not specify the Domain parameter, the value is set to the local domain.</span></span> <span data-ttu-id="39e0d-117">Este cmdlet retorna um valor de **LC_DOMAIN_SETTINGS_STATE_READY** se a preparação do domínio foi bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="39e0d-117">This cmdlet returns a value of **LC_DOMAIN_SETTINGS_STATE_READY** if domain preparation was successful.</span></span>
    

