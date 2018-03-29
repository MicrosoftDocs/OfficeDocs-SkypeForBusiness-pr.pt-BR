---
title: Shell de Gerenciamento do Skype for Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 9/20/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
description: O Skype do Shell de gerenciamento do Business Server fornece a interface de linha de comando para gerenciamento e administração de servidor. Ele é baseado no Windows PowerShell e inclui um conjunto abrangente de gerenciamento e administração cmdlets específicos ao Skype e produtos de servidor herdados do Lync.
ms.openlocfilehash: e4eb5f183af29dd5f9932fb15cdb86a0f78e7840
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="skype-for-business-server-2015-management-shell"></a><span data-ttu-id="4569b-104">Shell de Gerenciamento do Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="4569b-104">Skype for Business Server 2015 Management Shell</span></span>
 
<span data-ttu-id="4569b-105">O Skype do Shell de gerenciamento do Business Server fornece a interface de linha de comando para gerenciamento e administração de servidor.</span><span class="sxs-lookup"><span data-stu-id="4569b-105">The Skype for Business Server Management Shell provides the command line interface for server administration and management.</span></span> <span data-ttu-id="4569b-106">Ele é baseado no Windows PowerShell e inclui um conjunto abrangente de gerenciamento e administração cmdlets específicos ao Skype e produtos de servidor herdados do Lync.</span><span class="sxs-lookup"><span data-stu-id="4569b-106">It is built on Windows PowerShell and includes a comprehensive set of management and administration cmdlets that are specific to Skype and legacy Lync server products.</span></span>
  
<span data-ttu-id="4569b-107">Windows PowerShell permite gerenciar aplicativos da Microsoft a partir da linha de comando.</span><span class="sxs-lookup"><span data-stu-id="4569b-107">Windows PowerShell allows you to manage Microsoft applications from the command line.</span></span> <span data-ttu-id="4569b-108">Ele inclui um ambiente de linha de comando, comandos específicos de produtos e uma linguagem de script completa.</span><span class="sxs-lookup"><span data-stu-id="4569b-108">It includes a command-line environment, product-specific commands, and a full scripting language.</span></span> <span data-ttu-id="4569b-109">Windows PowerShell foi introduzido primeiro como uma versão para download para o sistema operacional Windows no final de 2006 e foi incorporado como a interface de linha de comando para o gerenciamento do Microsoft Exchange Server 2007.</span><span class="sxs-lookup"><span data-stu-id="4569b-109">Windows PowerShell was first introduced as a downloadable release for the Windows operating system late in 2006, and was incorporated as the command-line interface for manageability of Microsoft Exchange Server 2007.</span></span> <span data-ttu-id="4569b-110">Ele foi incorporado na maioria dos produtos Microsoft Server, incluindo servidores de Lync e Skype começando com o Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="4569b-110">It has been incorporated into most of the Microsoft Server products, including Lync and Skype servers beginning with Lync Server 2010.</span></span> <span data-ttu-id="4569b-111">Há mais de 700 cmdlets específicos do Lync e Skype disponíveis no Skype do Shell de gerenciamento do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="4569b-111">There are over 700 Lync and Skype specific cmdlets available in the Skype for Business Server Management Shell.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4569b-112">Skype para referência de cmdlet Business foi movido para docs.microsoft.com. Clicando nos links a seguir o levará à nova página docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="4569b-112">Skype for Business cmdlet reference has moved to docs.microsoft.com. Clicking on the links below will take you to the new docs.microsoft.com page.</span></span> <span data-ttu-id="4569b-113">O conteúdo agora está aberto e disponível para contribuições da comunidade através do GitHub.</span><span class="sxs-lookup"><span data-stu-id="4569b-113">The content is now open sourced and available for community contributions through GitHub.</span></span> <span data-ttu-id="4569b-114">Tem interesse em contribuir?</span><span class="sxs-lookup"><span data-stu-id="4569b-114">Interested in contributing?</span></span> <span data-ttu-id="4569b-115">Confira Leiame no repo aqui:[https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)</span><span class="sxs-lookup"><span data-stu-id="4569b-115">Check out the README in the repo here: [https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)</span></span>
  
