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
description: 'Resumo: visão geral dos métodos de instalação de cliente Enterprise para o Skype for Business.'
ms.openlocfilehash: cdee3db6dc6fcec646ee2e15b6aeebc298d75b67
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43778277"
---
# <a name="deploy-clients-for-skype-for-business-server"></a><span data-ttu-id="dbeb8-103">Implantar clientes para o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="dbeb8-103">Deploy clients for Skype for Business Server</span></span>
 
<span data-ttu-id="dbeb8-104">**Resumo:** Visão geral dos métodos de instalação de cliente Enterprise para o Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="dbeb8-104">**Summary:** Overview of enterprise client installation methods for Skype for Business.</span></span>
  
<span data-ttu-id="dbeb8-105">O modo como você implanta o Skype for Business para seus usuários depende se você comprou o Skype for Business como parte de um plano do Office 365 ou se comprou uma versão licenciada por volume do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="dbeb8-105">How you deploy Skype for Business to your users depends on whether you purchased Skype for Business as part of an Office 365 plan or you purchased a volume licensed version of Skype for Business.</span></span> 
  
- <span data-ttu-id="dbeb8-106">**Office 365** Se você tiver um plano do Office 365 que inclui o Skype for Business, a tecnologia de instalação usada é chamada de clique para executar.</span><span class="sxs-lookup"><span data-stu-id="dbeb8-106">**Office 365** If you have an Office 365 plan that includes Skype for Business, the installation technology that's used is called Click-to-Run.</span></span> <span data-ttu-id="dbeb8-107">Com o Office 365, você pode permitir que seus usuários instalem o Skype for Business por conta própria a partir do centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dbeb8-107">With Office 365, you can let your users install Skype for Business for themselves from the Microsoft 365 admin center.</span></span> <span data-ttu-id="dbeb8-108">Ou você pode implantar o Skype for Business em seus usuários baixando o software para sua rede local e usando suas ferramentas de implantação de software existentes, como o Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="dbeb8-108">Or, you can deploy Skype for Business to your users by downloading the software to your local network and then using your existing software deployment tools, such as with Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="dbeb8-109">Para obter informações sobre a instalação do Skype for Business que acompanham o Office 365, consulte [implantar o cliente Skype for Business no office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span><span class="sxs-lookup"><span data-stu-id="dbeb8-109">For installation information about Skype for Business that comes with Office 365, see [Deploy the Skype for Business client in Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span></span>
    
- <span data-ttu-id="dbeb8-110">**Volume licenciado** Se você tiver uma versão licenciada por volume do cliente do Skype for Business 2015 ou 2016, a tecnologia de instalação usada pelo Windows Installer (MSI).</span><span class="sxs-lookup"><span data-stu-id="dbeb8-110">**Volume licensed** If you have a volume licensed version of the Skype for Business 2015 or 2016 client, the installation technology that's used is Windows Installer (MSI).</span></span> <span data-ttu-id="dbeb8-111">Um pacote de instalação baseado no Windows Installer consiste em vários arquivos MSI.</span><span class="sxs-lookup"><span data-stu-id="dbeb8-111">A Windows Installer-based installation package consists of multiple MSI files.</span></span> <span data-ttu-id="dbeb8-112">Um pacote de núcleo MSI de linguagem neutra é combinado com um ou mais pacotes de linguagem específica para fazer um produto completo.</span><span class="sxs-lookup"><span data-stu-id="dbeb8-112">A language-neutral core MSI package is combined with one or more language-specific packages to make a complete product.</span></span> <span data-ttu-id="dbeb8-113">A instalação reúne os pacotes individuais e efetua a personalização e tarefas de manutenção durante e após a instalação do Office nos computadores dos usuários.</span><span class="sxs-lookup"><span data-stu-id="dbeb8-113">Setup assembles the individual packages and performs customization and maintenance tasks during and after installation of Office on users' computers.</span></span> <span data-ttu-id="dbeb8-114">O cliente 2019 do Skype for Business usa instaladores de clique para executar.</span><span class="sxs-lookup"><span data-stu-id="dbeb8-114">The Skype for Business 2019 client uses Click-to-Run installers.</span></span>
    
