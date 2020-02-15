---
title: Implantar a ferramenta SEFAUtil no Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
description: Implantar a ferramenta SEFAUtil no Skype for Business Server.
ms.openlocfilehash: 306e2ec305e9e12cd3486691b3e239e2aedfb548
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "41986806"
---
# <a name="deploy-the-sefautil-tool-in-skype-for-business"></a><span data-ttu-id="71e15-103">Implantar a ferramenta SEFAUtil no Skype for Business</span><span class="sxs-lookup"><span data-stu-id="71e15-103">Deploy the SEFAUtil tool in Skype for Business</span></span>
 
<span data-ttu-id="71e15-104">Implantar a ferramenta SEFAUtil no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="71e15-104">Deploying the SEFAUtil tool in Skype for Business Server.</span></span>
  
<span data-ttu-id="71e15-105">Para implantar e gerenciar o recebimento de chamadas em grupo, você precisa usar a versão do Skype for Business Server da ferramenta SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="71e15-105">To deploy and manage Group Call Pickup, you need to use the Skype for Business Server version of the SEFAUtil tool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="71e15-106">O Microsoft Unified Communications Managed API (UCMA) 5 Runtime deve ser instalado em qualquer computador no qual você planeja executar a ferramenta SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="71e15-106">Microsoft Unified Communications Managed API (UCMA) 5 Runtime must be installed on any computer where you plan to run the SEFAUtil tool.</span></span> <span data-ttu-id="71e15-107">Baixe-o aqui: [Unified Communications Managed API 5,0 Runtime](https://www.microsoft.com/download/details.aspx?id=47344).</span><span class="sxs-lookup"><span data-stu-id="71e15-107">Download it here: [Unified Communications Managed API 5.0 Runtime](https://www.microsoft.com/download/details.aspx?id=47344).</span></span> <span data-ttu-id="71e15-108">Você também pode baixar o UCMA 5 SDK, que inclui o tempo de execução, aqui: [UCMA 5,0 SDK](https://www.microsoft.com/download/details.aspx?id=47345).</span><span class="sxs-lookup"><span data-stu-id="71e15-108">You can also download the UCMA 5 SDK, which includes the runtime, here: [UCMA 5.0 SDK](https://www.microsoft.com/download/details.aspx?id=47345).</span></span>
  
<span data-ttu-id="71e15-109">Você pode executar a ferramenta SEFAUtil em qualquer pool de front-ends em sua implantação.</span><span class="sxs-lookup"><span data-stu-id="71e15-109">You can run the SEFAUtil tool in any Front End pool in your deployment.</span></span> <span data-ttu-id="71e15-110">Para executar a ferramenta SEFAUtil você deve executar as etapas 1, 2 e 3 do assistente de implantação do Skype for Business no computador de aplicativo confiável.</span><span class="sxs-lookup"><span data-stu-id="71e15-110">To run the SEFAUtil tool you must run Steps 1, 2, and 3 from the Skype for Business Deployment Wizard on the Trusted Application Computer.</span></span> <span data-ttu-id="71e15-111">O SEFAUtil exige que o repositório de configuração local esteja presente, bem como um certificado.</span><span class="sxs-lookup"><span data-stu-id="71e15-111">SEFAUtil requires the local configuration store to be present, as well as a certificate.</span></span>
  
> [!NOTE]
> <span data-ttu-id="71e15-112">Para obter mais detalhes sobre a execução do SEFAUtil, consulte o artigo do blog, "[How to Get SEFAUtil running?](https://go.microsoft.com/fwlink/?LinkId=278940)".</span><span class="sxs-lookup"><span data-stu-id="71e15-112">For more details about running SEFAUtil, see the  blog article, "[How to get SEFAutil running?](https://go.microsoft.com/fwlink/?LinkId=278940)".</span></span> 
  
### <a name="to-deploy-sefautil"></a><span data-ttu-id="71e15-113">Para implantar o SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="71e15-113">To deploy SEFAUtil</span></span>

1. <span data-ttu-id="71e15-114">Faça logon no computador onde o Shell de gerenciamento do Skype for Business Server está instalado como um membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário necessários, conforme descrito em **delegar permissões de configuração**.</span><span class="sxs-lookup"><span data-stu-id="71e15-114">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="71e15-115">Inicie o Shell de gerenciamento do Skype for Business Server: clique em **Iniciar**, em **todos os programas**, em **Skype for Business 2015**e em **Shell de gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="71e15-115">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="71e15-116">A ferramenta SEFAUtil pode ser executada apenas em um computador que faça parte de um pool de aplicativos confiáveis.</span><span class="sxs-lookup"><span data-stu-id="71e15-116">The SEFAUtil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="71e15-117">Se necessário, defina um pool de aplicativos confiáveis para o pool de front-ends onde você planeja executar o SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="71e15-117">If needed, define a trusted application pool for the Front End pool where you plan to run SEFAUtil.</span></span> <span data-ttu-id="71e15-118">Na linha de comando, execute:</span><span class="sxs-lookup"><span data-stu-id="71e15-118">At the command line, run:</span></span>
    
   ```powershell
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```
    > [!NOTE]
    > <span data-ttu-id="71e15-119">FQDN do pool: o FQDN do servidor ou pool que hospedará o aplicativo SEFAUtil (geralmente um servidor front-end do Skype for Business ou pool).</span><span class="sxs-lookup"><span data-stu-id="71e15-119">Pool FQDN: The FQDN of the server or pool that will host the SEFAUtil application (usually a Skype for Business Front End server or pool).</span></span>
    > <span data-ttu-id="71e15-120">FQDN do registrador de pool: o FQDN do servidor front-end do Skype for Business ou pool associado a esse pool de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="71e15-120">Pool Registrar FQDN: The FQDN of the Skype for Business Front End server or pool associated with this application pool.</span></span>
    > <span data-ttu-id="71e15-121">Site do pool: a ID do site em que este pool está hospedado.</span><span class="sxs-lookup"><span data-stu-id="71e15-121">Pool Site: The Site ID of the site on which this pool is homed.</span></span>

4. <span data-ttu-id="71e15-122">Defina a ferramenta SEFAUtil como um aplicativo confiável.</span><span class="sxs-lookup"><span data-stu-id="71e15-122">Define the SEFAUtil tool as a trusted application.</span></span> <span data-ttu-id="71e15-123">Na linha de comando, execute:</span><span class="sxs-lookup"><span data-stu-id="71e15-123">At the command line, run:</span></span>
    
   ```powershell
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
   ```

    > [!NOTE]
    > <span data-ttu-id="71e15-124">Você pode usar uma porta diferente, se necessário.</span><span class="sxs-lookup"><span data-stu-id="71e15-124">You can use a different port if needed.</span></span> 
  
5. <span data-ttu-id="71e15-125">Habilite a topologia com suas alterações.</span><span class="sxs-lookup"><span data-stu-id="71e15-125">Enable the topology with your changes.</span></span> <span data-ttu-id="71e15-126">Na linha de comando, execute:</span><span class="sxs-lookup"><span data-stu-id="71e15-126">At the command line, run:</span></span>
    
   ```powershell
   Enable-CsTopology
   ```

6. <span data-ttu-id="71e15-127">Se ainda não tiver feito isso, baixe a versão do Skype for Business Server da ferramenta SEFAUtil desse [local](https://www.microsoft.com/download/details.aspx?id=52631)e instale-a no pool de aplicativos confiáveis que você criou na etapa 3.</span><span class="sxs-lookup"><span data-stu-id="71e15-127">If you haven't already, download the Skype for Business Server version of the SEFAUtil tool from [this location](https://www.microsoft.com/download/details.aspx?id=52631), and install it on the trusted application pool you created in step 3.</span></span>
    
7. <span data-ttu-id="71e15-128">Verifique se a ferramenta SEFAUtil está funcionando corretamente, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="71e15-128">Verify that the SEFAUtil tool is running correctly, as follows:</span></span> 
    
    <span data-ttu-id="71e15-129">a.</span><span class="sxs-lookup"><span data-stu-id="71e15-129">a.</span></span> <span data-ttu-id="71e15-130">Execute a ferramenta a partir do prompt de comando do Windows com privilégios de administrador para exibir as configurações de encaminhamento de chamadas de um usuário em sua implantação.</span><span class="sxs-lookup"><span data-stu-id="71e15-130">Run the tool from the Windows command prompt with administrator privileges to display the call forwarding settings of a user in your deployment.</span></span>
    
    <span data-ttu-id="71e15-131">b.</span><span class="sxs-lookup"><span data-stu-id="71e15-131">b.</span></span> <span data-ttu-id="71e15-132">Exibir as configurações de encaminhamento de chamadas de um usuário.</span><span class="sxs-lookup"><span data-stu-id="71e15-132">Display the call forwarding settings of a user.</span></span> <span data-ttu-id="71e15-133">Na linha de comando, execute:</span><span class="sxs-lookup"><span data-stu-id="71e15-133">At the command line, run:</span></span>
    
   ```console
   SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
   ```

<span data-ttu-id="71e15-134">As configurações de encaminhamento de chamadas para o usuário serão exibidas.</span><span class="sxs-lookup"><span data-stu-id="71e15-134">The call forwarding settings for the user will be displayed.</span></span>
    

