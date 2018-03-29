---
title: Implantar a ferramenta SEFAUtil no Skype for Business 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
description: Implantando a ferramenta de SEFAUtil em Skype para Business Server.
ms.openlocfilehash: eba4c6d9c6d0c48256621537350a822c3314ca40
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-the-sefautil-tool-in-skype-for-business-2015"></a><span data-ttu-id="e73fd-103">Implantar a ferramenta SEFAUtil no Skype for Business 2015</span><span class="sxs-lookup"><span data-stu-id="e73fd-103">Deploy the SEFAUtil tool in Skype for Business 2015</span></span>
 
<span data-ttu-id="e73fd-104">Implantando a ferramenta de SEFAUtil em Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="e73fd-104">Deploying the SEFAUtil tool in Skype for Business Server.</span></span>
  
<span data-ttu-id="e73fd-105">Para implantar e gerenciar o atendimento de chamada de grupo, você precisará usar o Skype para Business Server versão da ferramenta SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="e73fd-105">To deploy and manage Group Call Pickup, you need to use the Skype for Business Server version of the SEFAUtil tool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="e73fd-106">O Microsoft UCMA (Unified Communications Managed API) 3.0 Core SDK deve estar instalado em qualquer computador no qual você planeja executar a ferramenta SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="e73fd-106">Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK must be installed on any computer where you plan to run the SEFAUtil tool.</span></span> 
  
<span data-ttu-id="e73fd-107">Você pode executar a ferramenta de SEFAUtil em qualquer pool de Front-End em sua implantação.</span><span class="sxs-lookup"><span data-stu-id="e73fd-107">You can run the SEFAUtil tool in any Front End pool in your deployment.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e73fd-108">Para obter mais detalhes sobre como executar SEFAUtil, consulte o artigo do blog Technet "[como obter SEFAutil executando?](https://go.microsoft.com/fwlink/?LinkId=278940)".</span><span class="sxs-lookup"><span data-stu-id="e73fd-108">For more details about running SEFAUtil, see the Technet blog article, "[How to get SEFAutil running?](https://go.microsoft.com/fwlink/?LinkId=278940)".</span></span> 
  
### <a name="to-deploy-sefautil"></a><span data-ttu-id="e73fd-109">Para implantar a SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="e73fd-109">To deploy SEFAUtil</span></span>

1. <span data-ttu-id="e73fd-110">Faça logon no computador onde o Skype do Shell de gerenciamento do servidor de negócios está instalado como membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário necessários, conforme descrito em **Delegate Setup Permissions**.</span><span class="sxs-lookup"><span data-stu-id="e73fd-110">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="e73fd-111">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="e73fd-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="e73fd-112">A ferramenta SEFAUtil só pode ser executada em um computador que integra um pool de aplicativos confiáveis.</span><span class="sxs-lookup"><span data-stu-id="e73fd-112">The SEFAUtil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="e73fd-113">Se necessário, definir um pool de aplicativos confiáveis para o pool de Front-End no qual você pretende executar SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="e73fd-113">If needed, define a trusted application pool for the Front End pool where you plan to run SEFAUtil.</span></span> <span data-ttu-id="e73fd-114">Na linha de comando, execute:</span><span class="sxs-lookup"><span data-stu-id="e73fd-114">At the command line, run:</span></span>
    
   ```
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```

4. <span data-ttu-id="e73fd-p102">Defina a ferramenta SEFAUtil como um aplicativo confiável. Na linha de comando, execute:</span><span class="sxs-lookup"><span data-stu-id="e73fd-p102">Define the SEFAUtil tool as a trusted application. At the command line, run:</span></span>
    
   ```
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
   ```

    > [!NOTE]
    > <span data-ttu-id="e73fd-117">Se necessário, você pode usar uma porta diferente.</span><span class="sxs-lookup"><span data-stu-id="e73fd-117">You can use a different port if needed.</span></span> 
  
5. <span data-ttu-id="e73fd-p103">Habilite a topologia com suas alterações. Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="e73fd-p103">Enable the topology with your changes. At the command line, run:</span></span>
    
  ```
  Enable-CsTopology
  ```

6. <span data-ttu-id="e73fd-120">Se você ainda não estiver, baixe o Skype para Business Server versão da ferramenta SEFAUtil [nesse local](https://www.microsoft.com/en-us/download/details.aspx?id=52631)e instale-o em um pool de aplicativos confiáveis que você criou na etapa 3.</span><span class="sxs-lookup"><span data-stu-id="e73fd-120">If you haven't already, download the Skype for Business Server version of the SEFAUtil tool from [this location](https://www.microsoft.com/en-us/download/details.aspx?id=52631), and install it on the trusted application pool you created in step 3.</span></span>
    
7. <span data-ttu-id="e73fd-121">Verifique se a ferramenta SEFAUtil está sendo executada corretamente conforme segue:</span><span class="sxs-lookup"><span data-stu-id="e73fd-121">Verify that the SEFAUtil tool is running correctly, as follows:</span></span> 
    
    <span data-ttu-id="e73fd-122">a.</span><span class="sxs-lookup"><span data-stu-id="e73fd-122">a.</span></span> <span data-ttu-id="e73fd-123">Execute a ferramenta no prompt de comando do Windows com privilégios de administrador para exibir as configurações de encaminhamento de chamada de um usuário de sua implantação.</span><span class="sxs-lookup"><span data-stu-id="e73fd-123">Run the tool from the Windows command prompt with administrator privileges to display the call forwarding settings of a user in your deployment.</span></span>
    
    <span data-ttu-id="e73fd-124">b.</span><span class="sxs-lookup"><span data-stu-id="e73fd-124">b.</span></span> <span data-ttu-id="e73fd-125">Exiba as configurações de um usuário de encaminhamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="e73fd-125">Display the call forwarding settings of a user.</span></span> <span data-ttu-id="e73fd-126">Na linha de comando, execute:</span><span class="sxs-lookup"><span data-stu-id="e73fd-126">At the command line, run:</span></span>
    
  ```
  SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
  ```

<span data-ttu-id="e73fd-127">As configurações de encaminhamento de chamada do usuário serão exibidas.</span><span class="sxs-lookup"><span data-stu-id="e73fd-127">The call forwarding settings for the user will be displayed.</span></span>
    

