---
title: Implantar clientes para o Skype para Business Server
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
description: 'Resumo: Visão geral dos métodos de instalação de cliente enterprise para Skype para negócios.'
ms.openlocfilehash: 31eb109f80379487ba50342817759f8d9b30acda
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20985684"
---
# <a name="deploy-clients-for-skype-for-business-server"></a><span data-ttu-id="8c74b-103">Implantar clientes para o Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="8c74b-103">Deploy clients for Skype for Business Server</span></span>
 
<span data-ttu-id="8c74b-104">**Resumo:** Visão geral dos métodos de instalação de cliente enterprise para Skype para negócios.</span><span class="sxs-lookup"><span data-stu-id="8c74b-104">**Summary:** Overview of enterprise client installation methods for Skype for Business.</span></span>
  
<span data-ttu-id="8c74b-105">Como você implanta Skype for Business para seus usuários depende se você comprou Skype para negócios como parte de um plano do Office 365 ou você comprou uma versão licenciada do volume do Skype para negócios.</span><span class="sxs-lookup"><span data-stu-id="8c74b-105">How you deploy Skype for Business to your users depends on whether you purchased Skype for Business as part of an Office 365 plan or you purchased a volume licensed version of Skype for Business.</span></span> 
  
- <span data-ttu-id="8c74b-106">**Office 365** Se você tiver um plano do Office 365 que inclui Skype para a empresa, a tecnologia de instalação que é usada é chamada Click-to-Run.</span><span class="sxs-lookup"><span data-stu-id="8c74b-106">**Office 365** If you have an Office 365 plan that includes Skype for Business, the installation technology that's used is called Click-to-Run.</span></span> <span data-ttu-id="8c74b-107">Com o Office 365, você pode permitir que os usuários instalar Skype for Business para si próprios do portal do Office 365.</span><span class="sxs-lookup"><span data-stu-id="8c74b-107">With Office 365, you can let your users install Skype for Business for themselves from the Office 365 portal.</span></span> <span data-ttu-id="8c74b-108">Ou então, você pode implantar Skype for Business para seus usuários baixando o software em sua rede local e, em seguida, usando suas ferramentas de implantação de software existentes, tais como com o Microsoft System Center Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="8c74b-108">Or, you can deploy Skype for Business to your users by downloading the software to your local network and then using your existing software deployment tools, such as with Microsoft System Center Configuration Manager.</span></span> <span data-ttu-id="8c74b-109">Para obter informações de instalação sobre Skype for Business que vem com o Office 365, consulte [Deploy a Skype para o cliente de negócios no Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span><span class="sxs-lookup"><span data-stu-id="8c74b-109">For installation information about Skype for Business that comes with Office 365, see [Deploy the Skype for Business client in Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span></span>
    
- <span data-ttu-id="8c74b-110">**Licença de volume** Se você tiver uma versão licenciada do volume do Skype para negócios 2015 ou cliente 2016, a tecnologia de instalação que é usada é o Windows Installer (MSI).</span><span class="sxs-lookup"><span data-stu-id="8c74b-110">**Volume licensed** If you have a volume licensed version of the Skype for Business 2015 or 2016 client, the installation technology that's used is Windows Installer (MSI).</span></span> <span data-ttu-id="8c74b-111">Um pacote de instalação baseada no Windows Installer consiste em vários arquivos MSI.</span><span class="sxs-lookup"><span data-stu-id="8c74b-111">A Windows Installer-based installation package consists of multiple MSI files.</span></span> <span data-ttu-id="8c74b-112">Um pacote de núcleo MSI de linguagem neutra é combinado com um ou mais pacotes de linguagem específica para fazer um produto completo.</span><span class="sxs-lookup"><span data-stu-id="8c74b-112">A language-neutral core MSI package is combined with one or more language-specific packages to make a complete product.</span></span> <span data-ttu-id="8c74b-113">A instalação reúne os pacotes individuais e efetua a personalização e tarefas de manutenção durante e após a instalação do Office nos computadores dos usuários.</span><span class="sxs-lookup"><span data-stu-id="8c74b-113">Setup assembles the individual packages and performs customization and maintenance tasks during and after installation of Office on users' computers.</span></span> <span data-ttu-id="8c74b-114">O Skype para negócios 2019 cliente usa instaladores Click-to-Run.</span><span class="sxs-lookup"><span data-stu-id="8c74b-114">The Skype for Business 2019 client uses Click-to-Run installers.</span></span>
    
