---
title: Instalar ferramentas administrativas no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/14/2018
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
ms.assetid: 52ee7da4-59ba-499a-a105-d93fa9941334
description: 'Resumo: saiba como instalar as ferramentas administrativas necessárias para uma instalação do Skype for Business Server. Baixe uma avaliação gratuita do Skype for Business Server no Centro de Avaliação da Microsoft em: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server .'
ms.openlocfilehash: ab3e64ae5d330c5b24eff7c23172b1141ff75527
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812101"
---
# <a name="install-administrative-tools-in-skype-for-business-server"></a><span data-ttu-id="729f4-104">Instalar ferramentas administrativas no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="729f4-104">Install administrative tools in Skype for Business Server</span></span>
 
<span data-ttu-id="729f4-105">**Resumo:** Saiba como instalar as ferramentas administrativas necessárias para uma instalação do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="729f4-105">**Summary:** Learn how to install the administrative tools required for an installation of Skype for Business Server.</span></span> <span data-ttu-id="729f4-106">Baixe uma avaliação gratuita do Skype for Business Server no Centro de Avaliação da Microsoft em: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server) .</span><span class="sxs-lookup"><span data-stu-id="729f4-106">Download a free trial of Skype for Business Server from the Microsoft Evaluation center at: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="729f4-107">As ferramentas administrativas incluem o Construtor de Topologias e o Painel de Controle.</span><span class="sxs-lookup"><span data-stu-id="729f4-107">The administrative tools include Topology Builder and the Control Panel.</span></span> <span data-ttu-id="729f4-108">As ferramentas administrativas devem ser instaladas em pelo menos um servidor na topologia ou em uma estação de trabalho de gerenciamento de 64 bits executando uma versão do sistema operacional Windows com suporte para o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="729f4-108">The administrative tools must be installed on at least one server in the topology or a 64-bit management workstation running a Windows OS version that is supported for Skype for Business Server.</span></span> <span data-ttu-id="729f4-109">Você pode realizar as etapas 1 a 5 em qualquer ordem.</span><span class="sxs-lookup"><span data-stu-id="729f4-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="729f4-110">No entanto, você deve realizar as etapas 6, 7 e 8 na ordem e após as etapas de 1 a 5, conforme descrito no diagrama.</span><span class="sxs-lookup"><span data-stu-id="729f4-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="729f4-111">Instalar as ferramentas administrativas é a etapa 3 de 8.</span><span class="sxs-lookup"><span data-stu-id="729f4-111">Installing the administrative tools is step 3 of 8.</span></span>
  
![Diagrama de visão geral](../../media/d856afe8-4758-432f-bc45-e1956016419a.png)
  
## <a name="install-skype-for-business-server-administrative-tools"></a><span data-ttu-id="729f4-113">Instalar ferramentas administrativas do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="729f4-113">Install Skype for Business Server administrative tools</span></span>

<span data-ttu-id="729f4-114">A mídia de instalação do Skype for Business Server oferece uma experiência flexível.</span><span class="sxs-lookup"><span data-stu-id="729f4-114">The installation media for Skype for Business Server provides a flexible experience.</span></span> <span data-ttu-id="729f4-115">Quando você executar o Setup.exe, as únicas ferramentas instaladas serão o Assistente de Implantação do Skype for Business Server e o Shell de Gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="729f4-115">When you first run Setup.exe, the only tools installed are the Skype for Business Server Deployment Wizard and the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="729f4-116">Usando essas duas ferramentas, conhecidas como Componentes Principais, você pode continuar com o processo de instalação, mas elas não fornecem a funcionalidade principal para o ambiente geral do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="729f4-116">By using these two tools, known as Core Components, you can continue with the installation process, but they do not provide primary functionality for the overall Skype for Business Server environment.</span></span> <span data-ttu-id="729f4-117">O Assistente de Implantação é lançado automaticamente após a instalação dos Componentes Principais.</span><span class="sxs-lookup"><span data-stu-id="729f4-117">The Deployment Wizard launches automatically after you install the Core Components.</span></span> <span data-ttu-id="729f4-118">A seção do Assistente  de Implantação intitulada Instalar Ferramentas Administrativas instala o Construtor de Topologias do Skype for Business Server e o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="729f4-118">The section of the Deployment Wizard titled **Install Administrative Tools** installs Skype for Business Server Topology Builder and Skype for Business Server Control Panel.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="729f4-119">Cada ambiente do Skype for Business Server deve ter pelo menos um servidor com as ferramentas administrativas instaladas.</span><span class="sxs-lookup"><span data-stu-id="729f4-119">Every Skype for Business Server environment must have at least one server with the administrative tools installed.</span></span> 
  
