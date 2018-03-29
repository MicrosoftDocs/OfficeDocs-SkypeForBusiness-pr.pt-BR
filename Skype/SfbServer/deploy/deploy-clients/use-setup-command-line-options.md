---
title: Usar opções de linha de comando Setup no Skype for Business Server 2015
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.date: 10/20/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
description: 'Resumo: Saiba sobre as operações de linha de comando Setup.exe na instalação do Office.'
ms.openlocfilehash: 0fa4f31750697f0bd0dbe87bbde025cbc7f530bd
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="use-setup-command-line-options-in-skype-for-business-server-2015"></a><span data-ttu-id="c0fb9-103">Usar opções de linha de comando Setup no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="c0fb9-103">Use Setup command-line options in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="c0fb9-104">**Resumo:** Saiba mais sobre as operações de linha de comando Setup.exe na instalação do Office.</span><span class="sxs-lookup"><span data-stu-id="c0fb9-104">**Summary:** Learn about Setup.exe command line operations in Office setup.</span></span>
  
<span data-ttu-id="c0fb9-105">A linha de comando Setup.exe é usada em poucas operações na instalação do Office.</span><span class="sxs-lookup"><span data-stu-id="c0fb9-105">The Setup.exe command line is used for very few operations in Office setup.</span></span> <span data-ttu-id="c0fb9-106">Em vez de usar as opções de linha de comando da instalação, você geralmente usará a ferramenta de personalização do Office e o arquivo config. XML para personalização de instalação e o recurso de produto.</span><span class="sxs-lookup"><span data-stu-id="c0fb9-106">Instead of using the Setup command-line options, you'll typically use the Office Customization Tool and the Config.xml file for product setup and feature customization.</span></span>
  
<span data-ttu-id="c0fb9-107">A linha de comando Setup.exe do Office reconhece as opções de linha de comando descritas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="c0fb9-107">The Office Setup.exe command line recognizes the command-line options described in the following table.</span></span>
  
<span data-ttu-id="c0fb9-108">**Opções de linha de comando de instalação do Office**</span><span class="sxs-lookup"><span data-stu-id="c0fb9-108">**Office Setup Command-Line Options**</span></span>

|<span data-ttu-id="c0fb9-109">**Opção de linha de comando de instalação**</span><span class="sxs-lookup"><span data-stu-id="c0fb9-109">**Setup Command-Line Option**</span></span>|<span data-ttu-id="c0fb9-110">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="c0fb9-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c0fb9-111">/admin</span><span class="sxs-lookup"><span data-stu-id="c0fb9-111">/admin</span></span>  <br/> |<span data-ttu-id="c0fb9-112">Executa a Ferramenta de personalização do Office para criar um arquivo de personalização de Setup (arquivo .msp).</span><span class="sxs-lookup"><span data-stu-id="c0fb9-112">Runs the Office Customization Tool to create a Setup customization file (.msp file).</span></span>  <br/> |
|<span data-ttu-id="c0fb9-113">/adminfile [caminho]</span><span class="sxs-lookup"><span data-stu-id="c0fb9-113">/adminfile [path]</span></span>  <br/> |<span data-ttu-id="c0fb9-p102">Aplica o arquivo de personalização de Setup à instalação. Você pode especificar um caminho de arquivo de personalização específico (arquivo .msp) ou a pasta onde você armazena os arquivos de personalização.</span><span class="sxs-lookup"><span data-stu-id="c0fb9-p102">Applies the specified Setup customization file to the installation. You can specify a path of a specific customization file (.msp file) or to the folder where you store customization files.</span></span>  <br/> |
|<span data-ttu-id="c0fb9-116">/config [caminho]</span><span class="sxs-lookup"><span data-stu-id="c0fb9-116">/config [path]</span></span>  <br/> |<span data-ttu-id="c0fb9-117">Especifica o arquivo Config.xml que o Setup usa durante a instalação.</span><span class="sxs-lookup"><span data-stu-id="c0fb9-117">Specifies the Config.xml file that Setup uses during the installation.</span></span> <span data-ttu-id="c0fb9-118">Use a opção /config para especificar o arquivo config. XML que é personalizado para Skype para instalações de negócios, por exemplo:`/config \\server\share\Skype15\Skype.WW\Config.xml`</span><span class="sxs-lookup"><span data-stu-id="c0fb9-118">Use the /config option to specify the Config.xml file you customized for Skype for Business installations, for example:  `/config \\server\share\Skype15\Skype.WW\Config.xml`</span></span> <br/> |
|<span data-ttu-id="c0fb9-119">/modify Skype</span><span class="sxs-lookup"><span data-stu-id="c0fb9-119">/modify Skype</span></span>  <br/> |<span data-ttu-id="c0fb9-120">Usado com um arquivo Config.xml modificado para executar o Setup em modo de manutenção e fazer alterações à instalação existente do Office.</span><span class="sxs-lookup"><span data-stu-id="c0fb9-120">Used with a modified Config.xml file to run Setup in maintenance mode and make changes to an existing Office installation.</span></span> <span data-ttu-id="c0fb9-121">Por exemplo, você pode usar o /Modify opção para adicionar ou remover Skype para recursos corporativos.</span><span class="sxs-lookup"><span data-stu-id="c0fb9-121">For example, you can use the /modify option to add or remove Skype for Business features.</span></span>  <br/> |
|<span data-ttu-id="c0fb9-122">/repair Skype</span><span class="sxs-lookup"><span data-stu-id="c0fb9-122">/repair Skype</span></span>  <br/> |<span data-ttu-id="c0fb9-123">Executa o Setup do computador do usuário para reparar Skype para negócios.</span><span class="sxs-lookup"><span data-stu-id="c0fb9-123">Runs Setup from the user's computer to repair Skype for Business.</span></span>  <br/> |
|<span data-ttu-id="c0fb9-124">/uninstall Skype</span><span class="sxs-lookup"><span data-stu-id="c0fb9-124">/uninstall Skype</span></span>  <br/> |<span data-ttu-id="c0fb9-125">Executa o Setup para remover Skype for Business do computador do usuário.</span><span class="sxs-lookup"><span data-stu-id="c0fb9-125">Runs Setup to remove Skype for Business from the user's computer.</span></span>  <br/> |
   
<span data-ttu-id="c0fb9-126">Para obter detalhes sobre como usar as opções de linha de comando de instalação, consulte [https://go.microsoft.com/fwlink/p/?linkid=267515](https://go.microsoft.com/fwlink/p/?linkid=267515).</span><span class="sxs-lookup"><span data-stu-id="c0fb9-126">For details about using the setup command-line options, see [https://go.microsoft.com/fwlink/p/?linkid=267515](https://go.microsoft.com/fwlink/p/?linkid=267515).</span></span> 
  

