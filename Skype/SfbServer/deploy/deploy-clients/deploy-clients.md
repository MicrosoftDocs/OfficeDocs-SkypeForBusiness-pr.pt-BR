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
description: 'Summary: Overview of enterprise client installation methods for Skype for Business.'
ms.openlocfilehash: d41ce5b2fe9b4717a9af78fb3072ae0da48b72ec
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-clients-for-skype-for-business-server-2015"></a><span data-ttu-id="94c2a-103">Implantar clientes do Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="94c2a-103">Deploy clients for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="94c2a-104">**Summary:** Overview of enterprise client installation methods for Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="94c2a-104">**Summary:** Overview of enterprise client installation methods for Skype for Business.</span></span>
  
<span data-ttu-id="94c2a-105">How you deploy Skype for Business to your users depends on whether you purchased Skype for Business as part of an Office 365 plan or you purchased a volume licensed version of Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="94c2a-105">How you deploy Skype for Business to your users depends on whether you purchased Skype for Business as part of an Office 365 plan or you purchased a volume licensed version of Skype for Business.</span></span> 
  
- <span data-ttu-id="94c2a-106">**Office 365** If you have an Office 365 plan that includes Skype for Business, the installation technology that's used is called Click-to-Run.</span><span class="sxs-lookup"><span data-stu-id="94c2a-106">**Office 365** If you have an Office 365 plan that includes Skype for Business, the installation technology that's used is called Click-to-Run.</span></span> <span data-ttu-id="94c2a-107">With Office 365, you can let your users install Skype for Business for themselves from the Office 365 portal.</span><span class="sxs-lookup"><span data-stu-id="94c2a-107">With Office 365, you can let your users install Skype for Business for themselves from the Office 365 portal.</span></span> <span data-ttu-id="94c2a-108">Or, you can deploy Skype for Business to your users by downloading the software to your local network and then using your existing software deployment tools, such as with Microsoft System Center Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="94c2a-108">Or, you can deploy Skype for Business to your users by downloading the software to your local network and then using your existing software deployment tools, such as with Microsoft System Center Configuration Manager.</span></span> <span data-ttu-id="94c2a-109">For installation information about Skype for Business that comes with Office 365, see [Deploy the Skype for Business client in Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span><span class="sxs-lookup"><span data-stu-id="94c2a-109">For installation information about Skype for Business that comes with Office 365, see [Deploy the Skype for Business client in Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span></span>
    
- <span data-ttu-id="94c2a-110">**Volume licensed** If you have a volume licensed version of Skype for Business, the installation technology that's used is Windows Installer (MSI).</span><span class="sxs-lookup"><span data-stu-id="94c2a-110">**Volume licensed** If you have a volume licensed version of Skype for Business, the installation technology that's used is Windows Installer (MSI).</span></span> <span data-ttu-id="94c2a-111">MSI Windows Installer é um pacote de instalação com base no Windows Installer que consiste em vários arquivos MSI.</span><span class="sxs-lookup"><span data-stu-id="94c2a-111">MSI Windows Installer is a Windows Installer-based installation package that consists of multiple MSI files.</span></span> <span data-ttu-id="94c2a-112">Um pacote de núcleo MSI de linguagem neutra é combinado com um ou mais pacotes de linguagem específica para fazer um produto completo.</span><span class="sxs-lookup"><span data-stu-id="94c2a-112">A language-neutral core MSI package is combined with one or more language-specific packages to make a complete product.</span></span> <span data-ttu-id="94c2a-113">A instalação reúne os pacotes individuais e efetua a personalização e tarefas de manutenção durante e após a instalação do Office nos computadores dos usuários.</span><span class="sxs-lookup"><span data-stu-id="94c2a-113">Setup assembles the individual packages and performs customization and maintenance tasks during and after installation of Office on users' computers.</span></span>
    
<span data-ttu-id="94c2a-114">Os tópicos nesta seção descrevem como utilizar e personalizar o  Windows Installer para implantar o cliente  em seus usuários através de procedimentos normais.</span><span class="sxs-lookup"><span data-stu-id="94c2a-114">The topics in this section describe how to use and customize the Windows Installer to deploy the  client to your users through your normal procedures.</span></span>
  
> [!NOTE]
> <span data-ttu-id="94c2a-115">O Suplemento de Reunião Online para o , que oferece suporte ao gerenciamento de reuniões a partir do cliente de mensagens e colaboração do Outlook, é instalado automaticamente com o .</span><span class="sxs-lookup"><span data-stu-id="94c2a-115">The Online meeting Add-in for , which supports meeting management from within the Outlook messaging and collaboration client, installs automatically with .</span></span> 
  
> [!NOTE]
> <span data-ttu-id="94c2a-116">O programa de instalação do  não desinstala versões anteriores do Lync ou Office Communicator.</span><span class="sxs-lookup"><span data-stu-id="94c2a-116">The  setup program does not uninstall previous versions of Lync or Office Communicator.</span></span> <span data-ttu-id="94c2a-117">O cliente  instala lado a lado com outros clientes Lync ou Office Communicator.</span><span class="sxs-lookup"><span data-stu-id="94c2a-117">The  client installs side-by-side with other Lync or Office Communicator clients.</span></span> 
  
## <a name="installing-windows-clients"></a><span data-ttu-id="94c2a-118">Instalação de Clientes Windows</span><span class="sxs-lookup"><span data-stu-id="94c2a-118">Installing Windows Clients</span></span>

- [<span data-ttu-id="94c2a-119">Personalizar instalação do cliente no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="94c2a-119">Customize client installation in Skype for Business Server 2015</span></span>](customize-windows-client-installation.md)
    
- [<span data-ttu-id="94c2a-120">Configurar a experiência do cliente com o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="94c2a-120">Configure the client experience with Skype for Business</span></span>](configure-the-client-experience.md)
    
- [<span data-ttu-id="94c2a-121">Configurar lista de contatos Inteligente no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="94c2a-121">Configure Smart contacts list in Skype for Business Server</span></span>](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a><span data-ttu-id="94c2a-122">Instalação de Clientes do Dispositivo</span><span class="sxs-lookup"><span data-stu-id="94c2a-122">Installing Device Clients</span></span>

- [<span data-ttu-id="94c2a-123">Skype for Business Server 2015: Instalar e testar o Skype for Business para Windows Phone</span><span class="sxs-lookup"><span data-stu-id="94c2a-123">Install and test Skype for Business for Windows Phone</span></span>](windows-phone.md)
    
- [<span data-ttu-id="94c2a-124">Instalar e testar o Skype for Business para iOS</span><span class="sxs-lookup"><span data-stu-id="94c2a-124">Install and test Skype for Business for iOS</span></span>](ios.md)
    
- [<span data-ttu-id="94c2a-125">Implantar Sistema de Salas do Skype no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="94c2a-125">Deploy Skype Room System in Skype for Business Server</span></span>](deploy-skype-room-system.md)
    
- [<span data-ttu-id="94c2a-126">Implantar o Skype Room Systems versão 2</span><span class="sxs-lookup"><span data-stu-id="94c2a-126">Deploy Skype Room Systems v2</span></span>](room-systems-v2.md)
    
- [<span data-ttu-id="94c2a-127">Implantar o plug-in VDI do Lync com o Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="94c2a-127">Deploy the Lync VDI plug-in with Skype for Business Server 2015</span></span>](deploy-the-lync-vdi-plug-in.md)
    
- [<span data-ttu-id="94c2a-128">Implantar clientes para download da Web no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="94c2a-128">Deploy Web downloadable clients in Skype for Business Server 2015</span></span>](deploy-web-downloadable-clients.md)
    
- [<span data-ttu-id="94c2a-129">Personalizar a experiência do cliente Mac no Skype for Business</span><span class="sxs-lookup"><span data-stu-id="94c2a-129">Customize the Mac client experience in Skype for Business</span></span>](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a><span data-ttu-id="94c2a-130">Consulte também</span><span class="sxs-lookup"><span data-stu-id="94c2a-130">See also</span></span>

#### 

[<span data-ttu-id="94c2a-131">Implantar o cliente Skype for Business em sua organizaçãohttps://support.officeppe.com/pt-br/article/Deploy-the-Skype-for-Business-client-for-your-organization-8c563b81-22c9-4024-9efe-9fe28c7bbc96?ui=pt-BR&rs=pt-BR&ad=BR</span><span class="sxs-lookup"><span data-stu-id="94c2a-131">Deploy the Skype for Business client for your organizationhttps://support.officeppe.com/en-us/article/Deploy-the-Skype-for-Business-client-for-your-organization-8c563b81-22c9-4024-9efe-9fe28c7bbc96?ui=en-US&rs=en-US&ad=US</span></span>](https://support.officeppe.com/en-us/article/Deploy-the-Skype-for-Business-client-for-your-organization-8c563b81-22c9-4024-9efe-9fe28c7bbc96?ui=en-US&amp;rs=en-US&amp;ad=US)

