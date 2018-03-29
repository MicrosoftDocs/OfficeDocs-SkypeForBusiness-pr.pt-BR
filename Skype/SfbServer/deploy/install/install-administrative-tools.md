---
title: Instalar as ferramentas administrativas no Skype for Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 7/14/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 52ee7da4-59ba-499a-a105-d93fa9941334
description: 'Resumo: Saiba como instalar as ferramentas administrativas necessárias para uma instalação do Skype para Business Server 2015. Baixe uma versão de avaliação gratuita do Skype para negócios 2015 de servidor do centro da Evaluation da Microsoft em: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: e54dfd4b29f3947b58517007949922a5c1230d51
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="install-administrative-tools-in-skype-for-business-server-2015"></a><span data-ttu-id="96c87-104">Instalar as ferramentas administrativas no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="96c87-104">Install administrative tools in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="96c87-105">**Resumo:** Saiba como instalar as ferramentas administrativas necessárias para uma instalação do Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="96c87-105">**Summary:** Learn how to install the administrative tools required for an installation of Skype for Business Server 2015.</span></span> <span data-ttu-id="96c87-106">Baixe uma versão de avaliação gratuita do Skype para negócios 2015 de servidor do centro da Evaluation da Microsoft em: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span><span class="sxs-lookup"><span data-stu-id="96c87-106">Download a free trial of Skype for Business Server 2015 from the Microsoft Evaluation center at: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="96c87-107">As ferramentas administrativas incluem o Construtor de Topologias e o Painel de Controle.</span><span class="sxs-lookup"><span data-stu-id="96c87-107">The administrative tools include Topology Builder and the Control Panel.</span></span> <span data-ttu-id="96c87-108">As ferramentas administrativas devem ser instaladas em pelo menos um servidor da topologia ou uma estação de trabalho de gerenciamento de 64 bits executando uma versão do sistema operacional Windows que é suportada para Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="96c87-108">The administrative tools must be installed on at least one server in the topology or a 64-bit management workstation running a Windows OS version that is supported for Skype for Business Server.</span></span> <span data-ttu-id="96c87-109">As etapas 1 a 5 podem ser executadas em qualquer ordem.</span><span class="sxs-lookup"><span data-stu-id="96c87-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="96c87-110">No entanto, você deve executar as etapas 6, 7 e 8 nesta ordem, após concluir as etapas 1 a 5, conforme descrito no diagrama.</span><span class="sxs-lookup"><span data-stu-id="96c87-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="96c87-111">A instalação das ferramentas administrativas é a etapa 3 de 8.</span><span class="sxs-lookup"><span data-stu-id="96c87-111">Installing the administrative tools is step 3 of 8.</span></span>
  
![Diagrama de visão geral](../../media/d856afe8-4758-432f-bc45-e1956016419a.png)
  
## <a name="install-skype-for-business-server-2015-administrative-tools"></a><span data-ttu-id="96c87-113">Instale o Skype para ferramentas administrativas do Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="96c87-113">Install Skype for Business Server 2015 administrative tools</span></span>

