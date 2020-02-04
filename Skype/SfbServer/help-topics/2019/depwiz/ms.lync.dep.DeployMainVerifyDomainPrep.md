---
title: Verificar Replicação no Domínio
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeployMainVerifyDomainPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4846b787-d55e-4364-bdcd-2dee33f0251c
ROBOTS: NOINDEX, NOFOLLOW
description: 'Para verificar a replicação da preparação do domínio realizada na etapa 1: preparar o esquema, é necessário executar um cmdlet do Shell de gerenciamento do Shell de gerenciamento do Lync Server Management Shell. Para executar o cmdlet do Windows PowerShell, faça logon em um computador que seja membro do domínio que você preparou e como membro do grupo Domain admins. Do the following:'
ms.openlocfilehash: 7a9b8e90ce3c7c65f5f4b3d160ca7379b3bf8910
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41705407"
---
# <a name="verify-replication-in-the-domain"></a><span data-ttu-id="2880e-105">Verificar Replicação no Domínio</span><span class="sxs-lookup"><span data-stu-id="2880e-105">Verify Replication in the Domain</span></span>
 
<span data-ttu-id="2880e-106">Para verificar a replicação da preparação do domínio realizada na **etapa 1: preparar o esquema**, é necessário executar um cmdlet do Shell de gerenciamento do Shell de gerenciamento do Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="2880e-106">To verify replication of the domain preparation accomplished in **Step 1: Prepare Schema**, it is necessary to run a cmdlet from the Skype for Business Server Management Shell Lync Server Management Shell.</span></span> <span data-ttu-id="2880e-107">Para executar o cmdlet do Windows PowerShell, faça logon em um computador que seja membro do domínio que você preparou e como membro do grupo Domain admins.</span><span class="sxs-lookup"><span data-stu-id="2880e-107">To run the Windows PowerShell cmdlet, log on to a computer that is a member of the domain that you have prepared, and as a member of the Domain Admins group.</span></span> <span data-ttu-id="2880e-108">Do the following:</span><span class="sxs-lookup"><span data-stu-id="2880e-108">Do the following:</span></span>
  
1. <span data-ttu-id="2880e-109">Inicie o Shell de gerenciamento do Skype for Business Server: clique em **Iniciar**, clique em **todos os programas**, clique em **Skype for Business**e, em seguida, clique em **Shell de gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="2880e-109">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="2880e-110">No Windows PowerShell, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="2880e-110">In Windows PowerShell, type the following:</span></span>
    
   ```PowerShell
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
   ```

    <span data-ttu-id="2880e-111">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="2880e-111">For example:</span></span>
    
   ```PowerShell
   Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
   ```

    > [!NOTE]
    > <span data-ttu-id="2880e-112">O parâmetro GlobalSettingsDomainController permite que você indique onde as configurações globais estão armazenadas.</span><span class="sxs-lookup"><span data-stu-id="2880e-112">The parameter GlobalSettingsDomainController enables you to indicate where global settings are stored.</span></span> <span data-ttu-id="2880e-113">Se as configurações estiverem armazenadas no contêiner do sistema (que é típico com implantações de atualização que não tiveram a configuração global migrada para o contêiner de configuração), defina um controlador de domínio na raiz da floresta dos serviços de domínio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2880e-113">If your settings are stored in the System container (which is typical with upgrade deployments that have not had the global setting migrated to the Configuration container), you define a domain controller in the root of your Active Directory Domain Services forest.</span></span> <span data-ttu-id="2880e-114">Se as configurações globais estiverem no contêiner Configuração (o que é normal em implantações novas ou em implantações de atualização nas quais as configurações foram migradas para o contêiner Configuração), defina qualquer controlador de domínio na floresta.</span><span class="sxs-lookup"><span data-stu-id="2880e-114">If the global settings are in the Configuration container (which is typical with new deployments or upgrade deployments where the settings have been migrated to the Configuration container), you define any domain controller in the forest.</span></span> <span data-ttu-id="2880e-115">Se você não especificar esse parâmetro, o cmdlet assumirá que as configurações estão armazenadas no contêiner Configuração e fará referência a qualquer controlador de domínio no Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2880e-115">If you do not specify this parameter, the cmdlet assumes that the settings are stored in the Configuration container and refers to any domain controller in Active Directory.</span></span> 
  
    <span data-ttu-id="2880e-116">Se você não especificar o parâmetro Domínio, o valor será definido como o domínio local.</span><span class="sxs-lookup"><span data-stu-id="2880e-116">If you do not specify the Domain parameter, the value is set to the local domain.</span></span> <span data-ttu-id="2880e-117">Esse cmdlet retorna um valor de **LC_DOMAIN_SETTINGS_STATE_READY** se a preparação do domínio tiver êxito.</span><span class="sxs-lookup"><span data-stu-id="2880e-117">This cmdlet returns a value of **LC_DOMAIN_SETTINGS_STATE_READY** if domain preparation was successful.</span></span>
    

