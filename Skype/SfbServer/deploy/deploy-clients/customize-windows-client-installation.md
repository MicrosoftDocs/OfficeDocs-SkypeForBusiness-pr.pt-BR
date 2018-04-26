---
title: Personalizar instalação do cliente no Skype for Business Server 2015
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.date: 10/20/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5c1a85f1-5ebb-48fb-acb7-3bf46decbf80
description: 'Summary: Overview of installation methods and tools for Skype for Business.'
ms.openlocfilehash: 8f74f3930e296d8f49eca4bf2a097c88883d7981
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="customize-windows-client-installation-in-skype-for-business-server-2015"></a><span data-ttu-id="234e0-103">Personalizar instalação do cliente no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="234e0-103">Customize client installation in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="234e0-104">**Summary:** Overview of installation methods and tools for Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="234e0-104">**Summary:** Overview of installation methods and tools for Skype for Business.</span></span>
  
> [!NOTE]
> <span data-ttu-id="234e0-105">For installation information about Skype for Business that comes with Office 365, see [Deploy the Skype for Business client in Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span><span class="sxs-lookup"><span data-stu-id="234e0-105">For installation information about Skype for Business that comes with Office 365, see [Deploy the Skype for Business client in Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span></span> 
  
<span data-ttu-id="234e0-106">Os administradores corporativos podem personalizar a instalação pelo Windows Installer (.msi) do  usando os métodos abordados nesta seção.</span><span class="sxs-lookup"><span data-stu-id="234e0-106">Enterprise administrators can customize the  Windows Installer-based (.msi) installation by using the methods discussed in this section.</span></span> <span data-ttu-id="234e0-107">Como nenhuma ferramenta individual oferece todas as opções de personalização, você provavelmente usará uma combinação desses métodos em sua implantação do .</span><span class="sxs-lookup"><span data-stu-id="234e0-107">Because no single tool provides all customization options, you’ll likely use a combination of these methods in your  deployment.</span></span> <span data-ttu-id="234e0-108">Você poderá usar pelo menos as ferramentas descritas nas seguintes seções:</span><span class="sxs-lookup"><span data-stu-id="234e0-108">You might use the tools described in the following sections:</span></span>
  
- <span data-ttu-id="234e0-109">[Use the Office Customization Tool (OCT) in Skype for Business Server 2015](use-the-office-customization-tool-oct.md) to customize setup options and features for Skype for Business and other Office programs.</span><span class="sxs-lookup"><span data-stu-id="234e0-109">[Use the Office Customization Tool (OCT) in Skype for Business Server 2015](use-the-office-customization-tool-oct.md) to customize setup options and features for Skype for Business and other Office programs.</span></span>
    
- <span data-ttu-id="234e0-110">[Use Config.xml to perform installation tasks in Skype for Business Server 2015](use-config-xml-to-perform-installation-tasks.md) to specify the path of the network installation point and perform silent installation.</span><span class="sxs-lookup"><span data-stu-id="234e0-110">[Use Config.xml to perform installation tasks in Skype for Business Server 2015](use-config-xml-to-perform-installation-tasks.md) to specify the path of the network installation point and perform silent installation.</span></span>
    
- <span data-ttu-id="234e0-111">[Use Setup command-line options in Skype for Business Server 2015](use-setup-command-line-options.md) to specify the Config.xml file to use during installation.</span><span class="sxs-lookup"><span data-stu-id="234e0-111">[Use Setup command-line options in Skype for Business Server 2015](use-setup-command-line-options.md) to specify the Config.xml file to use during installation.</span></span>
    
- <span data-ttu-id="234e0-112">[Configure client bootstrapping policies in Skype for Business Server 2015](configure-client-bootstrapping-policies.md) by using the Group Policy Object Editor MMC snap-in.</span><span class="sxs-lookup"><span data-stu-id="234e0-112">[Configure client bootstrapping policies in Skype for Business Server 2015](configure-client-bootstrapping-policies.md) by using the Group Policy Object Editor MMC snap-in.</span></span>
    
<span data-ttu-id="234e0-113">Provavelmente, haverá outras opções que você desejará configurar ao implantar o pacote de produtos do Office.</span><span class="sxs-lookup"><span data-stu-id="234e0-113">There will probably be other options you’ll want to configure as you deploy the Office suite of products.</span></span> <span data-ttu-id="234e0-114">Os tópicos desta seção oferecem uma visão geral dessas ferramentas de personalização e abordam considerações específicas do .</span><span class="sxs-lookup"><span data-stu-id="234e0-114">The topics in this section give an overview of these customization tools and discuss considerations specific to .</span></span> <span data-ttu-id="234e0-115">Estão inclusos links para a ajuda detalhada do Office referente a cada ferramenta.</span><span class="sxs-lookup"><span data-stu-id="234e0-115">Included are links to detailed Office help for each tool.</span></span> 
  

