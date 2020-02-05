---
title: Implantar clientes para o Skype for Business Server
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
description: 'Resumo: visão geral dos métodos de instalação do cliente corporativo para o Skype for Business.'
ms.openlocfilehash: 0e7859fe207ed80aa7dceef794aa57d15cc0c79b
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768724"
---
# <a name="deploy-clients-for-skype-for-business-server"></a><span data-ttu-id="45e65-103">Implantar clientes para o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="45e65-103">Deploy clients for Skype for Business Server</span></span>
 
<span data-ttu-id="45e65-104">**Resumo:** Visão geral dos métodos de instalação do cliente Enterprise para o Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="45e65-104">**Summary:** Overview of enterprise client installation methods for Skype for Business.</span></span>
  
<span data-ttu-id="45e65-105">A maneira como você implanta o Skype for Business para seus usuários depende se você comprou o Skype for Business como parte de um plano do Office 365 ou se comprou uma versão licenciada de volume do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="45e65-105">How you deploy Skype for Business to your users depends on whether you purchased Skype for Business as part of an Office 365 plan or you purchased a volume licensed version of Skype for Business.</span></span> 
  
- <span data-ttu-id="45e65-106">**Office 365** Se você tiver um plano do Office 365 que inclua o Skype for Business, a tecnologia de instalação que é usada é chamada de clique para executar.</span><span class="sxs-lookup"><span data-stu-id="45e65-106">**Office 365** If you have an Office 365 plan that includes Skype for Business, the installation technology that's used is called Click-to-Run.</span></span> <span data-ttu-id="45e65-107">Com o Office 365, você pode permitir que os usuários instalem o Skype for Business por conta própria no portal do Office 365.</span><span class="sxs-lookup"><span data-stu-id="45e65-107">With Office 365, you can let your users install Skype for Business for themselves from the Office 365 portal.</span></span> <span data-ttu-id="45e65-108">Ou você pode implantar o Skype for Business para seus usuários baixando o software para a sua rede local e, em seguida, usando as ferramentas de implantação de software existentes, como o Gerenciador de configuração do Microsoft Endpoint.</span><span class="sxs-lookup"><span data-stu-id="45e65-108">Or, you can deploy Skype for Business to your users by downloading the software to your local network and then using your existing software deployment tools, such as with Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="45e65-109">Para obter informações de instalação sobre o Skype for Business que vem com o Office 365, consulte [implantar o cliente Skype for Business no Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span><span class="sxs-lookup"><span data-stu-id="45e65-109">For installation information about Skype for Business that comes with Office 365, see [Deploy the Skype for Business client in Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span></span>
    
- <span data-ttu-id="45e65-110">**Volume licenciado** Se você tiver uma versão licenciada de volume do cliente Skype for Business 2015 ou 2016, a tecnologia de instalação usada pelo Windows Installer (MSI).</span><span class="sxs-lookup"><span data-stu-id="45e65-110">**Volume licensed** If you have a volume licensed version of the Skype for Business 2015 or 2016 client, the installation technology that's used is Windows Installer (MSI).</span></span> <span data-ttu-id="45e65-111">Um pacote de instalação baseado no Windows Installer consiste em vários arquivos MSI.</span><span class="sxs-lookup"><span data-stu-id="45e65-111">A Windows Installer-based installation package consists of multiple MSI files.</span></span> <span data-ttu-id="45e65-112">Um pacote de núcleo MSI de linguagem neutra é combinado com um ou mais pacotes de linguagem específica para fazer um produto completo.</span><span class="sxs-lookup"><span data-stu-id="45e65-112">A language-neutral core MSI package is combined with one or more language-specific packages to make a complete product.</span></span> <span data-ttu-id="45e65-113">A instalação reúne os pacotes individuais e efetua a personalização e tarefas de manutenção durante e após a instalação do Office nos computadores dos usuários.</span><span class="sxs-lookup"><span data-stu-id="45e65-113">Setup assembles the individual packages and performs customization and maintenance tasks during and after installation of Office on users' computers.</span></span> <span data-ttu-id="45e65-114">O cliente Skype for Business 2019 usa instaladores com Clique para executar.</span><span class="sxs-lookup"><span data-stu-id="45e65-114">The Skype for Business 2019 client uses Click-to-Run installers.</span></span>
    
