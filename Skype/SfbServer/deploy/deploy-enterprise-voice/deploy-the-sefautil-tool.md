---
title: Implantar a ferramenta SEFAUtil no Skype for Business 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
description: Implantando a ferramenta de SEFAUtil em Skype para Business Server.
ms.openlocfilehash: 4def73d0bca655569275f61d9ebfeafb4ab7e3d4
ms.sourcegitcommit: b394b394e6c51fe0d75b1eec47f6ada1b0265b63
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/10/2018
---
# <a name="deploy-the-sefautil-tool-in-skype-for-business-2015"></a><span data-ttu-id="53f70-103">Implantar a ferramenta SEFAUtil no Skype for Business 2015</span><span class="sxs-lookup"><span data-stu-id="53f70-103">Deploy the SEFAUtil tool in Skype for Business 2015</span></span>
 
<span data-ttu-id="53f70-104">Implantando a ferramenta de SEFAUtil em Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="53f70-104">Deploying the SEFAUtil tool in Skype for Business Server.</span></span>
  
<span data-ttu-id="53f70-105">Para implantar e gerenciar o atendimento de chamada de grupo, você precisará usar o Skype para Business Server versão da ferramenta SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="53f70-105">To deploy and manage Group Call Pickup, you need to use the Skype for Business Server version of the SEFAUtil tool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="53f70-106">Tempo de execução do Microsoft Unified Communications Managed API (UCMA) 5 deve ser instalado em qualquer computador no qual você pretende executar a ferramenta SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="53f70-106">Microsoft Unified Communications Managed API (UCMA) 5 Runtime must be installed on any computer where you plan to run the SEFAUtil tool.</span></span> <span data-ttu-id="53f70-107">Baixá-lo aqui: [Unified Communications Managed API 5.0 Runtime](https://www.microsoft.com/en-us/download/details.aspx?id=47344).</span><span class="sxs-lookup"><span data-stu-id="53f70-107">Download it here: [Unified Communications Managed API 5.0 Runtime](https://www.microsoft.com/en-us/download/details.aspx?id=47344).</span></span> <span data-ttu-id="53f70-108">Você também pode baixar o SDK do UCMA 5, que inclui o tempo de execução, aqui: [UCMA 5.0 SDK](https://www.microsoft.com/en-us/download/details.aspx?id=47345).</span><span class="sxs-lookup"><span data-stu-id="53f70-108">You can also download the UCMA 5 SDK, which includes the runtime, here: [UCMA 5.0 SDK](https://www.microsoft.com/en-us/download/details.aspx?id=47345).</span></span>
  
<span data-ttu-id="53f70-109">Você pode executar a ferramenta de SEFAUtil em qualquer pool de Front-End em sua implantação.</span><span class="sxs-lookup"><span data-stu-id="53f70-109">You can run the SEFAUtil tool in any Front End pool in your deployment.</span></span> <span data-ttu-id="53f70-110">Para executar a ferramenta de SEFAUtil você deve executar as etapas 1, 2 e 3 do Skype para o Assistente de implantação de negócios no computador de aplicativos confiáveis.</span><span class="sxs-lookup"><span data-stu-id="53f70-110">To run the SEFAUtil tool you must run Steps 1, 2, and 3 from the Skype for Business Deployment Wizard on the Trusted Application Computer.</span></span> <span data-ttu-id="53f70-111">SEFAUtil requer o repositório de configuração local estar presentes, bem como um certificado.</span><span class="sxs-lookup"><span data-stu-id="53f70-111">SEFAUtil requires the local configuration store to be present, as well as a certificate.</span></span>
  
> [!NOTE]
> <span data-ttu-id="53f70-112">Para obter mais detalhes sobre como executar SEFAUtil, consulte o artigo do blog Technet "[como obter SEFAutil executando?](https://go.microsoft.com/fwlink/?LinkId=278940)".</span><span class="sxs-lookup"><span data-stu-id="53f70-112">For more details about running SEFAUtil, see the Technet blog article, "[How to get SEFAutil running?](https://go.microsoft.com/fwlink/?LinkId=278940)".</span></span> 
  
### <a name="to-deploy-sefautil"></a><span data-ttu-id="53f70-113">Para implantar a SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="53f70-113">To deploy SEFAUtil</span></span>

1. <span data-ttu-id="53f70-114">Faça logon no computador onde o Skype do Shell de gerenciamento do servidor de negócios está instalado como membro do grupo RTCUniversalServerAdmins ou com os direitos de usuário necessários, conforme descrito em **Delegate Setup Permissions**.</span><span class="sxs-lookup"><span data-stu-id="53f70-114">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="53f70-115">Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="53f70-115">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="53f70-116">A ferramenta SEFAUtil só pode ser executada em um computador que integra um pool de aplicativos confiáveis.</span><span class="sxs-lookup"><span data-stu-id="53f70-116">The SEFAUtil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="53f70-117">Se necessário, definir um pool de aplicativos confiáveis para o pool de Front-End no qual você pretende executar SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="53f70-117">If needed, define a trusted application pool for the Front End pool where you plan to run SEFAUtil.</span></span> <span data-ttu-id="53f70-118">Na linha de comando, execute:</span><span class="sxs-lookup"><span data-stu-id="53f70-118">At the command line, run:</span></span>
    
   ```
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```

4. <span data-ttu-id="53f70-p104">Defina a ferramenta SEFAUtil como um aplicativo confiável. Na linha de comando, execute:</span><span class="sxs-lookup"><span data-stu-id="53f70-p104">Define the SEFAUtil tool as a trusted application. At the command line, run:</span></span>
    
   ```
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
   ```

    > [!NOTE]
    > <span data-ttu-id="53f70-121">Se necessário, você pode usar uma porta diferente.</span><span class="sxs-lookup"><span data-stu-id="53f70-121">You can use a different port if needed.</span></span> 
  
5. <span data-ttu-id="53f70-p105">Habilite a topologia com suas alterações. Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="53f70-p105">Enable the topology with your changes. At the command line, run:</span></span>
    
  ```
  Enable-CsTopology
  ```

6. <span data-ttu-id="53f70-124">Se você ainda não estiver, baixe o Skype para Business Server versão da ferramenta SEFAUtil [nesse local](https://www.microsoft.com/en-us/download/details.aspx?id=52631)e instale-o em um pool de aplicativos confiáveis que você criou na etapa 3.</span><span class="sxs-lookup"><span data-stu-id="53f70-124">If you haven't already, download the Skype for Business Server version of the SEFAUtil tool from [this location](https://www.microsoft.com/en-us/download/details.aspx?id=52631), and install it on the trusted application pool you created in step 3.</span></span>
    
7. <span data-ttu-id="53f70-125">Verifique se a ferramenta SEFAUtil está sendo executada corretamente conforme segue:</span><span class="sxs-lookup"><span data-stu-id="53f70-125">Verify that the SEFAUtil tool is running correctly, as follows:</span></span> 
    
    <span data-ttu-id="53f70-126">a.</span><span class="sxs-lookup"><span data-stu-id="53f70-126">a.</span></span> <span data-ttu-id="53f70-127">Execute a ferramenta no prompt de comando do Windows com privilégios de administrador para exibir as configurações de encaminhamento de chamada de um usuário de sua implantação.</span><span class="sxs-lookup"><span data-stu-id="53f70-127">Run the tool from the Windows command prompt with administrator privileges to display the call forwarding settings of a user in your deployment.</span></span>
    
    <span data-ttu-id="53f70-128">b.</span><span class="sxs-lookup"><span data-stu-id="53f70-128">b.</span></span> <span data-ttu-id="53f70-129">Exiba as configurações de um usuário de encaminhamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="53f70-129">Display the call forwarding settings of a user.</span></span> <span data-ttu-id="53f70-130">Na linha de comando, execute:</span><span class="sxs-lookup"><span data-stu-id="53f70-130">At the command line, run:</span></span>
    
  ```
  SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
  ```

<span data-ttu-id="53f70-131">As configurações de encaminhamento de chamada do usuário serão exibidas.</span><span class="sxs-lookup"><span data-stu-id="53f70-131">The call forwarding settings for the user will be displayed.</span></span>
    

