---
title: Instalar os pré-requisitos para o Skype for Business Server 2015
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
ms.assetid: 2ef91a1e-2899-44c8-8e2c-527cb9114a0a
description: 'Resumo: Saiba mais sobre os servidores e funções de servidor, que você deve configurar antes de instalar Skype para Business Server 2015. Baixe uma versão de avaliação gratuita do Skype para negócios 2015 de servidor do centro da Evaluation da Microsoft em: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: f37954b4eddffbcef08c270dc86234e3a56e7079
ms.sourcegitcommit: 2c084358844f02fbf7953f2ea49ed6d710cbf06f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/08/2018
---
# <a name="install-prerequisites-for-skype-for-business-server-2015"></a><span data-ttu-id="5dc6b-104">Instalar os pré-requisitos para o Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="5dc6b-104">Install prerequisites for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="5dc6b-105">**Resumo:** Saiba mais sobre os servidores e funções de servidor, que você deve configurar antes de instalar Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="5dc6b-105">**Summary:** Learn about the servers and server roles you must configure before you install Skype for Business Server 2015.</span></span> <span data-ttu-id="5dc6b-106">Baixe uma versão de avaliação gratuita do Skype para negócios 2015 de servidor do [Centro de avaliação do Microsoft](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span><span class="sxs-lookup"><span data-stu-id="5dc6b-106">Download a free trial of Skype for Business Server 2015 from the [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="5dc6b-107">Os pré-requisitos de instalação consistem na configuração do Windows Server por meio da instalação das funções e dos recursos necessários em cada servidor da topologia.</span><span class="sxs-lookup"><span data-stu-id="5dc6b-107">Installing prerequisites consists of setting up Windows Server by installing the required roles and features on each of the servers in the topology.</span></span> <span data-ttu-id="5dc6b-108">Os requisitos são baseados na função que o servidor vai desempenhar na topologia.</span><span class="sxs-lookup"><span data-stu-id="5dc6b-108">The requirements are based on the role the server will fulfill in the topology.</span></span> <span data-ttu-id="5dc6b-109">Você pode executar os passos 1 a 5 em qualquer ordem.</span><span class="sxs-lookup"><span data-stu-id="5dc6b-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="5dc6b-110">No entanto, as etapas 6, 7 e 8 devem ser executadas nesta ordem, após concluir as etapas 1 a 5, conforme descrito no diagrama.</span><span class="sxs-lookup"><span data-stu-id="5dc6b-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="5dc6b-111">Os pré-requisitos de instalação é a etapa 1 de 8.</span><span class="sxs-lookup"><span data-stu-id="5dc6b-111">Installing prerequisites is step 1 of 8.</span></span>
  
![Diagrama de visão geral - instalar pré-requisitos.](../../media/0a85349b-b398-4e04-8901-8f4bd25d8afe.png)
  
## <a name="setup-windows-server"></a><span data-ttu-id="5dc6b-113">Instalação do Windows Server</span><span class="sxs-lookup"><span data-stu-id="5dc6b-113">Setup Windows Server</span></span>

