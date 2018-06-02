---
title: Implantar clientes do Skype for Business Server 2015
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.date: 2/6/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
description: 'Resumo: Visão geral dos métodos de instalação de cliente enterprise para Skype para negócios.'
ms.openlocfilehash: 4c1253613befd5bf71add33b7ab9cab826d4a490
ms.sourcegitcommit: a5b8b0a1e5ae5eb718e296ca6df6687368ee9174
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/02/2018
ms.locfileid: "19546466"
---
# <a name="deploy-clients-for-skype-for-business-server-2015"></a><span data-ttu-id="a4c69-103">Implantar clientes do Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="a4c69-103">Deploy clients for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="a4c69-104">**Resumo:** Visão geral dos métodos de instalação de cliente enterprise para Skype para negócios.</span><span class="sxs-lookup"><span data-stu-id="a4c69-104">**Summary:** Overview of enterprise client installation methods for Skype for Business.</span></span>
  
<span data-ttu-id="a4c69-105">Como você implanta Skype for Business para seus usuários depende se você comprou Skype para negócios como parte de um plano do Office 365 ou você comprou uma versão licenciada do volume do Skype para negócios.</span><span class="sxs-lookup"><span data-stu-id="a4c69-105">How you deploy Skype for Business to your users depends on whether you purchased Skype for Business as part of an Office 365 plan or you purchased a volume licensed version of Skype for Business.</span></span> 
  
- <span data-ttu-id="a4c69-106">**Office 365** Se você tiver um plano do Office 365 que inclui Skype para a empresa, a tecnologia de instalação que é usada é chamada Click-to-Run.</span><span class="sxs-lookup"><span data-stu-id="a4c69-106">**Office 365** If you have an Office 365 plan that includes Skype for Business, the installation technology that's used is called Click-to-Run.</span></span> <span data-ttu-id="a4c69-107">Com o Office 365, você pode permitir que os usuários instalar Skype for Business para si próprios do portal do Office 365.</span><span class="sxs-lookup"><span data-stu-id="a4c69-107">With Office 365, you can let your users install Skype for Business for themselves from the Office 365 portal.</span></span> <span data-ttu-id="a4c69-108">Ou então, você pode implantar Skype for Business para seus usuários baixando o software em sua rede local e, em seguida, usando suas ferramentas de implantação de software existentes, tais como com o Microsoft System Center Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="a4c69-108">Or, you can deploy Skype for Business to your users by downloading the software to your local network and then using your existing software deployment tools, such as with Microsoft System Center Configuration Manager.</span></span> <span data-ttu-id="a4c69-109">Para obter informações de instalação sobre Skype for Business que vem com o Office 365, consulte [Deploy a Skype para o cliente de negócios no Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span><span class="sxs-lookup"><span data-stu-id="a4c69-109">For installation information about Skype for Business that comes with Office 365, see [Deploy the Skype for Business client in Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span></span>
    
- <span data-ttu-id="a4c69-110">**Licença de volume** Se você tiver uma versão de licença de volume do Skype para a empresa, a tecnologia de instalação que é usada é o Windows Installer (MSI).</span><span class="sxs-lookup"><span data-stu-id="a4c69-110">**Volume licensed** If you have a volume licensed version of Skype for Business, the installation technology that's used is Windows Installer (MSI).</span></span> <span data-ttu-id="a4c69-111">Um pacote de instalação baseada no Windows Installer consiste em vários arquivos MSI.</span><span class="sxs-lookup"><span data-stu-id="a4c69-111">A Windows Installer-based installation package consists of multiple MSI files.</span></span> <span data-ttu-id="a4c69-112">Um pacote de núcleo MSI de linguagem neutra é combinado com um ou mais pacotes de linguagem específica para fazer um produto completo.</span><span class="sxs-lookup"><span data-stu-id="a4c69-112">A language-neutral core MSI package is combined with one or more language-specific packages to make a complete product.</span></span> <span data-ttu-id="a4c69-113">A instalação reúne os pacotes individuais e efetua a personalização e tarefas de manutenção durante e após a instalação do Office nos computadores dos usuários.</span><span class="sxs-lookup"><span data-stu-id="a4c69-113">Setup assembles the individual packages and performs customization and maintenance tasks during and after installation of Office on users' computers.</span></span>
    
