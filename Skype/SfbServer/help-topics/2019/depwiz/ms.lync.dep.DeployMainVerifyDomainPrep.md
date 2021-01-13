---
title: Verificar Replicação no Domínio
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainVerifyDomainPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 4846b787-d55e-4364-bdcd-2dee33f0251c
ROBOTS: NOINDEX, NOFOLLOW
description: 'Para verificar a replicação da preparação de domínio realizada na Etapa 1: Preparar Esquema, é necessário executar um cmdlet do Shell de Gerenciamento do Shell de Gerenciamento do Skype for Business Server Lync Server. Para executar o cmdlet do Windows PowerShell, faça logon em um computador que seja membro do domínio que você preparou e como membro do grupo Administradores de Domínio. Faça o seguinte:'
ms.openlocfilehash: 9ec39551702e0f3480671787536929863cb61f6b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801651"
---
# <a name="verify-replication-in-the-domain"></a><span data-ttu-id="e43c8-105">Verificar a Replicação no Domínio</span><span class="sxs-lookup"><span data-stu-id="e43c8-105">Verify Replication in the Domain</span></span>
 
<span data-ttu-id="e43c8-106">Para verificar a replicação da preparação de domínio realizada na Etapa **1:** Preparar Esquema, é necessário executar um cmdlet do Shell de Gerenciamento do Shell de Gerenciamento do Skype for Business Server Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e43c8-106">To verify replication of the domain preparation accomplished in **Step 1: Prepare Schema**, it is necessary to run a cmdlet from the Skype for Business Server Management Shell Lync Server Management Shell.</span></span> <span data-ttu-id="e43c8-107">Para executar o cmdlet do Windows PowerShell, faça logon em um computador que seja membro do domínio que você preparou e como membro do grupo Administradores de Domínio.</span><span class="sxs-lookup"><span data-stu-id="e43c8-107">To run the Windows PowerShell cmdlet, log on to a computer that is a member of the domain that you have prepared, and as a member of the Domain Admins group.</span></span> <span data-ttu-id="e43c8-108">Faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e43c8-108">Do the following:</span></span>
  
1. <span data-ttu-id="e43c8-109">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar,** em Todos os **Programas,** no **Skype for Business** e no Shell de Gerenciamento do Skype for Business **Server.**</span><span class="sxs-lookup"><span data-stu-id="e43c8-109">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="e43c8-110">No Windows PowerShell, digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e43c8-110">In Windows PowerShell, type the following:</span></span>
    
   ```PowerShell
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
   ```

    <span data-ttu-id="e43c8-111">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="e43c8-111">For example:</span></span>
    
   ```PowerShell
   Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
   ```

    > [!NOTE]
    > <span data-ttu-id="e43c8-112">O parâmetro GlobalSettingsDomainController permite indicar onde as configurações globais estão armazenadas.</span><span class="sxs-lookup"><span data-stu-id="e43c8-112">The parameter GlobalSettingsDomainController enables you to indicate where global settings are stored.</span></span> <span data-ttu-id="e43c8-113">Se suas configurações são armazenadas no contêiner Sistema (o que é comum em implantações de atualização que não tiveram a configuração global migrada para o contêiner Configuração), defina um controlador de domínio na raiz da floresta dos Serviços de Domínio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e43c8-113">If your settings are stored in the System container (which is typical with upgrade deployments that have not had the global setting migrated to the Configuration container), you define a domain controller in the root of your Active Directory Domain Services forest.</span></span> <span data-ttu-id="e43c8-114">Se as configurações globais estiverem no contêiner Configuração (o que é típico nas novas implantações ou nas atualizadas, onde as configurações foram migradas para o contêiner Configuração), você define qualquer controlador de domínio na floresta.</span><span class="sxs-lookup"><span data-stu-id="e43c8-114">If the global settings are in the Configuration container (which is typical with new deployments or upgrade deployments where the settings have been migrated to the Configuration container), you define any domain controller in the forest.</span></span> <span data-ttu-id="e43c8-115">Se você não especificar esse parâmetro, o cmdlet assumirá que as configurações estão armazenadas no contêiner Configuração e fará referência a qualquer controlador de domínio no Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e43c8-115">If you do not specify this parameter, the cmdlet assumes that the settings are stored in the Configuration container and refers to any domain controller in Active Directory.</span></span> 
  
    <span data-ttu-id="e43c8-116">Se você não especificar o parâmetro Domínio, o valor é configurado para o domínio local.</span><span class="sxs-lookup"><span data-stu-id="e43c8-116">If you do not specify the Domain parameter, the value is set to the local domain.</span></span> <span data-ttu-id="e43c8-117">Este cmdlet retorna um valor de **LC_DOMAIN_SETTINGS_STATE_READY** se a preparação do domínio foi bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="e43c8-117">This cmdlet returns a value of **LC_DOMAIN_SETTINGS_STATE_READY** if domain preparation was successful.</span></span>
    

