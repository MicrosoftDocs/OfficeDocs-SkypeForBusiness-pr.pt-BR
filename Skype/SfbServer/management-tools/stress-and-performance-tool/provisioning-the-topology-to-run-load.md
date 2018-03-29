---
title: Provisionamento a topologia para executar a carga em cenários de Stress e desempenho
ms.author: heidip
author: microsoftheidi
ms.date: 12/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 143cf9bd-b935-494d-817c-a8b0ccc61eb8
description: Skype para alterações de topologia Business Server 2015 ou provisionamento para permitir que usuários com êxito, execute a ferramenta de Stress e desempenho.
ms.openlocfilehash: 825dd56a7f2cb343eddd8cbed7e811cdc5154b9c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="provisioning-the-topology-to-run-load-in-stress-and-performance-scenarios"></a><span data-ttu-id="f04ed-103">Provisionamento a topologia para executar a carga em cenários de Stress e desempenho</span><span class="sxs-lookup"><span data-stu-id="f04ed-103">Provisioning the topology to run load in Stress and Performance scenarios</span></span>
 
<span data-ttu-id="f04ed-104">Skype para alterações de topologia Business Server 2015 ou provisionamento para permitir que usuários com êxito, execute a ferramenta de Stress e desempenho.</span><span class="sxs-lookup"><span data-stu-id="f04ed-104">Skype for Business Server 2015 topology changes or provisioning to allow users to successfully run the Stress and Performance tool.</span></span>
  
<span data-ttu-id="f04ed-105">Dependendo as configurações existentes e a configuração de sua implantação do Skype para Business Server 2015, você pode precisar fazer algumas alterações em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="f04ed-105">Depending on your existing settings and configuration for your deployment of Skype for Business Server 2015, you might need to make some changes in your environment.</span></span> <span data-ttu-id="f04ed-106">A seguir está uma lista dessas alterações:</span><span class="sxs-lookup"><span data-stu-id="f04ed-106">The following is a list of those changes:</span></span>
  
1. <span data-ttu-id="f04ed-107">Defina a diretiva de execução do Windows PowerShell como irrestrito.</span><span class="sxs-lookup"><span data-stu-id="f04ed-107">Set the Windows PowerShell execution policy to Unrestricted.</span></span> <span data-ttu-id="f04ed-108">Se você não tiver certeza de qual é definido como atualmente, pode abrir o Skype para Business Server Management Shell e execute este comando:</span><span class="sxs-lookup"><span data-stu-id="f04ed-108">If you're not sure what it's set to currently, you can open the Skype for Business Server Management Shell and run this command:</span></span>
    
  ```
  Get-ExecutionPolicy
  ```

  <span data-ttu-id="f04ed-109">Se o valor Unrestricted não for retornado, você precisará executar nesse Avançar:</span><span class="sxs-lookup"><span data-stu-id="f04ed-109">If the value Unrestricted is not returned, you'll need to run this next:</span></span>
    
  ```
  Set-ExecutionPolicy -Unrestricted
  ```

2. <span data-ttu-id="f04ed-110">Para configurar efetivamente Skype para Business Server, você precisará:</span><span class="sxs-lookup"><span data-stu-id="f04ed-110">To effectively configure Skype for Business Server, you'll need to:</span></span>
    
    - <span data-ttu-id="f04ed-111">Estar familiarizado com seu Skype para Business Server 2015 topologia (por exemplo, nomes de computador, instâncias de serviço, nomes de site e políticas).</span><span class="sxs-lookup"><span data-stu-id="f04ed-111">Be familiar with your Skype for Business Server 2015 topology (such as computer names, service instances, site names, and policies).</span></span>
    
    - <span data-ttu-id="f04ed-112">Atribua alguns dos usuários que são criados para grupos, como o grupo de resposta (por exemplo, URIs de SIP) de grupos de busca.</span><span class="sxs-lookup"><span data-stu-id="f04ed-112">Assign some of the users that are created to groups, such as Response Group hunt groups (for example, SIP URIs).</span></span>
    
3. <span data-ttu-id="f04ed-113">Para executar um script de linha de comando, você pode usar:</span><span class="sxs-lookup"><span data-stu-id="f04ed-113">To run a script from command line, you can use:</span></span>
    
  ```
  PowerShell.exe -file <path to the file>
  ```

4. <span data-ttu-id="f04ed-114">Normalmente, depois de executar um script deste pacote, os rastreamentos resultantes serão armazenados em um arquivo no mesmo caminho em que o script foi executado.</span><span class="sxs-lookup"><span data-stu-id="f04ed-114">Typically, after you've run a script from this package, the resulting traces will be stored in a file in the same path from where the script was run.</span></span> <span data-ttu-id="f04ed-115">Há também um formato de nomeação \<scriptname\>$h$m$s.txt.</span><span class="sxs-lookup"><span data-stu-id="f04ed-115">There's a naming format as well, \<scriptname\>$h$m$s.txt.</span></span> <span data-ttu-id="f04ed-116">Portanto, se você executou o ArchivingPolicy.ps1 às 12:15:00, você obterá um arquivo de log chamado ArchivingPolicy121500.txt.</span><span class="sxs-lookup"><span data-stu-id="f04ed-116">So if you ran the ArchivingPolicy.ps1 at 12:15 PM, you'll get a log file named ArchivingPolicy121500.txt.</span></span>
    
5. <span data-ttu-id="f04ed-117">Enquanto fornecemos estes exemplos para a configuração do servidor, cabe a você modificar sua configuração e restaurar ou revertê-la depois de terminar a execução do teste de carga.</span><span class="sxs-lookup"><span data-stu-id="f04ed-117">While we've provided these examples for your server configuration, it's up to you to both modify your configuration and restore or roll it back after you've finished running the load testing.</span></span>
    