<span data-ttu-id="45e65-115">Os tópicos desta seção descrevem como usar e personalizar o Windows Installer para implantar o cliente Skype for Business para seus usuários por meio de seus procedimentos normais.</span><span class="sxs-lookup"><span data-stu-id="45e65-115">The topics in this section describe how to use and customize the Windows Installer to deploy the Skype for Business client to your users through your normal procedures.</span></span>
  
> [!NOTE]
> <span data-ttu-id="45e65-116">O suplemento de reunião do Skype para Microsoft Office, que dá suporte ao gerenciamento de reuniões dentro do cliente de mensagens e colaboração do Outlook, é instalado automaticamente com os clientes do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="45e65-116">The Skype Meeting Add-in for Microsoft Office, which supports meeting management from within the Outlook messaging and collaboration client, installs automatically with Skype for Business clients.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="45e65-117">O programa de instalação do Office 365 não desinstala versões anteriores do Lync.</span><span class="sxs-lookup"><span data-stu-id="45e65-117">The Office 365 setup program does not uninstall previous versions of Lync.</span></span> <span data-ttu-id="45e65-118">O cliente Skype for Business é instalado lado a lado com outros clientes do Lync.</span><span class="sxs-lookup"><span data-stu-id="45e65-118">The Skype for Business client installs side-by-side with other Lync clients.</span></span> 
  
## <a name="installing-windows-clients"></a><span data-ttu-id="45e65-119">Instalar clientes do Windows</span><span class="sxs-lookup"><span data-stu-id="45e65-119">Installing Windows clients</span></span>

- [<span data-ttu-id="45e65-120">Personalizar a instalação do Windows Client no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="45e65-120">Customize Windows client installation in Skype for Business Server</span></span>](customize-windows-client-installation.md)
    
- [<span data-ttu-id="45e65-121">Configure the client experience with Skype for Business</span><span class="sxs-lookup"><span data-stu-id="45e65-121">Configure the client experience with Skype for Business</span></span>](configure-the-client-experience.md)
    
- [<span data-ttu-id="45e65-122">Configurar lista de contatos Inteligente no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="45e65-122">Configure Smart contacts list in Skype for Business Server</span></span>](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a><span data-ttu-id="45e65-123">Instalar clientes de dispositivos</span><span class="sxs-lookup"><span data-stu-id="45e65-123">Installing device clients</span></span>

- [<span data-ttu-id="45e65-124">Install and test Skype for Business for Windows Phone</span><span class="sxs-lookup"><span data-stu-id="45e65-124">Install and test Skype for Business for Windows Phone</span></span>](windows-phone.md)
    
- [<span data-ttu-id="45e65-125">Install and test Skype for Business for iOS</span><span class="sxs-lookup"><span data-stu-id="45e65-125">Install and test Skype for Business for iOS</span></span>](ios.md)
    
    
- [<span data-ttu-id="45e65-126">Implantar o plug-in VDI do Lync com o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="45e65-126">Deploy the Lync VDI plug-in with Skype for Business Server</span></span>](deploy-the-lync-vdi-plug-in.md)
    
- [<span data-ttu-id="45e65-127">Implantar clientes para download da Web no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="45e65-127">Deploy Web downloadable clients in Skype for Business Server</span></span>](deploy-web-downloadable-clients.md)
    
- [<span data-ttu-id="45e65-128">Personalizar a experiência do cliente Mac no Skype for Business</span><span class="sxs-lookup"><span data-stu-id="45e65-128">Customize the Mac client experience in Skype for Business</span></span>](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a><span data-ttu-id="45e65-129">Confira também</span><span class="sxs-lookup"><span data-stu-id="45e65-129">See also</span></span>

[<span data-ttu-id="45e65-130">Implantar o cliente Skype for Business no Office 365</span><span class="sxs-lookup"><span data-stu-id="45e65-130">Deploy the Skype for Business client in Office 365</span></span>](../../../SfbOnline/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365.md)