<span data-ttu-id="8c74b-115">Os tópicos desta seção descrevem como usar e personalizar o Windows Installer para implantar o Skype para o cliente de negócios para seus usuários por meio de seus procedimentos normais.</span><span class="sxs-lookup"><span data-stu-id="8c74b-115">The topics in this section describe how to use and customize the Windows Installer to deploy the Skype for Business client to your users through your normal procedures.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8c74b-116">O suplemento de reunião Skype para Microsoft Office, que suporta o gerenciamento de reuniões de dentro do cliente de mensagens e colaboração do Outlook, instala automaticamente com Skype para clientes corporativos.</span><span class="sxs-lookup"><span data-stu-id="8c74b-116">The Skype Meeting Add-in for Microsoft Office, which supports meeting management from within the Outlook messaging and collaboration client, installs automatically with Skype for Business clients.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="8c74b-117">O programa de instalação do Office 365 não desinstala versões anteriores do Lync.</span><span class="sxs-lookup"><span data-stu-id="8c74b-117">The Office 365 setup program does not uninstall previous versions of Lync.</span></span> <span data-ttu-id="8c74b-118">O Skype para Business client instala lado a lado com outros clientes do Lync.</span><span class="sxs-lookup"><span data-stu-id="8c74b-118">The Skype for Business client installs side-by-side with other Lync clients.</span></span> 
  
## <a name="installing-windows-clients"></a><span data-ttu-id="8c74b-119">Instalando clientes Windows</span><span class="sxs-lookup"><span data-stu-id="8c74b-119">Installing Windows clients</span></span>

- [<span data-ttu-id="8c74b-120">Personalizar a instalação de cliente do Windows no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="8c74b-120">Customize Windows client installation in Skype for Business Server</span></span>](customize-windows-client-installation.md)
    
- [<span data-ttu-id="8c74b-121">Configurar a experiência do cliente com o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="8c74b-121">Configure the client experience with Skype for Business</span></span>](configure-the-client-experience.md)
    
- [<span data-ttu-id="8c74b-122">Configurar lista de contatos Inteligente no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="8c74b-122">Configure Smart contacts list in Skype for Business Server</span></span>](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a><span data-ttu-id="8c74b-123">Instalando clientes de dispositivos</span><span class="sxs-lookup"><span data-stu-id="8c74b-123">Installing device clients</span></span>

- [<span data-ttu-id="8c74b-124">Skype for Business Server 2015: Instalar e testar o Skype for Business para Windows Phone</span><span class="sxs-lookup"><span data-stu-id="8c74b-124">Install and test Skype for Business for Windows Phone</span></span>](windows-phone.md)
    
- [<span data-ttu-id="8c74b-125">Instalar e testar o Skype for Business para iOS</span><span class="sxs-lookup"><span data-stu-id="8c74b-125">Install and test Skype for Business for iOS</span></span>](ios.md)
    
- [<span data-ttu-id="8c74b-126">Implantar Sistema de Salas do Skype no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="8c74b-126">Deploy Skype Room System in Skype for Business Server</span></span>](deploy-skype-room-system.md)
    
- [<span data-ttu-id="8c74b-127">Implantar o Skype Room Systems versão 2</span><span class="sxs-lookup"><span data-stu-id="8c74b-127">Deploy Skype Room Systems v2</span></span>](room-systems-v2.md)
    
- [<span data-ttu-id="8c74b-128">Implantar o Lync VDI plug-in com Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="8c74b-128">Deploy the Lync VDI plug-in with Skype for Business Server</span></span>](deploy-the-lync-vdi-plug-in.md)
    
- [<span data-ttu-id="8c74b-129">Implantar clientes para download da Web no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="8c74b-129">Deploy Web downloadable clients in Skype for Business Server</span></span>](deploy-web-downloadable-clients.md)
    
- [<span data-ttu-id="8c74b-130">Personalizar a experiência do cliente Mac no Skype for Business</span><span class="sxs-lookup"><span data-stu-id="8c74b-130">Customize the Mac client experience in Skype for Business</span></span>](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a><span data-ttu-id="8c74b-131">Consulte também</span><span class="sxs-lookup"><span data-stu-id="8c74b-131">See also</span></span>

[<span data-ttu-id="8c74b-132">Implantar o Skype para o cliente de negócios no Office 365</span><span class="sxs-lookup"><span data-stu-id="8c74b-132">Deploy the Skype for Business client in Office 365</span></span>](../../../SfbOnline/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365.md)