---
title: Shell de Gerenciamento do Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
description: O Shell de Gerenciamento do Skype for Business Server fornece a interface de linha de comando para administração e gerenciamento de servidores. Ele é criado com base Windows PowerShell e inclui um conjunto abrangente de cmdlets de gerenciamento e administração que são específicos do Skype e dos produtos de servidor herdados do Lync.
ms.openlocfilehash: 24da9ac341129239399ea17218be8547f3549d6f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118580"
---
# <a name="skype-for-business-server-management-shell"></a><span data-ttu-id="b2788-104">Shell de Gerenciamento do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="b2788-104">Skype for Business Server Management Shell</span></span>
 
<span data-ttu-id="b2788-105">O Shell de Gerenciamento do Skype for Business Server fornece a interface de linha de comando para administração e gerenciamento de servidores.</span><span class="sxs-lookup"><span data-stu-id="b2788-105">The Skype for Business Server Management Shell provides the command line interface for server administration and management.</span></span> <span data-ttu-id="b2788-106">Ele é criado com base Windows PowerShell e inclui um conjunto abrangente de cmdlets de gerenciamento e administração que são específicos do Skype e dos produtos de servidor herdados do Lync.</span><span class="sxs-lookup"><span data-stu-id="b2788-106">It is built on Windows PowerShell and includes a comprehensive set of management and administration cmdlets that are specific to Skype and legacy Lync server products.</span></span>
  
<span data-ttu-id="b2788-107">Windows PowerShell permite gerenciar aplicativos Microsoft a partir da linha de comando.</span><span class="sxs-lookup"><span data-stu-id="b2788-107">Windows PowerShell allows you to manage Microsoft applications from the command line.</span></span> <span data-ttu-id="b2788-108">Ele inclui um ambiente de linha de comando, comandos específicos do produto e um idioma de script completo.</span><span class="sxs-lookup"><span data-stu-id="b2788-108">It includes a command-line environment, product-specific commands, and a full scripting language.</span></span> <span data-ttu-id="b2788-109">Windows PowerShell foi introduzida pela primeira vez como uma versão baixável para o sistema operacional Windows no final de 2006 e foi incorporada como a interface de linha de comando para gerenciar o Microsoft Exchange Server 2007.</span><span class="sxs-lookup"><span data-stu-id="b2788-109">Windows PowerShell was first introduced as a downloadable release for the Windows operating system late in 2006, and was incorporated as the command-line interface for manageability of Microsoft Exchange Server 2007.</span></span> <span data-ttu-id="b2788-110">Ele foi incorporado à maioria dos produtos do Microsoft Server, incluindo servidores Lync e Skype a partir do Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="b2788-110">It has been incorporated into most of the Microsoft Server products, including Lync and Skype servers beginning with Lync Server 2010.</span></span> <span data-ttu-id="b2788-111">Há mais de 700 cmdlets específicos do Lync e do Skype disponíveis no Shell de Gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="b2788-111">There are over 700 Lync and Skype specific cmdlets available in the Skype for Business Server Management Shell.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b2788-112">A referência de cmdlet do Skype for Business foi movida para docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="b2788-112">Skype for Business cmdlet reference has moved to docs.microsoft.com.</span></span> <span data-ttu-id="b2788-113">Clicar nos links abaixo o levará à nova página docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="b2788-113">Clicking on the links below will take you to the new docs.microsoft.com page.</span></span> <span data-ttu-id="b2788-114">O conteúdo agora está aberto e disponível para contribuições da comunidade por meio do GitHub.</span><span class="sxs-lookup"><span data-stu-id="b2788-114">The content is now open sourced and available for community contributions through GitHub.</span></span> <span data-ttu-id="b2788-115">Interessado em contribuir?</span><span class="sxs-lookup"><span data-stu-id="b2788-115">Interested in contributing?</span></span> <span data-ttu-id="b2788-116">Confira o README no repo aqui: [https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)</span><span class="sxs-lookup"><span data-stu-id="b2788-116">Check out the README in the repo here: [https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)</span></span>
  