<span data-ttu-id="96c87-114">A mídia de instalação do Skype para Business Server 2015 fornece uma experiência flexível.</span><span class="sxs-lookup"><span data-stu-id="96c87-114">The installation media for Skype for Business Server 2015 provides a flexible experience.</span></span> <span data-ttu-id="96c87-115">Quando você executa o Setup.exe pela primeira vez, as ferramentas somente instaladas são o Skype para o Assistente de implantação de servidor de negócios e do Skype do Shell de gerenciamento do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="96c87-115">When you first run Setup.exe, the only tools installed are the Skype for Business Server Deployment Wizard and the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="96c87-116">Usando essas duas ferramentas, conhecidas como componentes principais, você pode continuar com o processo de instalação, mas não fornecem funcionalidade principal para o Skype geral para ambiente de servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="96c87-116">By using these two tools, known as Core Components, you can continue with the installation process, but they do not provide primary functionality for the overall Skype for Business Server environment.</span></span> <span data-ttu-id="96c87-117">O Assistente de Implantação é iniciado automaticamente após a instalação dos Componentes Básicos.</span><span class="sxs-lookup"><span data-stu-id="96c87-117">The Deployment Wizard launches automatically after you install the Core Components.</span></span> <span data-ttu-id="96c87-118">A seção do Assistente para implantação intitulada **Instalar as ferramentas administrativas** instala Skype para o construtor de topologia de servidor de negócios e Skype para painel de controle do Business Server.</span><span class="sxs-lookup"><span data-stu-id="96c87-118">The section of the Deployment Wizard titled **Install Administrative Tools** installs Skype for Business Server Topology Builder and Skype for Business Server Control Panel.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="96c87-119">Cada Skype para ambiente de negócios servidor deve ter pelo menos um servidor com as ferramentas administrativas instaladas.</span><span class="sxs-lookup"><span data-stu-id="96c87-119">Every Skype for Business Server environment must have at least one server with the administrative tools installed.</span></span> 
  
<span data-ttu-id="96c87-120">Veja as etapas do vídeo para **instalar ferramentas administrativas**:</span><span class="sxs-lookup"><span data-stu-id="96c87-120">Watch the video steps for **Install administrative tools**:</span></span>
  
![Seu navegador não oferece suporte a vídeo. Instale o Microsoft Silverlight, o Adobe Flash Player ou o Internet Explorer 9.](../../media/MSN_Video_Widget.gif)
  
### <a name="install-skype-for-business-server-2015-administrative-tools-from-the-deployment-wizard"></a><span data-ttu-id="96c87-123">Instale o Skype para ferramentas administrativas do Business Server 2015 Assistente de implantação</span><span class="sxs-lookup"><span data-stu-id="96c87-123">Install Skype for Business Server 2015 administrative tools from the Deployment Wizard</span></span>

1. <span data-ttu-id="96c87-124">Insira o Skype para a mídia de instalação do Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="96c87-124">Insert the Skype for Business Server 2015 installation media.</span></span> <span data-ttu-id="96c87-125">Se a instalação não começar automaticamente, clique duas vezes em **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="96c87-125">If the setup does not automatically begin, double-click **Setup**.</span></span>
    
2. <span data-ttu-id="96c87-p107">A mídia de instalação requer o Microsoft Visual C++ para ser executada. Uma caixa de diálogo aparecerá perguntando se você quer instalá-lo. Clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="96c87-p107">The installation media requires Microsoft Visual C++ to run. A dialog box will pop up asking if you want to install it. Click **Yes**.</span></span>
    
3. <span data-ttu-id="96c87-129">Usando a instalação inteligente, um novo recurso do Skype para negócios 2015 do servidor, você pode se conectar à Internet para verificar se há atualizações durante o processo de instalação.</span><span class="sxs-lookup"><span data-stu-id="96c87-129">By using Smart Setup, a new feature in Skype for Business Server 2015, you can connect to the Internet to check for updates during the installation process.</span></span> <span data-ttu-id="96c87-130">Este recurso proporciona uma experiência aprimorada ao assegurar que você tenha as atualizações mais recentes do produto.</span><span class="sxs-lookup"><span data-stu-id="96c87-130">This provides a better experience by making sure you have the most recent updates to the product at installation.</span></span> <span data-ttu-id="96c87-131">Clique em **Instalar** para começar a instalação.</span><span class="sxs-lookup"><span data-stu-id="96c87-131">Click **Install** to begin the installation.</span></span>
    
4. <span data-ttu-id="96c87-132">Leia com atenção o Contrato de Licença e se você estiver de acordo, selecione **Aceito os termos do contrato de licença** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="96c87-132">Carefully review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and click **OK**.</span></span>
    
