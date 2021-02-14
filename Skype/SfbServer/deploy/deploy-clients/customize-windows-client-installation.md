---
title: Personalizar a instalação de cliente do Windows no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5c1a85f1-5ebb-48fb-acb7-3bf46decbf80
description: 'Resumo: Visão geral dos métodos e ferramentas de instalação do Skype for Business.'
ms.openlocfilehash: 001224369e46978e96ee063b31fcb546ef213a05
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805711"
---
# <a name="customize-windows-client-installation-in-skype-for-business-server"></a><span data-ttu-id="b08b5-103">Personalizar a instalação de cliente do Windows no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="b08b5-103">Customize Windows client installation in Skype for Business Server</span></span>
 
<span data-ttu-id="b08b5-104">**Resumo:** Visão geral dos métodos e ferramentas de instalação do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="b08b5-104">**Summary:** Overview of installation methods and tools for Skype for Business.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b08b5-105">Para obter informações de instalação sobre o Skype for Business que vem com o Microsoft 365 e o Office 365, confira Implantar o cliente Skype for Business no [Microsoft 365 ou Office 365.](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96)</span><span class="sxs-lookup"><span data-stu-id="b08b5-105">For installation information about Skype for Business that comes with Microsoft 365 and Office 365, see [Deploy the Skype for Business client in Microsoft 365 or Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span></span> 
  
<span data-ttu-id="b08b5-106">Os administradores corporativos podem personalizar a instalação baseada no Windows Installer (.msi) das versões licenciadas por volume do Skype for Business usando os métodos discutidos nesta seção.</span><span class="sxs-lookup"><span data-stu-id="b08b5-106">Enterprise administrators can customize the Windows Installer-based (.msi) installation of volume licensed versions of Skype for Business by using the methods discussed in this section.</span></span> <span data-ttu-id="b08b5-107">Como nenhuma ferramenta única fornece todas as opções de personalização, você provavelmente usará uma combinação desses métodos em sua implantação do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="b08b5-107">Because no single tool provides all customization options, you'll likely use a combination of these methods in your Skype for Business deployment.</span></span> <span data-ttu-id="b08b5-108">Você pode usar as ferramentas descritas nas seguintes seções:</span><span class="sxs-lookup"><span data-stu-id="b08b5-108">You might use the tools described in the following sections:</span></span>
  
- <span data-ttu-id="b08b5-109">[Use a Ferramenta de Personalização do Office (OCT)](use-the-office-customization-tool-oct.md) no Skype for Business Server para personalizar as opções e os recursos de instalação do Skype for Business e de outros programas do Office.</span><span class="sxs-lookup"><span data-stu-id="b08b5-109">[Use the Office Customization Tool (OCT) in Skype for Business Server](use-the-office-customization-tool-oct.md) to customize setup options and features for Skype for Business and other Office programs.</span></span>
    
- <span data-ttu-id="b08b5-110">[Use Config.xml para executar tarefas](use-config-xml-to-perform-installation-tasks.md) de instalação no Skype for Business Server para especificar o caminho do ponto de instalação de rede e executar a instalação silenciosa.</span><span class="sxs-lookup"><span data-stu-id="b08b5-110">[Use Config.xml to perform installation tasks in Skype for Business Server](use-config-xml-to-perform-installation-tasks.md) to specify the path of the network installation point and perform silent installation.</span></span>
    
- <span data-ttu-id="b08b5-111">[Use as opções de linha de comando de Instalação no Skype for Business Server](use-setup-command-line-options.md) para especificar o Config.xml arquivo a ser usado durante a instalação.</span><span class="sxs-lookup"><span data-stu-id="b08b5-111">[Use Setup command-line options in Skype for Business Server](use-setup-command-line-options.md) to specify the Config.xml file to use during installation.</span></span>
    
- <span data-ttu-id="b08b5-112">[Configure as políticas de inicialização do cliente no Skype for Business Server](configure-client-bootstrapping-policies.md) usando o snap-in MMC do Editor de Objeto de Diretiva de Grupo.</span><span class="sxs-lookup"><span data-stu-id="b08b5-112">[Configure client bootstrapping policies in Skype for Business Server](configure-client-bootstrapping-policies.md) by using the Group Policy Object Editor MMC snap-in.</span></span>
    
<span data-ttu-id="b08b5-113">Provavelmente, haverá outras opções que você vai querer configurar ao implantar o pacote de produtos do Office.</span><span class="sxs-lookup"><span data-stu-id="b08b5-113">There will probably be other options you'll want to configure as you deploy the Office suite of products.</span></span> <span data-ttu-id="b08b5-114">Os tópicos desta seção dão uma visão geral dessas ferramentas de personalização e discutem considerações específicas do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="b08b5-114">The topics in this section give an overview of these customization tools and discuss considerations specific to Skype for Business.</span></span> <span data-ttu-id="b08b5-115">Estão inclusos links para a ajuda detalhada do Office referente a cada ferramenta.</span><span class="sxs-lookup"><span data-stu-id="b08b5-115">Included are links to detailed Office help for each tool.</span></span> 
  

