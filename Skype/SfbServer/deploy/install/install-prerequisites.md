---
title: Instalar pré-requisitos para o Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/7/2018
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
ms.assetid: 2ef91a1e-2899-44c8-8e2c-527cb9114a0a
description: 'Resumo: saiba mais sobre os servidores e as funções de servidor que você deve configurar antes de instalar o Skype for Business Server. Baixe uma avaliação gratuita do Skype for Business Server no Centro de Avaliação da Microsoft em: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server .'
ms.openlocfilehash: 197f2482bd6c53f3cf9814dbf6f36bb6c4bdb331
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801711"
---
# <a name="install-prerequisites-for-skype-for-business-server"></a><span data-ttu-id="9c7c1-104">Instalar pré-requisitos para o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="9c7c1-104">Install prerequisites for Skype for Business Server</span></span>
 
<span data-ttu-id="9c7c1-105">**Resumo:** Saiba mais sobre os servidores e as funções de servidor que você deve configurar antes de instalar o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="9c7c1-105">**Summary:** Learn about the servers and server roles you must configure before you install Skype for Business Server.</span></span> <span data-ttu-id="9c7c1-106">Baixe uma avaliação gratuita do Skype for Business Server no Centro [de Avaliação da Microsoft.](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)</span><span class="sxs-lookup"><span data-stu-id="9c7c1-106">Download a free trial of Skype for Business Server from the [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="9c7c1-107">A instalação dos pré-requisitos consiste em configurar o Windows Server instalando as funções e os recursos necessários em cada um dos servidores na topologia.</span><span class="sxs-lookup"><span data-stu-id="9c7c1-107">Installing prerequisites consists of setting up Windows Server by installing the required roles and features on each of the servers in the topology.</span></span> <span data-ttu-id="9c7c1-108">Os requisitos são baseados na função que o servidor cumprirá na topologia.</span><span class="sxs-lookup"><span data-stu-id="9c7c1-108">The requirements are based on the role the server will fulfill in the topology.</span></span> <span data-ttu-id="9c7c1-109">Você pode realizar as etapas 1 a 5 em qualquer ordem.</span><span class="sxs-lookup"><span data-stu-id="9c7c1-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="9c7c1-110">No entanto, você deve realizar as etapas 6, 7 e 8 na ordem e após as etapas de 1 a 5, conforme descrito no diagrama.</span><span class="sxs-lookup"><span data-stu-id="9c7c1-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="9c7c1-111">Instalar os pré-requisitos é a etapa 1 de 8.</span><span class="sxs-lookup"><span data-stu-id="9c7c1-111">Installing prerequisites is step 1 of 8.</span></span>
  
![Diagrama de visão geral - pré-requisitos de instalação.](../../media/0a85349b-b398-4e04-8901-8f4bd25d8afe.png)
  
## <a name="setup-windows-server"></a><span data-ttu-id="9c7c1-113">Configurar o Windows Server</span><span class="sxs-lookup"><span data-stu-id="9c7c1-113">Setup Windows Server</span></span>

<span data-ttu-id="9c7c1-114">O Skype for Business Server requer o sistema operacional Windows Server e vários pré-requisitos para que ele possa ser instalado.</span><span class="sxs-lookup"><span data-stu-id="9c7c1-114">Skype for Business Server requires the Windows Server operating system and a number of prerequisites before it can be installed.</span></span> <span data-ttu-id="9c7c1-115">Para obter detalhes sobre o planejamento de pré-requisitos, consulte [Requisitos de servidor para o Skype for Business Server.](../../../SfBServer2019/plan/system-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="9c7c1-115">For details on planning for prerequisites, see [Server requirements for Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md).</span></span> 
  
> [!TIP]
> <span data-ttu-id="9c7c1-116">Este procedimento usa o Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="9c7c1-116">This procedure uses Windows Server 2012 R2.</span></span> <span data-ttu-id="9c7c1-117">Se você estiver usando uma versão diferente do Windows Server, o procedimento pode ser ligeiramente diferente.</span><span class="sxs-lookup"><span data-stu-id="9c7c1-117">If you are using a different version of Windows Server, the procedure might be slightly different.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="9c7c1-118">Antes de começar, certifique-se de que o Windows Server está atualizado usando o Windows Update.</span><span class="sxs-lookup"><span data-stu-id="9c7c1-118">Before you begin, make sure that Windows Server is up-to-date by using Windows Update.</span></span> 
  
![Windows Server atualizado.](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
<span data-ttu-id="9c7c1-120">Assista às etapas de vídeo **para instalar os pré-requisitos:**</span><span class="sxs-lookup"><span data-stu-id="9c7c1-120">Watch the video steps for **install prerequisites**:</span></span>
  
> [!video https://www.microsoft.com/videoplayer/embed/02447c2a-5b26-432f-aad6-b9b05cc93478?autoplay=false]
  
### <a name="install-required-roles-and-features-for-front-end-servers"></a><span data-ttu-id="9c7c1-121">Instalar funções e recursos necessários para servidores front-end</span><span class="sxs-lookup"><span data-stu-id="9c7c1-121">Install required roles and features for front-end servers</span></span>

<span data-ttu-id="9c7c1-122">Você pode instalar as funções e os recursos necessários usando o Gerenciador do Servidor.</span><span class="sxs-lookup"><span data-stu-id="9c7c1-122">You can install the required roles and features using Server Manager.</span></span> 
    
1. <span data-ttu-id="9c7c1-123">Instale os recursos de software de pré-requisito listados nos [requisitos de servidor para o Skype for Business Server.](../../../SfBServer2019/plan/system-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="9c7c1-123">Install the prerequisite software features listed in [Server requirements for Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md).</span></span> <span data-ttu-id="9c7c1-124">O software necessário deve estar no servidor que executará o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="9c7c1-124">The required software must be on the server that will run Skype for Business Server.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="9c7c1-125">O Windows Server 2012 R2 não instala todos os arquivos de origem dos recursos necessários por padrão.</span><span class="sxs-lookup"><span data-stu-id="9c7c1-125">Windows Server 2012 R2 does not install all of the source files for the required features by default.</span></span> <span data-ttu-id="9c7c1-126">Se o servidor não estiver conectado à Internet, será necessário inserir a mídia do  Windows Server 2012 R2 e selecionar Especificar um caminho de origem alternativo para instalar os recursos necessários.</span><span class="sxs-lookup"><span data-stu-id="9c7c1-126">If the server is not connected to the Internet, you will need to insert the Windows Server 2012 R2 media and select **Specify an alternate source path** in order to install the required features.</span></span> <span data-ttu-id="9c7c1-127">Os arquivos de origem estão localizados no diretório sources\sxs.</span><span class="sxs-lookup"><span data-stu-id="9c7c1-127">The source files are located in the sources\sxs directory.</span></span> <span data-ttu-id="9c7c1-128">Por exemplo, se a mídia do Windows Server 2012 R2 estiver na unidade D, você deve definir o caminho para `d:\sources\sxs` .</span><span class="sxs-lookup"><span data-stu-id="9c7c1-128">For example, if the Windows Server 2012 R2 media is in drive D, you would set the path to `d:\sources\sxs`.</span></span> <span data-ttu-id="9c7c1-129">É importante que você tenha as atualizações mais recentes do Windows Update.</span><span class="sxs-lookup"><span data-stu-id="9c7c1-129">It is important that you have the latest updates from Windows Update.</span></span> <span data-ttu-id="9c7c1-130">Se você não estiver conectado à Internet, será necessário instalar manualmente todas as atualizações relevantes, bem como quaisquer pré-requisitos para as atualizações necessárias.</span><span class="sxs-lookup"><span data-stu-id="9c7c1-130">If you are not connected to the Internet, you will need to manually install all relevant updates as well as any prerequisites to the required updates.</span></span> 
  
1. <span data-ttu-id="9c7c1-131">Quando a caixa de diálogo indicar que a instalação foi concluída, você precisará reiniciar o servidor para concluir o processo.</span><span class="sxs-lookup"><span data-stu-id="9c7c1-131">When the dialog box indicates that the installation has completed, you will need to reboot the server to complete the process.</span></span>
    
1. <span data-ttu-id="9c7c1-132">Execute **o Windows Update** novamente para verificar se há alguma atualização para as funções e serviços que foram instalados.</span><span class="sxs-lookup"><span data-stu-id="9c7c1-132">Run **Windows Update** again to check if there are any updates to the roles and services that were installed.</span></span>
    
1. <span data-ttu-id="9c7c1-133">Se você for usar o Painel de Controle do Skype for Business Server neste servidor, também deverá instalar o Silverlight.</span><span class="sxs-lookup"><span data-stu-id="9c7c1-133">If you will be using Skype for Business Server Control Panel on this server then you must also install Silverlight.</span></span> <span data-ttu-id="9c7c1-134">Para instalar o Silverlight, consulte [o Microsoft Silverlight.](https://www.microsoft.com/silverlight/)</span><span class="sxs-lookup"><span data-stu-id="9c7c1-134">To install Silverlight, see [Microsoft Silverlight](https://www.microsoft.com/silverlight/).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="9c7c1-135">Os pré-requisitos para servidores que executam funções diferentes do servidor front-end, como a função de Diretor, Chat Persistente ou Borda, têm seus próprios pré-requisitos.</span><span class="sxs-lookup"><span data-stu-id="9c7c1-135">The prerequisites for servers performing roles other than front-end server, such as the role of Director, Persistent Chat, or Edge, have their own prerequisites.</span></span> <span data-ttu-id="9c7c1-136">Para obter detalhes sobre os pré-requisitos exatos exigidos por cada tipo de servidor, consulte Requisitos de [servidor para o Skype for Business Server.](../../../SfBServer2019/plan/system-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="9c7c1-136">For details on the exact prerequisites required by each server type, see [Server requirements for Skype for Business Server](../../../SfBServer2019/plan/system-requirements.md).</span></span> 
  