5. <span data-ttu-id="96c87-133">O Skype para componentes principais do Business Server 2015 será instalado no servidor.</span><span class="sxs-lookup"><span data-stu-id="96c87-133">The Skype for Business Server 2015 Core Components will be installed on the server.</span></span> 
    
    <span data-ttu-id="96c87-134">Os Componentes consistem nos itens a seguir, como mostra a figura.</span><span class="sxs-lookup"><span data-stu-id="96c87-134">The Core Components consist of the following, as shown in the figure.</span></span>
    
    ![Componentes Principais na tela de aplicativos.](../../media/0da1d983-4c4b-4b23-a196-c3bdba4857c6.png)
  
  - <span data-ttu-id="96c87-136">**Skype para o Assistente de implantação de 2015 Business Server** Um programa de implantação que fornece um ponto de partida para instalar os vários componentes do Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="96c87-136">**Skype for Business Server 2015 Deployment Wizard** A deployment program that provides a launch pad for installing the various components of Skype for Business Server 2015.</span></span>
    
  - <span data-ttu-id="96c87-137">**Skype para Business Server 2015 Management Shell** Um programa PowerShell pré-configurado que permita a administração do Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="96c87-137">**Skype for Business Server 2015 Management Shell** A preconfigured PowerShell program that allows for administration of Skype for Business Server 2015.</span></span>
    
    <span data-ttu-id="96c87-138">Uma vez concluída a instalação dos componentes principais, o Skype para o Assistente de implantação do Business Server 2015 iniciará automaticamente, conforme mostrado na figura.</span><span class="sxs-lookup"><span data-stu-id="96c87-138">Once the installation of the Core Components is complete, the Skype for Business Server 2015 Deployment Wizard will automatically launch, as shown in the figure.</span></span> 
    
    ![Assistente de Implantação do Skype for Business Server 2015](../../media/310c3437-83f9-48fa-a1e1-9fd09009fe31.png)
  
6. <span data-ttu-id="96c87-140">Além dos componentes principais, você também precisará instalar o Skype para o construtor de topologias do Business Server 2015 e Skype para painel de controle do Business Server 2015 em pelo menos um servidor no ambiente.</span><span class="sxs-lookup"><span data-stu-id="96c87-140">In addition to the Core Components, you will also need to install Skype for Business Server 2015 Topology Builder and Skype for Business Server 2015 Control Panel on at least one server in the environment.</span></span> <span data-ttu-id="96c87-141">Clique em **Instalar ferramentas administrativas** no Assistente de Implantação.</span><span class="sxs-lookup"><span data-stu-id="96c87-141">Click **Install Administrative Tools** on the Deployment Wizard.</span></span>
    
7. <span data-ttu-id="96c87-142">Clique em **Avançar** para começar a instalação.</span><span class="sxs-lookup"><span data-stu-id="96c87-142">Click **Next** to begin the installation.</span></span>
    
8. <span data-ttu-id="96c87-p110">Assim que a instalação for concluída, clique em **Concluir**. As ferramentas administrativas agora são adicionadas ao servidor, conforme mostra a figura.</span><span class="sxs-lookup"><span data-stu-id="96c87-p110">Once the installation has completed, click **Finish**. The administrative tools are now added to the server, as shown in the figure.</span></span>
    
    ![Ferramentas Administrativas do Skype for Business Server 2015](../../media/760873dd-9c87-4efb-bf98-7162d876fd18.png)
  
   - <span data-ttu-id="96c87-146">**Skype para o construtor de topologias 2015 Business Server** Um programa usado para criar, implantar e gerenciar as topologias.</span><span class="sxs-lookup"><span data-stu-id="96c87-146">**Skype for Business Server 2015 Topology Builder** A program used to build, deploy, and manage topologies.</span></span>
    
   - <span data-ttu-id="96c87-147">**Skype para painel de controle Business Server 2015** Um programa pode usado para administrar a instalação.</span><span class="sxs-lookup"><span data-stu-id="96c87-147">**Skype for Business Server 2015 Control Panel** A program used to administer the installation.</span></span>
    

