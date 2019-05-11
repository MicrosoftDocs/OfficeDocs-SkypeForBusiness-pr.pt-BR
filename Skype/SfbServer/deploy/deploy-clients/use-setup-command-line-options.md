---
title: Use as opções de linha de comando de instalação com Skype para clientes corporativos
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
description: 'Resumo: Saiba sobre as operações de linha de comando Setup.exe na instalação do Office.'
ms.openlocfilehash: 924ecab4a53c6ec591416661bc98078e8e48381c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33895058"
---
# <a name="use-setup-command-line-options-with-skype-for-business-clients"></a><span data-ttu-id="4fc94-103">Use as opções de linha de comando de instalação com Skype para clientes corporativos</span><span class="sxs-lookup"><span data-stu-id="4fc94-103">Use Setup command-line options with Skype for Business clients</span></span>
 
<span data-ttu-id="4fc94-104">**Resumo:** Saiba mais sobre as operações de linha de comando Setup.exe na instalação do Office.</span><span class="sxs-lookup"><span data-stu-id="4fc94-104">**Summary:** Learn about Setup.exe command line operations in Office setup.</span></span>
  
<span data-ttu-id="4fc94-105">A linha de comando Setup.exe é usada em poucas operações na instalação do Office.</span><span class="sxs-lookup"><span data-stu-id="4fc94-105">The Setup.exe command line is used for very few operations in Office setup.</span></span> <span data-ttu-id="4fc94-106">Em vez de usar as opções de linha de comando da instalação, você geralmente usará a ferramenta de personalização do Office e o arquivo config. XML para personalização de instalação e o recurso de produto.</span><span class="sxs-lookup"><span data-stu-id="4fc94-106">Instead of using the Setup command-line options, you'll typically use the Office Customization Tool and the Config.xml file for product setup and feature customization.</span></span>
  
<span data-ttu-id="4fc94-107">A linha de comando Setup.exe do Office reconhece as opções de linha de comando descritas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="4fc94-107">The Office Setup.exe command line recognizes the command-line options described in the following table.</span></span>
  
<span data-ttu-id="4fc94-108">**Opções de linha de comando Setup do Office**</span><span class="sxs-lookup"><span data-stu-id="4fc94-108">**Office Setup Command-Line Options**</span></span>

|<span data-ttu-id="4fc94-109">**Opção de linha de comando Setup**</span><span class="sxs-lookup"><span data-stu-id="4fc94-109">**Setup Command-Line Option**</span></span>|<span data-ttu-id="4fc94-110">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="4fc94-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4fc94-111">/admin</span><span class="sxs-lookup"><span data-stu-id="4fc94-111">/admin</span></span>  <br/> |<span data-ttu-id="4fc94-112">Executa a Ferramenta de personalização do Office para criar um arquivo de personalização de Setup (arquivo .msp).</span><span class="sxs-lookup"><span data-stu-id="4fc94-112">Runs the Office Customization Tool to create a Setup customization file (.msp file).</span></span>  <br/> |
|<span data-ttu-id="4fc94-113">/adminfile [caminho]</span><span class="sxs-lookup"><span data-stu-id="4fc94-113">/adminfile [path]</span></span>  <br/> |<span data-ttu-id="4fc94-p102">Aplica o arquivo de personalização de Setup à instalação. Você pode especificar um caminho de arquivo de personalização específico (arquivo .msp) ou a pasta onde você armazena os arquivos de personalização.</span><span class="sxs-lookup"><span data-stu-id="4fc94-p102">Applies the specified Setup customization file to the installation. You can specify a path of a specific customization file (.msp file) or to the folder where you store customization files.</span></span>  <br/> |
|<span data-ttu-id="4fc94-116">/config [caminho]</span><span class="sxs-lookup"><span data-stu-id="4fc94-116">/config [path]</span></span>  <br/> |<span data-ttu-id="4fc94-117">Especifica o arquivo Config.xml que o Setup usa durante a instalação.</span><span class="sxs-lookup"><span data-stu-id="4fc94-117">Specifies the Config.xml file that Setup uses during the installation.</span></span> <span data-ttu-id="4fc94-118">Use a opção /config para especificar o arquivo config. XML que é personalizado para Skype para instalações de negócios, por exemplo:`/config \\server\share\Skype15\Skype.WW\Config.xml`</span><span class="sxs-lookup"><span data-stu-id="4fc94-118">Use the /config option to specify the Config.xml file you customized for Skype for Business installations, for example:  `/config \\server\share\Skype15\Skype.WW\Config.xml`</span></span> <br/> |
|<span data-ttu-id="4fc94-119">/modify Skype</span><span class="sxs-lookup"><span data-stu-id="4fc94-119">/modify Skype</span></span>  <br/> |<span data-ttu-id="4fc94-120">Usado com um arquivo Config.xml modificado para executar o Setup em modo de manutenção e fazer alterações à instalação existente do Office.</span><span class="sxs-lookup"><span data-stu-id="4fc94-120">Used with a modified Config.xml file to run Setup in maintenance mode and make changes to an existing Office installation.</span></span> <span data-ttu-id="4fc94-121">Por exemplo, você pode usar o /Modify opção para adicionar ou remover Skype para recursos corporativos.</span><span class="sxs-lookup"><span data-stu-id="4fc94-121">For example, you can use the /modify option to add or remove Skype for Business features.</span></span>  <br/> |
|<span data-ttu-id="4fc94-122">/repair Skype</span><span class="sxs-lookup"><span data-stu-id="4fc94-122">/repair Skype</span></span>  <br/> |<span data-ttu-id="4fc94-123">Executa o Setup do computador do usuário para reparar Skype para negócios.</span><span class="sxs-lookup"><span data-stu-id="4fc94-123">Runs Setup from the user's computer to repair Skype for Business.</span></span>  <br/> |
|<span data-ttu-id="4fc94-124">/uninstall Skype</span><span class="sxs-lookup"><span data-stu-id="4fc94-124">/uninstall Skype</span></span>  <br/> |<span data-ttu-id="4fc94-125">Executa o Setup para remover Skype for Business do computador do usuário.</span><span class="sxs-lookup"><span data-stu-id="4fc94-125">Runs Setup to remove Skype for Business from the user's computer.</span></span>  <br/> |
   