<span data-ttu-id="b2788-117">O Skype for Business Server vem com mais de 700 cmdlets que permitem que os administradores gerenciem o Skype for Business Server usando o Shell de Gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="b2788-117">Skype for Business Server ships with more than 700 cmdlets that enable administrators to manage Skype for Business Server using the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="b2788-118">Você pode recuperar ajuda para um cmdlet diretamente da linha de comando digitando um comando semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="b2788-118">You can retrieve help for a cmdlet directly from the command line by typing a command similar to the following:</span></span>
  
```PowerShell
Get-Help New-CsVoicePolicy -Full
```

<span data-ttu-id="b2788-119">O comando anterior recupera a ajuda completa disponível para o cmdlet **New-CsVoicePolicy**.</span><span class="sxs-lookup"><span data-stu-id="b2788-119">The preceding command retrieves the complete help available for the **New-CsVoicePolicy** cmdlet.</span></span> <span data-ttu-id="b2788-120">Para exibir a ajuda para um cmdlet diferente, substitua **New-CsVoicePolicy** pelo nome do cmdlet para o qual você deseja recuperar a ajuda.</span><span class="sxs-lookup"><span data-stu-id="b2788-120">To view help for a different cmdlet, substitute **New-CsVoicePolicy** with the name of the cmdlet for which you want to retrieve help.</span></span>
  
<span data-ttu-id="b2788-121">Para recuperar uma lista completa de cmdlets disponíveis para gerenciar o Skype for Business Server, digite o seguinte no prompt de comando do shell:</span><span class="sxs-lookup"><span data-stu-id="b2788-121">To retrieve a full list of cmdlets available for managing Skype for Business Server, type the following at the shell command prompt:</span></span> 
  
```PowerShell
Get-Command * -Module SkypeforBusiness -CommandType cmdlet
```



<span data-ttu-id="b2788-122">O que saber sobre Windows PowerShell no Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="b2788-122">Things to know about Windows PowerShell in Skype for Business Server:</span></span>
  
- <span data-ttu-id="b2788-123">Para executar os cmdlets do Skype for Business Server, abra o Shell de Gerenciamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="b2788-123">To run the Skype for Business Server cmdlets, open the Skype for Business Server Management Shell.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="b2788-124">Se você abrir uma Windows PowerShell em vez do Shell de Gerenciamento do Skype for Business Server, por padrão, talvez não seja possível executar os cmdlets do Skype.</span><span class="sxs-lookup"><span data-stu-id="b2788-124">If you open a Windows PowerShell window rather than the Skype for Business Server Management Shell, by default you may not be able to run the Skype cmdlets.</span></span> <span data-ttu-id="b2788-125">Para executar cmdlets do Skype for Business Server de dentro Windows PowerShell, digite o seguinte no prompt de comando Windows PowerShell: >  `Import-Module SkypeforBusiness`</span><span class="sxs-lookup"><span data-stu-id="b2788-125">To run Skype for Business Server cmdlets from within Windows PowerShell, first type the following at the Windows PowerShell command prompt: >  `Import-Module SkypeforBusiness`</span></span>
  
- <span data-ttu-id="b2788-126">O Shell de Gerenciamento do Skype for Business Server é instalado automaticamente em todos os servidores front-end do Skype for Business Server Enterprise Edition ou no servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="b2788-126">Skype for Business Server Management Shell is automatically installed on every Skype for Business Server Enterprise Edition Front End Server or Standard Edition server.</span></span>
    
