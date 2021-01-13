---
title: Usar opções de linha de comando de Instalação com clientes do Skype for Business
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
ms.assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
description: 'Resumo: saiba mais sobre Setup.exe de linha de comando na configuração do Office.'
ms.openlocfilehash: 042ba2bdea6228f7c8a726c0bdb2ca5c3233d5f4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49837201"
---
# <a name="use-setup-command-line-options-with-skype-for-business-clients"></a><span data-ttu-id="69d8e-103">Usar opções de linha de comando de Instalação com clientes do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="69d8e-103">Use Setup command-line options with Skype for Business clients</span></span>
 
<span data-ttu-id="69d8e-104">**Resumo:** Saiba mais sobre Setup.exe de linha de comando na configuração do Office.</span><span class="sxs-lookup"><span data-stu-id="69d8e-104">**Summary:** Learn about Setup.exe command line operations in Office setup.</span></span>
  
<span data-ttu-id="69d8e-105">A Setup.exe de comando é usada para poucas operações na configuração do Office.</span><span class="sxs-lookup"><span data-stu-id="69d8e-105">The Setup.exe command line is used for very few operations in Office setup.</span></span> <span data-ttu-id="69d8e-106">Em vez de usar as opções de linha de comando da Instalação, você normalmente usará a Ferramenta de Personalização do Office e o arquivo Config.xml para instalação do produto e personalização de recursos.</span><span class="sxs-lookup"><span data-stu-id="69d8e-106">Instead of using the Setup command-line options, you'll typically use the Office Customization Tool and the Config.xml file for product setup and feature customization.</span></span>
  
<span data-ttu-id="69d8e-107">A linha Setup.exe comando do Office reconhece as opções de linha de comando descritas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="69d8e-107">The Office Setup.exe command line recognizes the command-line options described in the following table.</span></span>
  
<span data-ttu-id="69d8e-108">**Opções de configuração Command-Line Office**</span><span class="sxs-lookup"><span data-stu-id="69d8e-108">**Office Setup Command-Line Options**</span></span>

|<span data-ttu-id="69d8e-109">**Opção de Command-Line configuração**</span><span class="sxs-lookup"><span data-stu-id="69d8e-109">**Setup Command-Line Option**</span></span>|<span data-ttu-id="69d8e-110">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="69d8e-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="69d8e-111">/admin</span><span class="sxs-lookup"><span data-stu-id="69d8e-111">/admin</span></span>  <br/> |<span data-ttu-id="69d8e-112">Executa a Ferramenta de Personalização do Office para criar um arquivo de personalização da Instalação (arquivo .msp).</span><span class="sxs-lookup"><span data-stu-id="69d8e-112">Runs the Office Customization Tool to create a Setup customization file (.msp file).</span></span>  <br/> |
|<span data-ttu-id="69d8e-113">/adminfile [path]</span><span class="sxs-lookup"><span data-stu-id="69d8e-113">/adminfile [path]</span></span>  <br/> |<span data-ttu-id="69d8e-p102">Aplica o arquivo de personalização da Instalação específico para a instalação. É possível especificar um caminho de um arquivo de personalização específico (arquivo .msp) ou para a pasta na qual você armazena os arquivos de personalização.</span><span class="sxs-lookup"><span data-stu-id="69d8e-p102">Applies the specified Setup customization file to the installation. You can specify a path of a specific customization file (.msp file) or to the folder where you store customization files.</span></span>  <br/> |
|<span data-ttu-id="69d8e-116">/config [path]</span><span class="sxs-lookup"><span data-stu-id="69d8e-116">/config [path]</span></span>  <br/> |<span data-ttu-id="69d8e-117">Especifica o arquivo Config.xml que a Instalação usa durante a instalação.</span><span class="sxs-lookup"><span data-stu-id="69d8e-117">Specifies the Config.xml file that Setup uses during the installation.</span></span> <span data-ttu-id="69d8e-118">Use a opção /config para especificar o arquivo Config.xml personalizado para instalações do Skype for Business, por exemplo:  `/config \\server\share\Skype15\Skype.WW\Config.xml`</span><span class="sxs-lookup"><span data-stu-id="69d8e-118">Use the /config option to specify the Config.xml file you customized for Skype for Business installations, for example:  `/config \\server\share\Skype15\Skype.WW\Config.xml`</span></span> <br/> |
|<span data-ttu-id="69d8e-119">/modify Skype</span><span class="sxs-lookup"><span data-stu-id="69d8e-119">/modify Skype</span></span>  <br/> |<span data-ttu-id="69d8e-120">Usado com um arquivo Config.xml modificado para executar a instalação no modo de manutenção e fazer alterações em uma instalação existente do Office.</span><span class="sxs-lookup"><span data-stu-id="69d8e-120">Used with a modified Config.xml file to run Setup in maintenance mode and make changes to an existing Office installation.</span></span> <span data-ttu-id="69d8e-121">Por exemplo, você pode usar a opção /modify para adicionar ou remover recursos do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="69d8e-121">For example, you can use the /modify option to add or remove Skype for Business features.</span></span>  <br/> |
|<span data-ttu-id="69d8e-122">/repair Skype</span><span class="sxs-lookup"><span data-stu-id="69d8e-122">/repair Skype</span></span>  <br/> |<span data-ttu-id="69d8e-123">Executa a Instalação do computador do usuário para reparar o Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="69d8e-123">Runs Setup from the user's computer to repair Skype for Business.</span></span>  <br/> |
|<span data-ttu-id="69d8e-124">/uninstall Skype</span><span class="sxs-lookup"><span data-stu-id="69d8e-124">/uninstall Skype</span></span>  <br/> |<span data-ttu-id="69d8e-125">Executa a Instalação para remover o Skype for Business do computador do usuário.</span><span class="sxs-lookup"><span data-stu-id="69d8e-125">Runs Setup to remove Skype for Business from the user's computer.</span></span>  <br/> |
   


