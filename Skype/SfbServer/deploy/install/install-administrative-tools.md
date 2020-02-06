---
title: Instalar ferramentas administrativas no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 'Resumo: saiba como instalar as ferramentas administrativas necessárias para uma instalação do Skype for Business Server. Baixe um teste grátis do Skype for Business Server no centro de avaliação da Microsoft em https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server:.'
ms.openlocfilehash: 3abf2eb35a4593f25db75e175f3cd30fdf49e21b
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41790169"
---
# <a name="install-administrative-tools-in-skype-for-business-server"></a><span data-ttu-id="b7ea8-104">Instalar ferramentas administrativas no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="b7ea8-104">Install administrative tools in Skype for Business Server</span></span>
 
<span data-ttu-id="b7ea8-105">**Resumo:** Saiba como instalar as ferramentas administrativas necessárias para uma instalação do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="b7ea8-105">**Summary:** Learn how to install the administrative tools required for an installation of Skype for Business Server.</span></span> <span data-ttu-id="b7ea8-106">Baixe um teste grátis do Skype for Business Server no centro de avaliação da Microsoft em [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server):.</span><span class="sxs-lookup"><span data-stu-id="b7ea8-106">Download a free trial of Skype for Business Server from the Microsoft Evaluation center at: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="b7ea8-107">As ferramentas administrativas incluem o Construtor de Topologias e o Painel de Controle.</span><span class="sxs-lookup"><span data-stu-id="b7ea8-107">The administrative tools include Topology Builder and the Control Panel.</span></span> <span data-ttu-id="b7ea8-108">As ferramentas administrativas devem ser instaladas em pelo menos um servidor na topologia ou em uma estação de trabalho de gerenciamento de 64 executando uma versão do sistema operacional do Windows que seja compatível com o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="b7ea8-108">The administrative tools must be installed on at least one server in the topology or a 64-bit management workstation running a Windows OS version that is supported for Skype for Business Server.</span></span> <span data-ttu-id="b7ea8-109">Você pode executar os passos 1 a 5 em qualquer ordem.</span><span class="sxs-lookup"><span data-stu-id="b7ea8-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="b7ea8-110">No entanto, você deve executar as etapas 6, 7 e 8 nesta ordem, após concluir as etapas 1 a 5, conforme descrito no diagrama.</span><span class="sxs-lookup"><span data-stu-id="b7ea8-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="b7ea8-111">A instalação das ferramentas administrativas é a etapa 3 de 8.</span><span class="sxs-lookup"><span data-stu-id="b7ea8-111">Installing the administrative tools is step 3 of 8.</span></span>
  
![Diagrama de visão geral](../../media/d856afe8-4758-432f-bc45-e1956016419a.png)
  
## <a name="install-skype-for-business-server-administrative-tools"></a><span data-ttu-id="b7ea8-113">Instalar as ferramentas administrativas do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="b7ea8-113">Install Skype for Business Server administrative tools</span></span>

<span data-ttu-id="b7ea8-114">A mídia de instalação do Skype for Business Server oferece uma experiência flexível.</span><span class="sxs-lookup"><span data-stu-id="b7ea8-114">The installation media for Skype for Business Server provides a flexible experience.</span></span> <span data-ttu-id="b7ea8-115">Quando você executa o setup. exe pela primeira vez, as únicas ferramentas instaladas são o assistente de implantação do Skype for Business Server e o Shell de gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="b7ea8-115">When you first run Setup.exe, the only tools installed are the Skype for Business Server Deployment Wizard and the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="b7ea8-116">Ao usar essas duas ferramentas, conhecida como componentes principais, você pode continuar com o processo de instalação, mas elas não oferecem a funcionalidade principal para o ambiente geral do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="b7ea8-116">By using these two tools, known as Core Components, you can continue with the installation process, but they do not provide primary functionality for the overall Skype for Business Server environment.</span></span> <span data-ttu-id="b7ea8-117">O Assistente de Implantação é iniciado automaticamente após a instalação dos Componentes Básicos.</span><span class="sxs-lookup"><span data-stu-id="b7ea8-117">The Deployment Wizard launches automatically after you install the Core Components.</span></span> <span data-ttu-id="b7ea8-118">A seção do assistente de implantação intitulado **instalar ferramentas administrativas** instala o construtor de topologias do Skype for Business Server e o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="b7ea8-118">The section of the Deployment Wizard titled **Install Administrative Tools** installs Skype for Business Server Topology Builder and Skype for Business Server Control Panel.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="b7ea8-119">Cada ambiente do Skype for Business Server deve ter pelo menos um servidor com as ferramentas administrativas instaladas.</span><span class="sxs-lookup"><span data-stu-id="b7ea8-119">Every Skype for Business Server environment must have at least one server with the administrative tools installed.</span></span> 
  
<span data-ttu-id="b7ea8-120">Veja as etapas do vídeo para **instalar ferramentas administrativas**:</span><span class="sxs-lookup"><span data-stu-id="b7ea8-120">Watch the video steps for **Install administrative tools**:</span></span>
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/99a5c436-963b-4eed-b423-651568c87cb1?autoplay=false]
  
### <a name="install-skype-for-business-server-administrative-tools-from-the-deployment-wizard"></a><span data-ttu-id="b7ea8-121">Instalar as ferramentas administrativas do Skype for Business Server pelo assistente de implantação</span><span class="sxs-lookup"><span data-stu-id="b7ea8-121">Install Skype for Business Server administrative tools from the Deployment Wizard</span></span>

1. <span data-ttu-id="b7ea8-122">Insira a mídia de instalação do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="b7ea8-122">Insert the Skype for Business Server installation media.</span></span> <span data-ttu-id="b7ea8-123">Se a instalação não começar automaticamente, clique duas vezes em **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="b7ea8-123">If the setup does not automatically begin, double-click **Setup**.</span></span>
    
