---
title: Provisionamento a topologia para executar a carga em cenários de Stress e desempenho
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 12/17/2015
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 143cf9bd-b935-494d-817c-a8b0ccc61eb8
description: Skype para alterações de topologia Business Server 2015 ou provisionamento para permitir que usuários com êxito, execute a ferramenta de Stress e desempenho.
ms.openlocfilehash: 446c8d8154992540ffd8bfe18b07af7c54e864fe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33906638"
---
# <a name="provisioning-the-topology-to-run-load-in-stress-and-performance-scenarios"></a><span data-ttu-id="35c02-103">Provisionamento a topologia para executar a carga em cenários de Stress e desempenho</span><span class="sxs-lookup"><span data-stu-id="35c02-103">Provisioning the topology to run load in Stress and Performance scenarios</span></span>
 
<span data-ttu-id="35c02-104">Skype para alterações de topologia Business Server 2015 ou provisionamento para permitir que usuários com êxito, execute a ferramenta de Stress e desempenho.</span><span class="sxs-lookup"><span data-stu-id="35c02-104">Skype for Business Server 2015 topology changes or provisioning to allow users to successfully run the Stress and Performance tool.</span></span>
  
<span data-ttu-id="35c02-105">Dependendo as configurações existentes e a configuração de sua implantação do Skype para Business Server 2015, você pode precisar fazer algumas alterações em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="35c02-105">Depending on your existing settings and configuration for your deployment of Skype for Business Server 2015, you might need to make some changes in your environment.</span></span> <span data-ttu-id="35c02-106">A seguir está uma lista dessas alterações:</span><span class="sxs-lookup"><span data-stu-id="35c02-106">The following is a list of those changes:</span></span>
  
1. <span data-ttu-id="35c02-107">Defina a diretiva de execução do Windows PowerShell como irrestrito.</span><span class="sxs-lookup"><span data-stu-id="35c02-107">Set the Windows PowerShell execution policy to Unrestricted.</span></span> <span data-ttu-id="35c02-108">Se você não tiver certeza de qual é definido como atualmente, pode abrir o Skype para Business Server Management Shell e execute este comando:</span><span class="sxs-lookup"><span data-stu-id="35c02-108">If you're not sure what it's set to currently, you can open the Skype for Business Server Management Shell and run this command:</span></span>
    
   ```
   Get-ExecutionPolicy
   ```

   <span data-ttu-id="35c02-109">Se o valor Unrestricted não for retornado, você precisará executar nesse Avançar:</span><span class="sxs-lookup"><span data-stu-id="35c02-109">If the value Unrestricted is not returned, you'll need to run this next:</span></span>
    
   ```
   Set-ExecutionPolicy -Unrestricted
   ```

2. <span data-ttu-id="35c02-110">Para configurar efetivamente Skype para Business Server, você precisará:</span><span class="sxs-lookup"><span data-stu-id="35c02-110">To effectively configure Skype for Business Server, you'll need to:</span></span>
    
    - <span data-ttu-id="35c02-111">Estar familiarizado com seu Skype para Business Server 2015 topologia (por exemplo, nomes de computador, instâncias de serviço, nomes de site e políticas).</span><span class="sxs-lookup"><span data-stu-id="35c02-111">Be familiar with your Skype for Business Server 2015 topology (such as computer names, service instances, site names, and policies).</span></span>
    
    - <span data-ttu-id="35c02-112">Atribua alguns dos usuários que são criados para grupos, como o grupo de resposta (por exemplo, URIs de SIP) de grupos de busca.</span><span class="sxs-lookup"><span data-stu-id="35c02-112">Assign some of the users that are created to groups, such as Response Group hunt groups (for example, SIP URIs).</span></span>
    
3. <span data-ttu-id="35c02-113">Para executar um script de linha de comando, você pode usar:</span><span class="sxs-lookup"><span data-stu-id="35c02-113">To run a script from command line, you can use:</span></span>
    
   ```
   PowerShell.exe -file <path to the file>
   ```

4. <span data-ttu-id="35c02-114">Normalmente, depois de executar um script deste pacote, os rastreamentos resultantes serão armazenados em um arquivo no mesmo caminho em que o script foi executado.</span><span class="sxs-lookup"><span data-stu-id="35c02-114">Typically, after you've run a script from this package, the resulting traces will be stored in a file in the same path from where the script was run.</span></span> <span data-ttu-id="35c02-115">Há também um formato de nomeação \<scriptname\>$h$m$s.txt.</span><span class="sxs-lookup"><span data-stu-id="35c02-115">There's a naming format as well, \<scriptname\>$h$m$s.txt.</span></span> <span data-ttu-id="35c02-116">Portanto, se você executou o ArchivingPolicy.ps1 às 12:15:00, você obterá um arquivo de log chamado ArchivingPolicy121500.txt.</span><span class="sxs-lookup"><span data-stu-id="35c02-116">So if you ran the ArchivingPolicy.ps1 at 12:15 PM, you'll get a log file named ArchivingPolicy121500.txt.</span></span>
    
5. <span data-ttu-id="35c02-117">Enquanto fornecemos estes exemplos para a configuração do servidor, cabe a você modificar sua configuração e restaurar ou revertê-la depois de terminar a execução do teste de carga.</span><span class="sxs-lookup"><span data-stu-id="35c02-117">While we've provided these examples for your server configuration, it's up to you to both modify your configuration and restore or roll it back after you've finished running the load testing.</span></span>
    

