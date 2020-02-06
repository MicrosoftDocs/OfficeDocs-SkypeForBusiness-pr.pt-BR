---
title: Provisionando a topologia para executar carga em cenários de carga e desempenho
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 12/17/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 143cf9bd-b935-494d-817c-a8b0ccc61eb8
description: O Skype for Business Server 2015 altera ou provisionamento de topologia para permitir que os usuários executem com êxito a ferramenta de stress e desempenho.
ms.openlocfilehash: 2156616fac98d1e6fad08d2036f4bc2def3e98b6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816160"
---
# <a name="provisioning-the-topology-to-run-load-in-stress-and-performance-scenarios"></a><span data-ttu-id="aa4a5-103">Provisionando a topologia para executar carga em cenários de carga e desempenho</span><span class="sxs-lookup"><span data-stu-id="aa4a5-103">Provisioning the topology to run load in Stress and Performance scenarios</span></span>
 
<span data-ttu-id="aa4a5-104">O Skype for Business Server 2015 altera ou provisionamento de topologia para permitir que os usuários executem com êxito a ferramenta de stress e desempenho.</span><span class="sxs-lookup"><span data-stu-id="aa4a5-104">Skype for Business Server 2015 topology changes or provisioning to allow users to successfully run the Stress and Performance tool.</span></span>
  
<span data-ttu-id="aa4a5-105">Dependendo das configurações existentes e da configuração da sua implantação do Skype for Business Server 2015, talvez seja necessário fazer algumas alterações no ambiente.</span><span class="sxs-lookup"><span data-stu-id="aa4a5-105">Depending on your existing settings and configuration for your deployment of Skype for Business Server 2015, you might need to make some changes in your environment.</span></span> <span data-ttu-id="aa4a5-106">Veja a seguir uma lista dessas alterações:</span><span class="sxs-lookup"><span data-stu-id="aa4a5-106">The following is a list of those changes:</span></span>
  
1. <span data-ttu-id="aa4a5-107">Defina a política de execução do Windows PowerShell como Irrestrito.</span><span class="sxs-lookup"><span data-stu-id="aa4a5-107">Set the Windows PowerShell execution policy to Unrestricted.</span></span> <span data-ttu-id="aa4a5-108">Se não tiver certeza de que ele está definido no momento, você pode abrir o Shell de gerenciamento do Skype for Business Server e executar este comando:</span><span class="sxs-lookup"><span data-stu-id="aa4a5-108">If you're not sure what it's set to currently, you can open the Skype for Business Server Management Shell and run this command:</span></span>
    
   ```PowerShell
   Get-ExecutionPolicy
   ```

   <span data-ttu-id="aa4a5-109">Se o valor irrestrito não for retornado, você precisará executar o seguinte:</span><span class="sxs-lookup"><span data-stu-id="aa4a5-109">If the value Unrestricted is not returned, you'll need to run this next:</span></span>
    
   ```PowerShell
   Set-ExecutionPolicy -Unrestricted
   ```

2. <span data-ttu-id="aa4a5-110">Para configurar efetivamente o Skype for Business Server, você precisará:</span><span class="sxs-lookup"><span data-stu-id="aa4a5-110">To effectively configure Skype for Business Server, you'll need to:</span></span>
    
    - <span data-ttu-id="aa4a5-111">Familiarize-se com sua topologia do Skype for Business Server 2015 (por exemplo, nomes de computador, instâncias de serviço, nomes de site e políticas).</span><span class="sxs-lookup"><span data-stu-id="aa4a5-111">Be familiar with your Skype for Business Server 2015 topology (such as computer names, service instances, site names, and policies).</span></span>
    
    - <span data-ttu-id="aa4a5-112">Atribua alguns dos usuários criados a grupos, como os números coletivos de grupos de resposta (por exemplo, URIs SIP).</span><span class="sxs-lookup"><span data-stu-id="aa4a5-112">Assign some of the users that are created to groups, such as Response Group hunt groups (for example, SIP URIs).</span></span>
    
3. <span data-ttu-id="aa4a5-113">Para executar um script a partir da linha de comando, você pode usar:</span><span class="sxs-lookup"><span data-stu-id="aa4a5-113">To run a script from command line, you can use:</span></span>
    
   ```PowerShell
   PowerShell.exe -file <path to the file>
   ```

4. <span data-ttu-id="aa4a5-114">Geralmente, depois que você executar um script deste pacote, os rastreamentos resultantes serão armazenados em um arquivo no mesmo caminho a partir do local em que o script foi executado.</span><span class="sxs-lookup"><span data-stu-id="aa4a5-114">Typically, after you've run a script from this package, the resulting traces will be stored in a file in the same path from where the script was run.</span></span> <span data-ttu-id="aa4a5-115">Também há um formato de nomenclatura, \<scriptname\>$h $ m $ s. txt.</span><span class="sxs-lookup"><span data-stu-id="aa4a5-115">There's a naming format as well, \<scriptname\>$h$m$s.txt.</span></span> <span data-ttu-id="aa4a5-116">Portanto, se você executou o ArchivingPolicy. ps1 em 12:15 PM, obterá um arquivo de log chamado ArchivingPolicy121500. txt.</span><span class="sxs-lookup"><span data-stu-id="aa4a5-116">So if you ran the ArchivingPolicy.ps1 at 12:15 PM, you'll get a log file named ArchivingPolicy121500.txt.</span></span>
    
5. <span data-ttu-id="aa4a5-117">Embora tenhamos fornecido esses exemplos para a configuração do seu servidor, você pode modificar a configuração e restaurá-la ou recarregá-la após concluir a execução do teste de carga.</span><span class="sxs-lookup"><span data-stu-id="aa4a5-117">While we've provided these examples for your server configuration, it's up to you to both modify your configuration and restore or roll it back after you've finished running the load testing.</span></span>
    

