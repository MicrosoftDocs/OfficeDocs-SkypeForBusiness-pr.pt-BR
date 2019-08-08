---
title: Personalizar a instalação do Windows Client no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5c1a85f1-5ebb-48fb-acb7-3bf46decbf80
description: 'Resumo: visão geral dos métodos e das ferramentas de instalação do Skype for Business.'
ms.openlocfilehash: 16c460d8fbbafd98a980c69bc0cd7638108ea164
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234180"
---
# <a name="customize-windows-client-installation-in-skype-for-business-server"></a><span data-ttu-id="5b8ef-103">Personalizar a instalação do Windows Client no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="5b8ef-103">Customize Windows client installation in Skype for Business Server</span></span>
 
<span data-ttu-id="5b8ef-104">**Resumo:** Visão geral dos métodos e das ferramentas de instalação do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="5b8ef-104">**Summary:** Overview of installation methods and tools for Skype for Business.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5b8ef-105">Para obter informações de instalação sobre o Skype for Business que vem com o Office 365, consulte [implantar o cliente Skype for Business no Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span><span class="sxs-lookup"><span data-stu-id="5b8ef-105">For installation information about Skype for Business that comes with Office 365, see [Deploy the Skype for Business client in Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span></span> 
  
<span data-ttu-id="5b8ef-106">Os administradores corporativos podem personalizar a instalação do Skype for Business com base no Windows Installer (. msi) usando os métodos discutidos nesta seção.</span><span class="sxs-lookup"><span data-stu-id="5b8ef-106">Enterprise administrators can customize the Windows Installer-based (.msi) installation of volume licensed versions of Skype for Business by using the methods discussed in this section.</span></span> <span data-ttu-id="5b8ef-107">Como nenhuma ferramenta tem todas as opções de personalização, você provavelmente usará uma combinação desses métodos na sua implantação do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="5b8ef-107">Because no single tool provides all customization options, you'll likely use a combination of these methods in your Skype for Business deployment.</span></span> <span data-ttu-id="5b8ef-108">Você poderá usar pelo menos as ferramentas descritas nas seguintes seções:</span><span class="sxs-lookup"><span data-stu-id="5b8ef-108">You might use the tools described in the following sections:</span></span>
  
- <span data-ttu-id="5b8ef-109">[Use a ferramenta de personalização do Office (OCT) no Skype for Business Server](use-the-office-customization-tool-oct.md) para personalizar opções e recursos de configuração do Skype for Business e outros programas do Office.</span><span class="sxs-lookup"><span data-stu-id="5b8ef-109">[Use the Office Customization Tool (OCT) in Skype for Business Server](use-the-office-customization-tool-oct.md) to customize setup options and features for Skype for Business and other Office programs.</span></span>
    
- <span data-ttu-id="5b8ef-110">[Use config. xml para executar tarefas de instalação no Skype for Business Server](use-config-xml-to-perform-installation-tasks.md) para especificar o caminho do ponto de instalação de rede e executar a instalação silenciosa.</span><span class="sxs-lookup"><span data-stu-id="5b8ef-110">[Use Config.xml to perform installation tasks in Skype for Business Server](use-config-xml-to-perform-installation-tasks.md) to specify the path of the network installation point and perform silent installation.</span></span>
    
- <span data-ttu-id="5b8ef-111">[Use as opções de linha de comando de configuração no Skype for Business Server](use-setup-command-line-options.md) para especificar o arquivo config. XML a ser usado durante a instalação.</span><span class="sxs-lookup"><span data-stu-id="5b8ef-111">[Use Setup command-line options in Skype for Business Server](use-setup-command-line-options.md) to specify the Config.xml file to use during installation.</span></span>
    
- <span data-ttu-id="5b8ef-112">[Configure as políticas de inicialização do cliente no Skype for Business Server](configure-client-bootstrapping-policies.md) usando o snap-in do MMC do editor de objeto de política de grupo.</span><span class="sxs-lookup"><span data-stu-id="5b8ef-112">[Configure client bootstrapping policies in Skype for Business Server](configure-client-bootstrapping-policies.md) by using the Group Policy Object Editor MMC snap-in.</span></span>
    
<span data-ttu-id="5b8ef-113">Provavelmente, haverá outras opções que você vai querer configurar ao implantar o pacote de produtos do Office.</span><span class="sxs-lookup"><span data-stu-id="5b8ef-113">There will probably be other options you'll want to configure as you deploy the Office suite of products.</span></span> <span data-ttu-id="5b8ef-114">Os tópicos desta seção fornecem uma visão geral dessas ferramentas de personalização e discutem considerações específicas do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="5b8ef-114">The topics in this section give an overview of these customization tools and discuss considerations specific to Skype for Business.</span></span> <span data-ttu-id="5b8ef-115">Estão inclusos links para a ajuda detalhada do Office referente a cada ferramenta.</span><span class="sxs-lookup"><span data-stu-id="5b8ef-115">Included are links to detailed Office help for each tool.</span></span> 
  