<span data-ttu-id="a4c69-114">Os tópicos desta seção descrevem como usar e personalizar o Windows Installer para implantar o Skype para o cliente de negócios para seus usuários por meio de seus procedimentos normais.</span><span class="sxs-lookup"><span data-stu-id="a4c69-114">The topics in this section describe how to use and customize the Windows Installer to deploy the Skype for Business client to your users through your normal procedures.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a4c69-115">O Online meeting Add-in para Skype para os negócios, que suporta o gerenciamento de dentro do Outlook de reuniões cliente de mensagens e colaboração, instala automaticamente com o Skype para negócios.</span><span class="sxs-lookup"><span data-stu-id="a4c69-115">The Online meeting Add-in for Skype for Business, which supports meeting management from within the Outlook messaging and collaboration client, installs automatically with Skype for Business.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="a4c69-116">O programa de instalação do Office 365 não desinstala versões anteriores do Lync ou Office Communicator.</span><span class="sxs-lookup"><span data-stu-id="a4c69-116">The Office 365 setup program does not uninstall previous versions of Lync or Office Communicator.</span></span> <span data-ttu-id="a4c69-117">O Skype para Business client instala lado a lado com outros clientes do Lync ou Office Communicator.</span><span class="sxs-lookup"><span data-stu-id="a4c69-117">The Skype for Business client installs side-by-side with other Lync or Office Communicator clients.</span></span> 
  
## <a name="installing-windows-clients"></a><span data-ttu-id="a4c69-118">Instalando clientes Windows</span><span class="sxs-lookup"><span data-stu-id="a4c69-118">Installing Windows clients</span></span>

- [<span data-ttu-id="a4c69-119">Personalizar a instalação de cliente do Windows no Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="a4c69-119">Customize Windows client installation in Skype for Business Server 2015</span></span>](customize-windows-client-installation.md)
    
- [<span data-ttu-id="a4c69-120">Configurar a experiência do cliente com Skype para negócios</span><span class="sxs-lookup"><span data-stu-id="a4c69-120">Configure the client experience with Skype for Business</span></span>](configure-the-client-experience.md)
    
- [<span data-ttu-id="a4c69-121">Configurar a lista de contatos inteligente no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="a4c69-121">Configure Smart contacts list in Skype for Business Server</span></span>](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a><span data-ttu-id="a4c69-122">Instalando clientes de dispositivos</span><span class="sxs-lookup"><span data-stu-id="a4c69-122">Installing device clients</span></span>

- [<span data-ttu-id="a4c69-123">Instalar e testar o Skype para Business para Windows Phone</span><span class="sxs-lookup"><span data-stu-id="a4c69-123">Install and test Skype for Business for Windows Phone</span></span>](windows-phone.md)
    
- [<span data-ttu-id="a4c69-124">Instalar e testar o Skype for Business para iOS</span><span class="sxs-lookup"><span data-stu-id="a4c69-124">Install and test Skype for Business for iOS</span></span>](ios.md)
    
- [<span data-ttu-id="a4c69-125">Implantar o sistema de sala Skype no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="a4c69-125">Deploy Skype Room System in Skype for Business Server</span></span>](deploy-skype-room-system.md)
    
- [<span data-ttu-id="a4c69-126">Implantar Skype sala v2 de sistemas</span><span class="sxs-lookup"><span data-stu-id="a4c69-126">Deploy Skype Room Systems v2</span></span>](room-systems-v2.md)
    
- [<span data-ttu-id="a4c69-127">Implantar o Lync VDI plug-in com Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="a4c69-127">Deploy the Lync VDI plug-in with Skype for Business Server 2015</span></span>](deploy-the-lync-vdi-plug-in.md)
    
- [<span data-ttu-id="a4c69-128">Implantar clientes para download da Web no Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="a4c69-128">Deploy Web downloadable clients in Skype for Business Server 2015</span></span>](deploy-web-downloadable-clients.md)
    
- [<span data-ttu-id="a4c69-129">Personalizar a experiência do cliente do Mac no Skype para negócios</span><span class="sxs-lookup"><span data-stu-id="a4c69-129">Customize the Mac client experience in Skype for Business</span></span>](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a><span data-ttu-id="a4c69-130">Consulte também</span><span class="sxs-lookup"><span data-stu-id="a4c69-130">See also</span></span>

[<span data-ttu-id="a4c69-131">Implantar o Skype para o cliente de negócios no Office 365</span><span class="sxs-lookup"><span data-stu-id="a4c69-131">Deploy the Skype for Business client in Office 365</span></span>](../../../SfbOnline/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365.md)