<span data-ttu-id="dbeb8-115">Os tópicos desta seção descrevem como usar e personalizar o Windows Installer para implantar o cliente Skype for Business em seus usuários através de seus procedimentos normais.</span><span class="sxs-lookup"><span data-stu-id="dbeb8-115">The topics in this section describe how to use and customize the Windows Installer to deploy the Skype for Business client to your users through your normal procedures.</span></span>
  
> [!NOTE]
> <span data-ttu-id="dbeb8-116">O suplemento de reunião do Skype para o Microsoft Office, que oferece suporte ao gerenciamento de reuniões a partir do cliente de mensagens e colaboração do Outlook, é instalado automaticamente com clientes do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="dbeb8-116">The Skype Meeting Add-in for Microsoft Office, which supports meeting management from within the Outlook messaging and collaboration client, installs automatically with Skype for Business clients.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="dbeb8-117">O programa de instalação do Office 365 não desinstala versões anteriores do Lync.</span><span class="sxs-lookup"><span data-stu-id="dbeb8-117">The Office 365 setup program does not uninstall previous versions of Lync.</span></span> <span data-ttu-id="dbeb8-118">O cliente Skype for Business instala lado a lado com outros clientes do Lync.</span><span class="sxs-lookup"><span data-stu-id="dbeb8-118">The Skype for Business client installs side-by-side with other Lync clients.</span></span> 
  
## <a name="installing-windows-clients"></a><span data-ttu-id="dbeb8-119">Instalando clientes do Windows</span><span class="sxs-lookup"><span data-stu-id="dbeb8-119">Installing Windows clients</span></span>

- [<span data-ttu-id="dbeb8-120">Personalizar a instalação do cliente Windows no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="dbeb8-120">Customize Windows client installation in Skype for Business Server</span></span>](customize-windows-client-installation.md)
    
- [<span data-ttu-id="dbeb8-121">Configurar a experiência do cliente com o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="dbeb8-121">Configure the client experience with Skype for Business</span></span>](configure-the-client-experience.md)
    
- [<span data-ttu-id="dbeb8-122">Configurar a lista de contatos inteligente no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="dbeb8-122">Configure Smart contacts list in Skype for Business Server</span></span>](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a><span data-ttu-id="dbeb8-123">Instalando clientes de dispositivos</span><span class="sxs-lookup"><span data-stu-id="dbeb8-123">Installing device clients</span></span>

- [<span data-ttu-id="dbeb8-124">Instalar e testar o Skype for Business para Windows Phone</span><span class="sxs-lookup"><span data-stu-id="dbeb8-124">Install and test Skype for Business for Windows Phone</span></span>](windows-phone.md)
    
- [<span data-ttu-id="dbeb8-125">Instalar e testar o Skype for Business para iOS</span><span class="sxs-lookup"><span data-stu-id="dbeb8-125">Install and test Skype for Business for iOS</span></span>](ios.md)
    
    
- [<span data-ttu-id="dbeb8-126">Implantar o plug-in de VDI do Lync com o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="dbeb8-126">Deploy the Lync VDI plug-in with Skype for Business Server</span></span>](deploy-the-lync-vdi-plug-in.md)
    
- [<span data-ttu-id="dbeb8-127">Implantar clientes para download da Web no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="dbeb8-127">Deploy Web downloadable clients in Skype for Business Server</span></span>](deploy-web-downloadable-clients.md)
    
- [<span data-ttu-id="dbeb8-128">Personalizar a experiência do cliente Mac no Skype for Business</span><span class="sxs-lookup"><span data-stu-id="dbeb8-128">Customize the Mac client experience in Skype for Business</span></span>](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a><span data-ttu-id="dbeb8-129">Confira também</span><span class="sxs-lookup"><span data-stu-id="dbeb8-129">See also</span></span>

[<span data-ttu-id="dbeb8-130">Implantar o cliente Skype for Business no Office 365</span><span class="sxs-lookup"><span data-stu-id="dbeb8-130">Deploy the Skype for Business client in Office 365</span></span>](../../../SfbOnline/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365.md)