<span data-ttu-id="5dc6b-114">Skype para Business Server 2015 requer o sistema operacional Windows Server e um número de pré-requisitos antes que ele possa ser instalado.</span><span class="sxs-lookup"><span data-stu-id="5dc6b-114">Skype for Business Server 2015 requires the Windows Server operating system and a number of prerequisites before it can be installed.</span></span> <span data-ttu-id="5dc6b-115">Para obter detalhes sobre como planejar os pré-requisitos, consulte [requisitos de servidor para Skype para Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5dc6b-115">For details on planning for prerequisites, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span> 
  
> [!TIP]
> <span data-ttu-id="5dc6b-p105">Esse procedimento usa o Windows Server 2012 R2. Se você estiver usando uma versão diferente do Windows Server, o procedimento pode ser um pouco diferente.</span><span class="sxs-lookup"><span data-stu-id="5dc6b-p105">This procedure uses Windows Server 2012 R2. If you are using a different version of Windows Server, the procedure might be slightly different.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="5dc6b-118">Antes de começar, certifique-se de que o Windows Server seja atualizada usando o Windows Update.</span><span class="sxs-lookup"><span data-stu-id="5dc6b-118">Before you begin, make sure that Windows Server is up-to-date by using Windows Update.</span></span> 
  
![Windows Server atualizado.](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
<span data-ttu-id="5dc6b-120">Assista as etapas do vídeo para **os pré-requisitos de instalação**:</span><span class="sxs-lookup"><span data-stu-id="5dc6b-120">Watch the video steps for **install prerequisites**:</span></span>
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/02447c2a-5b26-432f-aad6-b9b05cc93478?autoplay=false]
  
### <a name="install-required-roles-and-features-for-front-end-servers"></a><span data-ttu-id="5dc6b-121">Instale as funções e os recursos necessários para os servidores front-end</span><span class="sxs-lookup"><span data-stu-id="5dc6b-121">Install required roles and features for front-end servers</span></span>

<span data-ttu-id="5dc6b-122">Você pode instalar as funções e necessários recursos usando o Gerenciador de servidores.</span><span class="sxs-lookup"><span data-stu-id="5dc6b-122">You can install the required roles and features using Server Manager.</span></span> 
    
1. <span data-ttu-id="5dc6b-123">Instale os recursos de software de pré-requisito listados em [requisitos de servidor para Skype para Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5dc6b-123">Install the prerequisite software features listed in [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span> <span data-ttu-id="5dc6b-124">O software necessário deve ser no servidor que executará o Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="5dc6b-124">The required software must be on the server that will run Skype for Business Server 2015.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="5dc6b-125">O Windows Server 2012 R2 não instala todos os arquivo de origem para os recursos necessários por padrão.</span><span class="sxs-lookup"><span data-stu-id="5dc6b-125">Windows Server 2012 R2 does not install all of the source files for the required features by default.</span></span> <span data-ttu-id="5dc6b-126">Se o servidor não estiver conectado à Internet, você terá que inserir a mídia do Windows Server 2012 R2 e selecionar **Especificar um caminho de origem alternativo** para instalar os recursos necessários.</span><span class="sxs-lookup"><span data-stu-id="5dc6b-126">If the server is not connected to the Internet, you will need to insert the Windows Server 2012 R2 media and select **Specify an alternate source path** in order to install the required features.</span></span> <span data-ttu-id="5dc6b-127">Os arquivos de origem estão localizados no diretório sources\sxs.</span><span class="sxs-lookup"><span data-stu-id="5dc6b-127">The source files are located in the sources\sxs directory.</span></span> <span data-ttu-id="5dc6b-128">Por exemplo, se a mídia do Windows Server 2012 R2 estiver na unidade D, você teria que definir o caminho como `d:\sources\sxs`.</span><span class="sxs-lookup"><span data-stu-id="5dc6b-128">For example, if the Windows Server 2012 R2 media is in drive D, you would set the path to `d:\sources\sxs`.</span></span> <span data-ttu-id="5dc6b-129">É importante que você tenha as atualizações mais recentes do Windows Update.</span><span class="sxs-lookup"><span data-stu-id="5dc6b-129">It is important that you have the latest updates from Windows Update.</span></span> <span data-ttu-id="5dc6b-130">Se você não estiver conectado à Internet, terá que instalar manualmente todas as atualizações importantes, bem como quaisquer pré-requisitos para as atualizações necessárias.</span><span class="sxs-lookup"><span data-stu-id="5dc6b-130">If you are not connected to the Internet, you will need to manually install all relevant updates as well as any prerequisites to the required updates.</span></span> 
  
1. <span data-ttu-id="5dc6b-131">Quando a caixa de diálogo indicar que a instalação foi concluída, você terá que reiniciar o servidor para concluir o processo.</span><span class="sxs-lookup"><span data-stu-id="5dc6b-131">When the dialog box indicates that the installation has completed, you will need to reboot the server to complete the process.</span></span>
    
1. <span data-ttu-id="5dc6b-132">Execute o **Windows Update** novamente para verificar se há alguma atualização para as funções e os serviços que foram instalados.</span><span class="sxs-lookup"><span data-stu-id="5dc6b-132">Run **Windows Update** again to check if there are any updates to the roles and services that were installed.</span></span>
    
1. <span data-ttu-id="5dc6b-133">Se você for usar Skype para painel de controle do Business Server neste servidor você também deve instalar o Silverlight.</span><span class="sxs-lookup"><span data-stu-id="5dc6b-133">If you will be using Skype for Business Server Control Panel on this server then you must also install Silverlight.</span></span> <span data-ttu-id="5dc6b-134">Para instalar o Silverlight, consulte [Microsoft Silverlight](https://www.microsoft.com/silverlight/).</span><span class="sxs-lookup"><span data-stu-id="5dc6b-134">To install Silverlight, see [Microsoft Silverlight](https://www.microsoft.com/silverlight/).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="5dc6b-135">Os pré-requisitos para servidores executando funções diferentes da de servidor front-end, como a função de Diretor, Chat Persistente ou Borda, terão seus próprios pré-requisitos.</span><span class="sxs-lookup"><span data-stu-id="5dc6b-135">The prerequisites for servers performing roles other than front-end server, such as the role of Director, Persistent Chat, or Edge, have their own prerequisites.</span></span> <span data-ttu-id="5dc6b-136">Para obter detalhes sobre os pré-requisitos exatos exigidos por cada tipo de servidor, consulte [requisitos de servidor para Skype para Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5dc6b-136">For details on the exact prerequisites required by each server type, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span> 
  