- <span data-ttu-id="b2788-127">Você pode atualizar o conteúdo da ajuda do Shell de Gerenciamento do Skype for Business Server executando o cmdlet [Update-Help.](/powershell/module/microsoft.powershell.core/update-help)</span><span class="sxs-lookup"><span data-stu-id="b2788-127">You can update the Skype for Business Server Management Shell help content by running the [Update-Help](/powershell/module/microsoft.powershell.core/update-help) cmdlet.</span></span> <span data-ttu-id="b2788-128">O Update-Help cmdlet baixa e instala os arquivos de ajuda mais novos disponíveis para todos os módulos instalados em seu computador, incluindo atualizações para cmdlets do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="b2788-128">The Update-Help cmdlet downloads and installs the newest help files available for all of the modules installed on your computer, including updates to Skype for Business cmdlets.</span></span>
    
    <span data-ttu-id="b2788-129">Por padrão, o cmdlet **Update-Help** atualizará todos os módulos instalados em seu Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="b2788-129">By default, the **Update-Help** cmdlet will update all the modules installed on your Skype for Business Server.</span></span> <span data-ttu-id="b2788-130">Se você quiser atualizar apenas determinados módulos, poderá usar o parâmetro _Module_ para limitar o escopo do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="b2788-130">If you want to update only certain modules, you can use the _Module_ parameter to limit the scope of the cmdlet.</span></span> <span data-ttu-id="b2788-131">O exemplo a seguir atualiza apenas o módulo Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="b2788-131">The following example updates only the Skype for Business module.</span></span>
    
  ```PowerShell
  Update-Help -Module SkypeforBusiness
  ```

    <span data-ttu-id="b2788-132">Se você precisar atualizar a Ajuda em servidores que não estão conectados à Internet, use o cmdlet Save-Help para obter a versão mais recente da ajuda e [salvá-la](/powershell/module/microsoft.powershell.core/save-help) em um local especificado.</span><span class="sxs-lookup"><span data-stu-id="b2788-132">If you need to update the Help on servers that are not connected to the internet, you can use the [Save-Help](/powershell/module/microsoft.powershell.core/save-help) cmdlet to get the latest version of the help and save it to a location you specify.</span></span> <span data-ttu-id="b2788-133">Em seguida, você pode usar o cmdlet **Update-Help** com o parâmetro _-SourcePath_ em servidores não conectados à Internet para obter a ajuda atualizada do local selecionado.</span><span class="sxs-lookup"><span data-stu-id="b2788-133">You can then use the **Update-Help** cmdlet with the _-SourcePath_ parameter on servers not connected to the internet to get the updated help from the location you selected.</span></span> <span data-ttu-id="b2788-134">O exemplo a seguir mostra como salvar os arquivos de ajuda em um compartilhamento de arquivos de rede e, em seguida, atualizar a ajuda para o módulo Skype for Business do compartilhamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="b2788-134">The following example shows how to save the help files to a network file share, and then update the help for the Skype for Business module from the file share.</span></span>
    
  ```PowerShell
  // Save the help files
   Save-Help -DestinationPath \\UpdateShare\HelpDownload
  // Run Update-Help against the local help files
   Update-Help -Module SkypeforBusiness -SourcePath \\UpdateShare\HelpDownload
  ```

    <span data-ttu-id="b2788-135">Para obter informações mais detalhadas, consulte [About Updatable Help](/powershell/module/microsoft.powershell.core/about/about_updatable_help).</span><span class="sxs-lookup"><span data-stu-id="b2788-135">For more detailed information, see [About Updatable Help](/powershell/module/microsoft.powershell.core/about/about_updatable_help).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b2788-136">Se você estiver usando o PowerShell remotamente, talvez seja necessário permitir a comunicação por meio de um firewall.</span><span class="sxs-lookup"><span data-stu-id="b2788-136">If you are using PowerShell remotely you may need to allow communication through a firewall.</span></span> <span data-ttu-id="b2788-137">Para saber mais sobre as portas que o PowerShell remoting usa, consulte [What Port Does PowerShell Remoting Use?](/archive/blogs/christwe/what-port-does-powershell-remoting-use).</span><span class="sxs-lookup"><span data-stu-id="b2788-137">To learn more about the ports PowerShell remoting uses, see [What Port Does PowerShell Remoting Use?](/archive/blogs/christwe/what-port-does-powershell-remoting-use).</span></span>