<span data-ttu-id="4569b-116">Skype para Business Server 2015 é fornecido com mais de 700 cmdlets que permitem que administradores gerenciem Skype para Business Server usando o Skype do Shell de gerenciamento do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="4569b-116">Skype for Business Server 2015 ships with more than 700 cmdlets that enable administrators to manage Skype for Business Server using the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="4569b-117">Você pode obter ajuda para um cmdlet diretamente a partir da linha de comando digitando um comando similar ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="4569b-117">You can retrieve help for a cmdlet directly from the command line by typing a command similar to the following:</span></span>
  
```
Get-Help New-CsVoicePolicy -Full
```

<span data-ttu-id="4569b-118">O comando anterior recupera a Ajuda completa disponível para o cmdlet **New-CsVoicePolicy** .</span><span class="sxs-lookup"><span data-stu-id="4569b-118">The preceding command retrieves the complete help available for the **New-CsVoicePolicy** cmdlet.</span></span> <span data-ttu-id="4569b-119">Para exibir a Ajuda para um cmdlet diferente, substitua **New-CsVoicePolicy** com o nome do cmdlet para o qual você deseja recuperar a Ajuda.</span><span class="sxs-lookup"><span data-stu-id="4569b-119">To view help for a different cmdlet, substitute **New-CsVoicePolicy** with the name of the cmdlet for which you want to retrieve help.</span></span>
  
<span data-ttu-id="4569b-120">Para recuperar uma lista completa dos cmdlets disponíveis para gerenciamento do Skype for Business Server, digite o seguinte no prompt de comando do shell:</span><span class="sxs-lookup"><span data-stu-id="4569b-120">To retrieve a full list of cmdlets available for managing Skype for Business Server, type the following at the shell command prompt:</span></span> 
  
```
Get-Command * -Module SkypeforBusiness -CommandType cmdlet
```



<span data-ttu-id="4569b-121">Informações importantes sobre o Windows PowerShell no Skype para Business Server:</span><span class="sxs-lookup"><span data-stu-id="4569b-121">Things to know about Windows PowerShell in Skype for Business Server:</span></span>
  
- <span data-ttu-id="4569b-122">Para executar o Skype para cmdlets Business Server, abra o Skype do Shell de gerenciamento do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="4569b-122">To run the Skype for Business Server cmdlets, open the Skype for Business Server Management Shell.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="4569b-123">Se você abrir uma janela do Windows PowerShell, em vez do Skype do Shell de gerenciamento do servidor de negócios, por padrão você pode não conseguir executar os cmdlets do Skype.</span><span class="sxs-lookup"><span data-stu-id="4569b-123">If you open a Windows PowerShell window rather than the Skype for Business Server Management Shell, by default you may not be able to run the Skype cmdlets.</span></span> <span data-ttu-id="4569b-124">Para executar o Skype para cmdlets do servidor de negócios de dentro do Windows PowerShell, primeiro digite o seguinte no prompt de comando do Windows PowerShell: >`Import-Module SkypeforBusiness`</span><span class="sxs-lookup"><span data-stu-id="4569b-124">To run Skype for Business Server cmdlets from within Windows PowerShell, first type the following at the Windows PowerShell command prompt: >  `Import-Module SkypeforBusiness`</span></span>
  
- <span data-ttu-id="4569b-125">Skype do Shell de gerenciamento do servidor de negócios é instalado automaticamente em cada Skype para Business Server Enterprise Edition servidor Front-End ou servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="4569b-125">Skype for Business Server Management Shell is automatically installed on every Skype for Business Server Enterprise Edition Front End Server or Standard Edition server.</span></span>
    
