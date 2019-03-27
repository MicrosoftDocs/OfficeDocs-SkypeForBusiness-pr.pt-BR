---
title: Personalizar a instalação de cliente do Windows no Skype para Business Server
ms.reviewer: ''
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5c1a85f1-5ebb-48fb-acb7-3bf46decbf80
description: 'Resumo: Visão geral dos métodos de instalação e ferramentas para Skype para negócios.'
ms.openlocfilehash: d6458c1ec81ea67162a53107582249f301102ebd
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30890610"
---
# <a name="customize-windows-client-installation-in-skype-for-business-server"></a><span data-ttu-id="41d14-103">Personalizar a instalação de cliente do Windows no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="41d14-103">Customize Windows client installation in Skype for Business Server</span></span>
 
<span data-ttu-id="41d14-104">**Resumo:** Visão geral dos métodos de instalação e ferramentas para Skype para negócios.</span><span class="sxs-lookup"><span data-stu-id="41d14-104">**Summary:** Overview of installation methods and tools for Skype for Business.</span></span>
  
> [!NOTE]
> <span data-ttu-id="41d14-105">Para obter informações de instalação sobre Skype for Business que vem com o Office 365, consulte [Deploy a Skype para o cliente de negócios no Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span><span class="sxs-lookup"><span data-stu-id="41d14-105">For installation information about Skype for Business that comes with Office 365, see [Deploy the Skype for Business client in Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span></span> 
  
<span data-ttu-id="41d14-106">Os administradores de empresa podem personalizar a instalação de baseadas no Windows Installer (. msi) das versões de licença de volume do Skype para negócios usando os métodos discutidos nesta seção.</span><span class="sxs-lookup"><span data-stu-id="41d14-106">Enterprise administrators can customize the Windows Installer-based (.msi) installation of volume licensed versions of Skype for Business by using the methods discussed in this section.</span></span> <span data-ttu-id="41d14-107">Como nenhum única ferramenta fornece todas as opções de personalização, você provavelmente utilizará uma combinação desses métodos no seu Skype para implantação de negócios.</span><span class="sxs-lookup"><span data-stu-id="41d14-107">Because no single tool provides all customization options, you'll likely use a combination of these methods in your Skype for Business deployment.</span></span> <span data-ttu-id="41d14-108">Você poderá usar pelo menos as ferramentas descritas nas seguintes seções:</span><span class="sxs-lookup"><span data-stu-id="41d14-108">You might use the tools described in the following sections:</span></span>
  
- <span data-ttu-id="41d14-109">[Use a ferramenta de personalização do Office (OCT) no Skype para Business Server](use-the-office-customization-tool-oct.md) para personalizar opções de instalação e recursos para Skype para outros programas do Office e de negócios.</span><span class="sxs-lookup"><span data-stu-id="41d14-109">[Use the Office Customization Tool (OCT) in Skype for Business Server](use-the-office-customization-tool-oct.md) to customize setup options and features for Skype for Business and other Office programs.</span></span>
    
- <span data-ttu-id="41d14-110">[Usar config. XML para executar tarefas de instalação no Skype para Business Server](use-config-xml-to-perform-installation-tasks.md) para especificar o caminho do ponto de instalação de rede e executar a instalação silenciosa.</span><span class="sxs-lookup"><span data-stu-id="41d14-110">[Use Config.xml to perform installation tasks in Skype for Business Server](use-config-xml-to-perform-installation-tasks.md) to specify the path of the network installation point and perform silent installation.</span></span>
    
- <span data-ttu-id="41d14-111">[Use Setup Command-line options em Skype para Business Server](use-setup-command-line-options.md) para especificar o arquivo config. XML a ser usada durante a instalação.</span><span class="sxs-lookup"><span data-stu-id="41d14-111">[Use Setup command-line options in Skype for Business Server](use-setup-command-line-options.md) to specify the Config.xml file to use during installation.</span></span>
    
- <span data-ttu-id="41d14-112">[Configurar políticas de inicialização do cliente no Skype para Business Server](configure-client-bootstrapping-policies.md) usando o snap-in do MMC do Editor de objeto de diretiva de grupo.</span><span class="sxs-lookup"><span data-stu-id="41d14-112">[Configure client bootstrapping policies in Skype for Business Server](configure-client-bootstrapping-policies.md) by using the Group Policy Object Editor MMC snap-in.</span></span>
    
<span data-ttu-id="41d14-113">Provavelmente será outras opções que você vai querer configurar ao implantar o conjunto de produtos do Office.</span><span class="sxs-lookup"><span data-stu-id="41d14-113">There will probably be other options you'll want to configure as you deploy the Office suite of products.</span></span> <span data-ttu-id="41d14-114">Os tópicos desta seção apresentaremos uma visão geral dessas ferramentas de personalização e discutem as considerações específicas para Skype para negócios.</span><span class="sxs-lookup"><span data-stu-id="41d14-114">The topics in this section give an overview of these customization tools and discuss considerations specific to Skype for Business.</span></span> <span data-ttu-id="41d14-115">Estão inclusos links para a ajuda detalhada do Office referente a cada ferramenta.</span><span class="sxs-lookup"><span data-stu-id="41d14-115">Included are links to detailed Office help for each tool.</span></span> 
  