2. <span data-ttu-id="b7ea8-p106">A mídia de instalação requer o Microsoft Visual C++ para ser executada. Uma caixa de diálogo aparecerá perguntando se você quer instalá-lo. Clique em **Sim**.</span><span class="sxs-lookup"><span data-stu-id="b7ea8-p106">The installation media requires Microsoft Visual C++ to run. A dialog box will pop up asking if you want to install it. Click **Yes**.</span></span>
    
3. <span data-ttu-id="b7ea8-127">Ao usar a configuração inteligente, um novo recurso no Skype for Business Server, você pode se conectar à Internet para verificar se há atualizações durante o processo de instalação.</span><span class="sxs-lookup"><span data-stu-id="b7ea8-127">By using Smart Setup, a new feature in Skype for Business Server, you can connect to the Internet to check for updates during the installation process.</span></span> <span data-ttu-id="b7ea8-128">Este recurso proporciona uma experiência aprimorada ao assegurar que você tenha as atualizações mais recentes do produto.</span><span class="sxs-lookup"><span data-stu-id="b7ea8-128">This provides a better experience by making sure you have the most recent updates to the product at installation.</span></span> <span data-ttu-id="b7ea8-129">Clique em **Instalar** para começar a instalação.</span><span class="sxs-lookup"><span data-stu-id="b7ea8-129">Click **Install** to begin the installation.</span></span>
    
4. <span data-ttu-id="b7ea8-130">Leia com atenção o Contrato de Licença e se você estiver de acordo, selecione **Aceito os termos do contrato de licença** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="b7ea8-130">Carefully review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and click **OK**.</span></span>
    
5. <span data-ttu-id="b7ea8-131">Os componentes principais do Skype for Business Server serão instalados no servidor.</span><span class="sxs-lookup"><span data-stu-id="b7ea8-131">The Skype for Business Server Core Components will be installed on the server.</span></span> 
    
    <span data-ttu-id="b7ea8-132">Os Componentes consistem nos itens a seguir, como mostra a figura.</span><span class="sxs-lookup"><span data-stu-id="b7ea8-132">The Core Components consist of the following, as shown in the figure.</span></span>
    
    ![Componentes Principais na tela de aplicativos.](../../media/0da1d983-4c4b-4b23-a196-c3bdba4857c6.png)
  
   - <span data-ttu-id="b7ea8-134">**Assistente de implantação do Skype for Business Server** Um programa de implantação que fornece um bloco de inicialização para a instalação de vários componentes do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="b7ea8-134">**Skype for Business Server Deployment Wizard** A deployment program that provides a launch pad for installing the various components of Skype for Business Server.</span></span>
    
   - <span data-ttu-id="b7ea8-135">**Shell de gerenciamento do Skype for Business Server** Um programa pré-configurado do PowerShell que permite a administração do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="b7ea8-135">**Skype for Business Server Management Shell** A preconfigured PowerShell program that allows for administration of Skype for Business Server.</span></span>
    
     <span data-ttu-id="b7ea8-136">Após a conclusão da instalação dos componentes principais, o assistente de implantação do Skype for Business Server será iniciado automaticamente, conforme mostrado na figura.</span><span class="sxs-lookup"><span data-stu-id="b7ea8-136">Once the installation of the Core Components is complete, the Skype for Business Server Deployment Wizard will automatically launch, as shown in the figure.</span></span> 
    
     ![Assistente de Implantação do Skype for Business Server](../../media/310c3437-83f9-48fa-a1e1-9fd09009fe31.png)
  
6. <span data-ttu-id="b7ea8-138">Além dos componentes centrais, você também precisará instalar o construtor de topologias do Skype for Business Server e o painel de controle do Skype for Business Server em pelo menos um servidor no ambiente.</span><span class="sxs-lookup"><span data-stu-id="b7ea8-138">In addition to the Core Components, you will also need to install Skype for Business Server Topology Builder and Skype for Business Server Control Panel on at least one server in the environment.</span></span> <span data-ttu-id="b7ea8-139">Clique em **Instalar ferramentas administrativas** no Assistente de Implantação.</span><span class="sxs-lookup"><span data-stu-id="b7ea8-139">Click **Install Administrative Tools** on the Deployment Wizard.</span></span>
    
7. <span data-ttu-id="b7ea8-140">Clique em **Avançar** para começar a instalação.</span><span class="sxs-lookup"><span data-stu-id="b7ea8-140">Click **Next** to begin the installation.</span></span>
    
8. <span data-ttu-id="b7ea8-p109">Assim que a instalação for concluída, clique em **Concluir**. As ferramentas administrativas agora são adicionadas ao servidor, conforme mostra a figura.</span><span class="sxs-lookup"><span data-stu-id="b7ea8-p109">Once the installation has completed, click **Finish**. The administrative tools are now added to the server, as shown in the figure.</span></span>
    
    ![Ferramentas administrativas do Skype for Business Server](../../media/760873dd-9c87-4efb-bf98-7162d876fd18.png)
  
   - <span data-ttu-id="b7ea8-144">**Construtor de topologias do Skype for Business Server** Um programa usado para compilar, implantar e gerenciar topologias.</span><span class="sxs-lookup"><span data-stu-id="b7ea8-144">**Skype for Business Server Topology Builder** A program used to build, deploy, and manage topologies.</span></span>
    
   - <span data-ttu-id="b7ea8-145">**Painel de controle do Skype for Business Server** Um programa usado para administrar a instalação.</span><span class="sxs-lookup"><span data-stu-id="b7ea8-145">**Skype for Business Server Control Panel** A program used to administer the installation.</span></span>
    