- <span data-ttu-id="4569b-126">Você pode atualizar o Skype para conteúdo de Ajuda do Shell de gerenciamento do Business Server executando o cmdlet [Update-Help](https://technet.microsoft.com/en-us/library/hh849720.aspx) .</span><span class="sxs-lookup"><span data-stu-id="4569b-126">You can update the Skype for Business Server Management Shell help content by running the [Update-Help](https://technet.microsoft.com/en-us/library/hh849720.aspx) cmdlet.</span></span> <span data-ttu-id="4569b-127">O cmdlet Update-Help baixa e instala os mais novos arquivos de ajuda disponíveis para todos os módulos instalados no computador, inclusive devido às Skype atualizações para cmdlets de negócios.</span><span class="sxs-lookup"><span data-stu-id="4569b-127">The Update-Help cmdlet downloads and installs the newest help files available for all of the modules installed on your computer, including updates to Skype for Business cmdlets.</span></span>
    
    <span data-ttu-id="4569b-128">Por padrão, o cmdlet **Update-Help** atualizará todos os módulos instalados no seu Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="4569b-128">By default, the **Update-Help** cmdlet will update all the modules installed on your Skype for Business Server.</span></span> <span data-ttu-id="4569b-129">Se você deseja atualizar apenas determinados módulos, você pode usar o parâmetro do _módulo_ para limitar o escopo do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="4569b-129">If you want to update only certain modules, you can use the _Module_ parameter to limit the scope of the cmdlet.</span></span> <span data-ttu-id="4569b-130">O exemplo a seguir atualiza apenas o Skype para módulo comercial.</span><span class="sxs-lookup"><span data-stu-id="4569b-130">The following example updates only the Skype for Business module.</span></span>
    
  ```
  Update-Help -Module SkypeforBusiness
  ```

    <span data-ttu-id="4569b-131">Se você precisar atualizar a Ajuda em servidores que não estão conectados à internet, você pode usar o cmdlet [Salvar-Help](https://technet.microsoft.com/en-us/library/hh849724.aspx) para obter a versão mais recente da Ajuda e salvá-lo em um local especificado.</span><span class="sxs-lookup"><span data-stu-id="4569b-131">If you need to update the Help on servers that are not connected to the internet, you can use the [Save-Help](https://technet.microsoft.com/en-us/library/hh849724.aspx) cmdlet to get the latest version of the help and save it to a location you specify.</span></span> <span data-ttu-id="4569b-132">Em seguida, você pode usar o cmdlet **Update-Help** com o parâmetro _- SourcePath_ nos servidores que não está conectado à internet para obter a Ajuda atualizada do local selecionado.</span><span class="sxs-lookup"><span data-stu-id="4569b-132">You can then use the **Update-Help** cmdlet with the _-SourcePath_ parameter on servers not connected to the internet to get the updated help from the location you selected.</span></span> <span data-ttu-id="4569b-133">O exemplo a seguir mostra como salvar os arquivos de ajuda para um compartilhamento de arquivo de rede e, em seguida, atualize a Ajuda para o Skype para módulo comercial do compartilhamento de arquivo.</span><span class="sxs-lookup"><span data-stu-id="4569b-133">The following example shows how to save the help files to a network file share, and then update the help for the Skype for Business module from the file share.</span></span>
    
  ```
  // Save the help files
   Save-Help -DestinationPath \\UpdateShare\HelpDownload
// Run Update-Help against the local help files
   Update-Help -Module SkypeforBusiness -SourcePath \\UpdateShare\HelpDownload
  ```

    <span data-ttu-id="4569b-134">Para obter informações mais detalhadas, consulte [Sobre ajuda atualizável](https://technet.microsoft.com/library/hh847735.aspx).</span><span class="sxs-lookup"><span data-stu-id="4569b-134">For more detailed information, see [About Updatable Help](https://technet.microsoft.com/library/hh847735.aspx).</span></span>
    