<span data-ttu-id="729f4-120">Assista às etapas de vídeo para **Instalar ferramentas administrativas:**</span><span class="sxs-lookup"><span data-stu-id="729f4-120">Watch the video steps for **Install administrative tools**:</span></span>
  
> [!video https://www.microsoft.com/videoplayer/embed/99a5c436-963b-4eed-b423-651568c87cb1?autoplay=false]
  
### <a name="install-skype-for-business-server-administrative-tools-from-the-deployment-wizard"></a><span data-ttu-id="729f4-121">Instalar ferramentas administrativas do Skype for Business Server a partir do Assistente de Implantação</span><span class="sxs-lookup"><span data-stu-id="729f4-121">Install Skype for Business Server administrative tools from the Deployment Wizard</span></span>

1. <span data-ttu-id="729f4-122">Insira a mídia de instalação do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="729f4-122">Insert the Skype for Business Server installation media.</span></span> <span data-ttu-id="729f4-123">Se a instalação não começar automaticamente, clique duas vezes em **Setup**.</span><span class="sxs-lookup"><span data-stu-id="729f4-123">If the setup does not automatically begin, double-click **Setup**.</span></span>
    
2. <span data-ttu-id="729f4-124">A mídia de instalação requer o Microsoft Visual C++ para ser executado.</span><span class="sxs-lookup"><span data-stu-id="729f4-124">The installation media requires Microsoft Visual C++ to run.</span></span> <span data-ttu-id="729f4-125">Uma caixa de diálogo será exibida perguntando se você deseja instalá-la.</span><span class="sxs-lookup"><span data-stu-id="729f4-125">A dialog box will pop up asking if you want to install it.</span></span> <span data-ttu-id="729f4-126">Clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="729f4-126">Click **Yes**.</span></span>
    
3. <span data-ttu-id="729f4-127">Usando a Instalação Inteligente, um novo recurso no Skype for Business Server, você pode se conectar à Internet para verificar se há atualizações durante o processo de instalação.</span><span class="sxs-lookup"><span data-stu-id="729f4-127">By using Smart Setup, a new feature in Skype for Business Server, you can connect to the Internet to check for updates during the installation process.</span></span> <span data-ttu-id="729f4-128">Isso proporciona uma experiência melhor ao garantir que você tenha as atualizações mais recentes do produto na instalação.</span><span class="sxs-lookup"><span data-stu-id="729f4-128">This provides a better experience by making sure you have the most recent updates to the product at installation.</span></span> <span data-ttu-id="729f4-129">Clique em **Instalar** para iniciar a instalação.</span><span class="sxs-lookup"><span data-stu-id="729f4-129">Click **Install** to begin the installation.</span></span>
    
4. <span data-ttu-id="729f4-130">Revise cuidadosamente o Contrato de Licença e, se você concordar, selecione **Eu aceito** os termos do contrato de licença e clique em **OK.**</span><span class="sxs-lookup"><span data-stu-id="729f4-130">Carefully review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and click **OK**.</span></span>
    
5. <span data-ttu-id="729f4-131">Os componentes principais do Skype for Business Server serão instalados no servidor.</span><span class="sxs-lookup"><span data-stu-id="729f4-131">The Skype for Business Server Core Components will be installed on the server.</span></span> 
    
    <span data-ttu-id="729f4-132">Os Componentes Principais consistem no seguinte, conforme mostrado na figura.</span><span class="sxs-lookup"><span data-stu-id="729f4-132">The Core Components consist of the following, as shown in the figure.</span></span>
    
    ![Componentes principais na tela Aplicativos.](../../media/0da1d983-4c4b-4b23-a196-c3bdba4857c6.png)
  
   - <span data-ttu-id="729f4-134">**Assistente de Implantação do Skype for Business Server** Um programa de implantação que fornece um painel de lançamento para instalar os vários componentes do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="729f4-134">**Skype for Business Server Deployment Wizard** A deployment program that provides a launch pad for installing the various components of Skype for Business Server.</span></span>
    
   - <span data-ttu-id="729f4-135">**Shell de Gerenciamento do Skype for Business Server** Um programa do PowerShell pré-configurado que permite a administração do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="729f4-135">**Skype for Business Server Management Shell** A preconfigured PowerShell program that allows for administration of Skype for Business Server.</span></span>
    
     <span data-ttu-id="729f4-136">Quando a instalação dos Componentes Principais for concluída, o Assistente de Implantação do Skype for Business Server será automaticamente lançado, conforme mostrado na figura.</span><span class="sxs-lookup"><span data-stu-id="729f4-136">Once the installation of the Core Components is complete, the Skype for Business Server Deployment Wizard will automatically launch, as shown in the figure.</span></span> 
    
     ![Assistente de Implantação do Skype for Business Server](../../media/310c3437-83f9-48fa-a1e1-9fd09009fe31.png)
  
6. <span data-ttu-id="729f4-138">Além dos Componentes Principais, você também precisará instalar o Construtor de Topologias do Skype for Business Server e o Painel de Controle do Skype for Business Server em pelo menos um servidor no ambiente.</span><span class="sxs-lookup"><span data-stu-id="729f4-138">In addition to the Core Components, you will also need to install Skype for Business Server Topology Builder and Skype for Business Server Control Panel on at least one server in the environment.</span></span> <span data-ttu-id="729f4-139">Clique **em Instalar Ferramentas Administrativas** no Assistente de Implantação.</span><span class="sxs-lookup"><span data-stu-id="729f4-139">Click **Install Administrative Tools** on the Deployment Wizard.</span></span>
    
7. <span data-ttu-id="729f4-140">Clique em **Avançar** para iniciar a instalação.</span><span class="sxs-lookup"><span data-stu-id="729f4-140">Click **Next** to begin the installation.</span></span>
    
8. <span data-ttu-id="729f4-141">Depois que a instalação tiver sido concluída, clique em **Concluir.**</span><span class="sxs-lookup"><span data-stu-id="729f4-141">Once the installation has completed, click **Finish**.</span></span> <span data-ttu-id="729f4-142">As ferramentas administrativas agora são adicionadas ao servidor, conforme mostrado na figura.</span><span class="sxs-lookup"><span data-stu-id="729f4-142">The administrative tools are now added to the server, as shown in the figure.</span></span>
    
    ![Ferramentas administrativas do Skype for Business Server](../../media/760873dd-9c87-4efb-bf98-7162d876fd18.png)
  
   - <span data-ttu-id="729f4-144">**Construtor de Topologias do Skype for Business Server** Um programa usado para criar, implantar e gerenciar topologias.</span><span class="sxs-lookup"><span data-stu-id="729f4-144">**Skype for Business Server Topology Builder** A program used to build, deploy, and manage topologies.</span></span>
    
   - <span data-ttu-id="729f4-145">**Painel de Controle do Skype for Business Server** Um programa usado para administrar a instalação.</span><span class="sxs-lookup"><span data-stu-id="729f4-145">**Skype for Business Server Control Panel** A program used to administer the installation.</span></span>
    

