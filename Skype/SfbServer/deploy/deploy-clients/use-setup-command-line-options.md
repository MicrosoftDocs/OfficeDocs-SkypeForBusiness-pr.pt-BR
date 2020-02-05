---
title: Usar as opções de linha de comando de configuração com os clientes do Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
description: 'Resumo: Saiba mais sobre as operações de linha de comando Setup. exe na instalação do Office.'
ms.openlocfilehash: 68add6e2744e9648db49508519c14e64b4e6aeef
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768624"
---
# <a name="use-setup-command-line-options-with-skype-for-business-clients"></a><span data-ttu-id="1f21f-103">Usar as opções de linha de comando de configuração com os clientes do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="1f21f-103">Use Setup command-line options with Skype for Business clients</span></span>
 
<span data-ttu-id="1f21f-104">**Resumo:** Saiba mais sobre as operações de linha de comando Setup. exe na instalação do Office.</span><span class="sxs-lookup"><span data-stu-id="1f21f-104">**Summary:** Learn about Setup.exe command line operations in Office setup.</span></span>
  
<span data-ttu-id="1f21f-105">A linha de comando Setup.exe é usada em poucas operações na instalação do Office.</span><span class="sxs-lookup"><span data-stu-id="1f21f-105">The Setup.exe command line is used for very few operations in Office setup.</span></span> <span data-ttu-id="1f21f-106">Em vez de usar as opções de linha de comando de configuração, você geralmente usará a ferramenta de personalização do Office e o arquivo config. xml para configuração do produto e personalização de recursos.</span><span class="sxs-lookup"><span data-stu-id="1f21f-106">Instead of using the Setup command-line options, you'll typically use the Office Customization Tool and the Config.xml file for product setup and feature customization.</span></span>
  
<span data-ttu-id="1f21f-107">A linha de comando Setup.exe do Office reconhece as opções de linha de comando descritas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="1f21f-107">The Office Setup.exe command line recognizes the command-line options described in the following table.</span></span>
  
<span data-ttu-id="1f21f-108">**Opções de linha de comando Setup do Office**</span><span class="sxs-lookup"><span data-stu-id="1f21f-108">**Office Setup Command-Line Options**</span></span>

|<span data-ttu-id="1f21f-109">**Opção de linha de comando Setup**</span><span class="sxs-lookup"><span data-stu-id="1f21f-109">**Setup Command-Line Option**</span></span>|<span data-ttu-id="1f21f-110">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="1f21f-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1f21f-111">/admin</span><span class="sxs-lookup"><span data-stu-id="1f21f-111">/admin</span></span>  <br/> |<span data-ttu-id="1f21f-112">Executa a Ferramenta de personalização do Office para criar um arquivo de personalização de Setup (arquivo .msp).</span><span class="sxs-lookup"><span data-stu-id="1f21f-112">Runs the Office Customization Tool to create a Setup customization file (.msp file).</span></span>  <br/> |
|<span data-ttu-id="1f21f-113">/adminfile [caminho]</span><span class="sxs-lookup"><span data-stu-id="1f21f-113">/adminfile [path]</span></span>  <br/> |<span data-ttu-id="1f21f-p102">Aplica o arquivo de personalização de Setup à instalação. Você pode especificar um caminho de arquivo de personalização específico (arquivo .msp) ou a pasta onde você armazena os arquivos de personalização.</span><span class="sxs-lookup"><span data-stu-id="1f21f-p102">Applies the specified Setup customization file to the installation. You can specify a path of a specific customization file (.msp file) or to the folder where you store customization files.</span></span>  <br/> |
|<span data-ttu-id="1f21f-116">/config [caminho]</span><span class="sxs-lookup"><span data-stu-id="1f21f-116">/config [path]</span></span>  <br/> |<span data-ttu-id="1f21f-117">Especifica o arquivo Config.xml que o Setup usa durante a instalação.</span><span class="sxs-lookup"><span data-stu-id="1f21f-117">Specifies the Config.xml file that Setup uses during the installation.</span></span> <span data-ttu-id="1f21f-118">Use a opção/config para especificar o arquivo config. xml personalizado para instalações do Skype for Business, por exemplo:`/config \\server\share\Skype15\Skype.WW\Config.xml`</span><span class="sxs-lookup"><span data-stu-id="1f21f-118">Use the /config option to specify the Config.xml file you customized for Skype for Business installations, for example:  `/config \\server\share\Skype15\Skype.WW\Config.xml`</span></span> <br/> |
|<span data-ttu-id="1f21f-119">/modify Skype</span><span class="sxs-lookup"><span data-stu-id="1f21f-119">/modify Skype</span></span>  <br/> |<span data-ttu-id="1f21f-120">Usado com um arquivo Config.xml modificado para executar o Setup em modo de manutenção e fazer alterações à instalação existente do Office.</span><span class="sxs-lookup"><span data-stu-id="1f21f-120">Used with a modified Config.xml file to run Setup in maintenance mode and make changes to an existing Office installation.</span></span> <span data-ttu-id="1f21f-121">Por exemplo, você pode usar a opção/Modify para adicionar ou remover recursos do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="1f21f-121">For example, you can use the /modify option to add or remove Skype for Business features.</span></span>  <br/> |
|<span data-ttu-id="1f21f-122">/repair Skype</span><span class="sxs-lookup"><span data-stu-id="1f21f-122">/repair Skype</span></span>  <br/> |<span data-ttu-id="1f21f-123">Executa a instalação a partir do computador do usuário para reparar o Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="1f21f-123">Runs Setup from the user's computer to repair Skype for Business.</span></span>  <br/> |
|<span data-ttu-id="1f21f-124">/uninstall Skype</span><span class="sxs-lookup"><span data-stu-id="1f21f-124">/uninstall Skype</span></span>  <br/> |<span data-ttu-id="1f21f-125">Executa a instalação para remover o Skype for Business do computador do usuário.</span><span class="sxs-lookup"><span data-stu-id="1f21f-125">Runs Setup to remove Skype for Business from the user's computer.</span></span>  <br/> |
   


