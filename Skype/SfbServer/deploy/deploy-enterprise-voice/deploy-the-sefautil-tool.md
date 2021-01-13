---
title: Implantar a ferramenta SEFAUtil no Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Implantação da ferramenta SEFAUtil no Skype for Business Server.
ms.openlocfilehash: 20cda161c182c8dfb426f61b793366b7f60f37d5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812381"
---
# <a name="deploy-the-sefautil-tool-in-skype-for-business"></a><span data-ttu-id="c44fe-103">Implantar a ferramenta SEFAUtil no Skype for Business</span><span class="sxs-lookup"><span data-stu-id="c44fe-103">Deploy the SEFAUtil tool in Skype for Business</span></span>
 
<span data-ttu-id="c44fe-104">Implantação da ferramenta SEFAUtil no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c44fe-104">Deploying the SEFAUtil tool in Skype for Business Server.</span></span>
  
<span data-ttu-id="c44fe-105">Para implantar e gerenciar o Atendimento de Chamadas em Grupo, você precisa usar a versão do Skype for Business Server da ferramenta SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="c44fe-105">To deploy and manage Group Call Pickup, you need to use the Skype for Business Server version of the SEFAUtil tool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="c44fe-106">O Microsoft Unified Communications Managed API (UCMA) 5 Runtime deve ser instalado em qualquer computador em que você planeje executar a ferramenta SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="c44fe-106">Microsoft Unified Communications Managed API (UCMA) 5 Runtime must be installed on any computer where you plan to run the SEFAUtil tool.</span></span> <span data-ttu-id="c44fe-107">Baixe-o aqui: [Unified Communications Managed API 5.0 Runtime](https://www.microsoft.com/download/details.aspx?id=47344).</span><span class="sxs-lookup"><span data-stu-id="c44fe-107">Download it here: [Unified Communications Managed API 5.0 Runtime](https://www.microsoft.com/download/details.aspx?id=47344).</span></span> <span data-ttu-id="c44fe-108">Você também pode baixar o UCMA 5 SDK, que inclui o tempo de execução, aqui: [UCMA 5.0 SDK](https://www.microsoft.com/download/details.aspx?id=47345).</span><span class="sxs-lookup"><span data-stu-id="c44fe-108">You can also download the UCMA 5 SDK, which includes the runtime, here: [UCMA 5.0 SDK](https://www.microsoft.com/download/details.aspx?id=47345).</span></span>
  
<span data-ttu-id="c44fe-109">Você pode executar a ferramenta SEFAUtil em qualquer pool de Front-End em sua implantação.</span><span class="sxs-lookup"><span data-stu-id="c44fe-109">You can run the SEFAUtil tool in any Front End pool in your deployment.</span></span> <span data-ttu-id="c44fe-110">Para executar a ferramenta SEFAUtil, você deve executar as Etapas 1, 2 e 3 do Assistente de Implantação do Skype for Business no Computador de Aplicativo Confiável.</span><span class="sxs-lookup"><span data-stu-id="c44fe-110">To run the SEFAUtil tool you must run Steps 1, 2, and 3 from the Skype for Business Deployment Wizard on the Trusted Application Computer.</span></span> <span data-ttu-id="c44fe-111">A SEFAUtil exige que o armazenamento de configuração local seja presente, bem como um certificado.</span><span class="sxs-lookup"><span data-stu-id="c44fe-111">SEFAUtil requires the local configuration store to be present, as well as a certificate.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c44fe-112">Para obter mais detalhes sobre como executar a SEFAUtil, consulte o artigo do blog , "[Como obter SEFAutil em execução?](https://go.microsoft.com/fwlink/?LinkId=278940)".</span><span class="sxs-lookup"><span data-stu-id="c44fe-112">For more details about running SEFAUtil, see the  blog article, "[How to get SEFAutil running?](https://go.microsoft.com/fwlink/?LinkId=278940)".</span></span> 
  
### <a name="to-deploy-sefautil"></a><span data-ttu-id="c44fe-113">Para implantar a SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="c44fe-113">To deploy SEFAUtil</span></span>

1. <span data-ttu-id="c44fe-114">Faça logoff no computador onde o Shell de Gerenciamento do Skype for Business Server está instalado como membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário **necessários,** conforme descrito em Delegate Setup Permissions .</span><span class="sxs-lookup"><span data-stu-id="c44fe-114">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="c44fe-115">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar,** em Todos os **Programas,** no **Skype for Business 2015** e, em seguida, clique no Shell de Gerenciamento do **Skype for Business Server.**</span><span class="sxs-lookup"><span data-stu-id="c44fe-115">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="c44fe-116">A ferramenta SEFAUtil pode ser executado somente em um computador que faz parte de um pool de aplicativos confiáveis.</span><span class="sxs-lookup"><span data-stu-id="c44fe-116">The SEFAUtil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="c44fe-117">Se necessário, defina um pool de aplicativos confiáveis para o pool de Front-End onde você planeja executar SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="c44fe-117">If needed, define a trusted application pool for the Front End pool where you plan to run SEFAUtil.</span></span> <span data-ttu-id="c44fe-118">Na linha de comando, execute:</span><span class="sxs-lookup"><span data-stu-id="c44fe-118">At the command line, run:</span></span>
    
   ```powershell
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```
    > [!NOTE]
    > <span data-ttu-id="c44fe-119">FQDN do pool: O FQDN do servidor ou pool que hospedará o aplicativo SEFAUtil (geralmente um pool ou servidor front-end do Skype for Business).</span><span class="sxs-lookup"><span data-stu-id="c44fe-119">Pool FQDN: The FQDN of the server or pool that will host the SEFAUtil application (usually a Skype for Business Front End server or pool).</span></span>
    > <span data-ttu-id="c44fe-120">FQDN do Registrador de Pool: O FQDN do servidor front-end do Skype for Business ou pool associado a este pool de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="c44fe-120">Pool Registrar FQDN: The FQDN of the Skype for Business Front End server or pool associated with this application pool.</span></span>
    > <span data-ttu-id="c44fe-121">Site do Pool: A ID do Site do site no qual este pool está.</span><span class="sxs-lookup"><span data-stu-id="c44fe-121">Pool Site: The Site ID of the site on which this pool is homed.</span></span>

4. <span data-ttu-id="c44fe-122">Defina a ferramenta SEFAUtil como um aplicativo confiável.</span><span class="sxs-lookup"><span data-stu-id="c44fe-122">Define the SEFAUtil tool as a trusted application.</span></span> <span data-ttu-id="c44fe-123">Na linha de comando, execute:</span><span class="sxs-lookup"><span data-stu-id="c44fe-123">At the command line, run:</span></span>
    
   ```powershell
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
   ```

    > [!NOTE]
    > <span data-ttu-id="c44fe-124">Você pode usar uma porta diferente, se necessário.</span><span class="sxs-lookup"><span data-stu-id="c44fe-124">You can use a different port if needed.</span></span> 
  
5. <span data-ttu-id="c44fe-125">Habilita a topologia com suas alterações.</span><span class="sxs-lookup"><span data-stu-id="c44fe-125">Enable the topology with your changes.</span></span> <span data-ttu-id="c44fe-126">Na linha de comando, execute:</span><span class="sxs-lookup"><span data-stu-id="c44fe-126">At the command line, run:</span></span>
    
   ```powershell
   Enable-CsTopology
   ```

6. <span data-ttu-id="c44fe-127">Caso ainda não tenha feito isso, baixe a versão do [](https://www.microsoft.com/download/details.aspx?id=52631)Skype for Business Server da ferramenta SEFAUtil deste local e instale-a no pool de aplicativos confiáveis criado na etapa 3.</span><span class="sxs-lookup"><span data-stu-id="c44fe-127">If you haven't already, download the Skype for Business Server version of the SEFAUtil tool from [this location](https://www.microsoft.com/download/details.aspx?id=52631), and install it on the trusted application pool you created in step 3.</span></span>
    
7. <span data-ttu-id="c44fe-128">Verifique se a ferramenta SEFAUtil está sendo executado corretamente, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="c44fe-128">Verify that the SEFAUtil tool is running correctly, as follows:</span></span> 
    
    <span data-ttu-id="c44fe-129">a.</span><span class="sxs-lookup"><span data-stu-id="c44fe-129">a.</span></span> <span data-ttu-id="c44fe-130">Execute a ferramenta no prompt de comando do Windows com privilégios de administrador para exibir as configurações de encaminhamento de chamada de um usuário em sua implantação.</span><span class="sxs-lookup"><span data-stu-id="c44fe-130">Run the tool from the Windows command prompt with administrator privileges to display the call forwarding settings of a user in your deployment.</span></span>
    
    <span data-ttu-id="c44fe-131">b.</span><span class="sxs-lookup"><span data-stu-id="c44fe-131">b.</span></span> <span data-ttu-id="c44fe-132">Exibe as configurações de encaminhamento de chamada de um usuário.</span><span class="sxs-lookup"><span data-stu-id="c44fe-132">Display the call forwarding settings of a user.</span></span> <span data-ttu-id="c44fe-133">Na linha de comando, execute:</span><span class="sxs-lookup"><span data-stu-id="c44fe-133">At the command line, run:</span></span>
    
   ```console
   SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
   ```

<span data-ttu-id="c44fe-134">As configurações de encaminhamento de chamada do usuário serão exibidas.</span><span class="sxs-lookup"><span data-stu-id="c44fe-134">The call forwarding settings for the user will be displayed.</span></span>
    

