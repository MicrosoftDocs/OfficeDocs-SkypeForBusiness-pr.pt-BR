---
title: Provisionando a topologia para executar a carga em cenários de Stress and Performance
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Alterações ou provisionamento da topologia do Skype for Business Server 2015 para permitir que os usuários executem com êxito a ferramenta Stress and Performance.
ms.openlocfilehash: 8d422497d11c9e56e4d5b205269a09f96dffc136
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814931"
---
# <a name="provisioning-the-topology-to-run-load-in-stress-and-performance-scenarios"></a><span data-ttu-id="6f027-103">Provisionando a topologia para executar a carga em cenários de Stress and Performance</span><span class="sxs-lookup"><span data-stu-id="6f027-103">Provisioning the topology to run load in Stress and Performance scenarios</span></span>
 
<span data-ttu-id="6f027-104">Alterações ou provisionamento da topologia do Skype for Business Server 2015 para permitir que os usuários executem com êxito a ferramenta Stress and Performance.</span><span class="sxs-lookup"><span data-stu-id="6f027-104">Skype for Business Server 2015 topology changes or provisioning to allow users to successfully run the Stress and Performance tool.</span></span>
  
<span data-ttu-id="6f027-105">Dependendo das configurações existentes para sua implantação do Skype for Business Server 2015, talvez seja necessário fazer algumas alterações em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="6f027-105">Depending on your existing settings and configuration for your deployment of Skype for Business Server 2015, you might need to make some changes in your environment.</span></span> <span data-ttu-id="6f027-106">A seguir está uma lista dessas alterações:</span><span class="sxs-lookup"><span data-stu-id="6f027-106">The following is a list of those changes:</span></span>
  
1. <span data-ttu-id="6f027-107">Definir a política de execução do Windows PowerShell como Irrestrita.</span><span class="sxs-lookup"><span data-stu-id="6f027-107">Set the Windows PowerShell execution policy to Unrestricted.</span></span> <span data-ttu-id="6f027-108">Se você não tiver certeza para o que ele está definido no momento, poderá abrir o Shell de Gerenciamento do Skype for Business Server e executar este comando:</span><span class="sxs-lookup"><span data-stu-id="6f027-108">If you're not sure what it's set to currently, you can open the Skype for Business Server Management Shell and run this command:</span></span>
    
   ```PowerShell
   Get-ExecutionPolicy
   ```

   <span data-ttu-id="6f027-109">Se o valor Irrestrito não for retornado, você precisará executar o seguinte:</span><span class="sxs-lookup"><span data-stu-id="6f027-109">If the value Unrestricted is not returned, you'll need to run this next:</span></span>
    
   ```PowerShell
   Set-ExecutionPolicy -Unrestricted
   ```

2. <span data-ttu-id="6f027-110">Para configurar efetivamente o Skype for Business Server, você precisará:</span><span class="sxs-lookup"><span data-stu-id="6f027-110">To effectively configure Skype for Business Server, you'll need to:</span></span>
    
    - <span data-ttu-id="6f027-111">Familiarizar-se com sua topologia do Skype for Business Server 2015 (como nomes de computador, instâncias de serviço, nomes de site e políticas).</span><span class="sxs-lookup"><span data-stu-id="6f027-111">Be familiar with your Skype for Business Server 2015 topology (such as computer names, service instances, site names, and policies).</span></span>
    
    - <span data-ttu-id="6f027-112">Atribua alguns dos usuários criados a grupos, como grupos de busca do Grupo de Resposta (por exemplo, URIs SIP).</span><span class="sxs-lookup"><span data-stu-id="6f027-112">Assign some of the users that are created to groups, such as Response Group hunt groups (for example, SIP URIs).</span></span>
    
3. <span data-ttu-id="6f027-113">Para executar um script na linha de comando, você pode usar:</span><span class="sxs-lookup"><span data-stu-id="6f027-113">To run a script from command line, you can use:</span></span>
    
   ```PowerShell
   PowerShell.exe -file <path to the file>
   ```

4. <span data-ttu-id="6f027-114">Normalmente, depois que você executar um script desse pacote, os rastreamentos resultantes serão armazenados em um arquivo no mesmo caminho de onde o script foi executado.</span><span class="sxs-lookup"><span data-stu-id="6f027-114">Typically, after you've run a script from this package, the resulting traces will be stored in a file in the same path from where the script was run.</span></span> <span data-ttu-id="6f027-115">Também há um formato de nomen por \<scriptname\> $h$m$s.txt.</span><span class="sxs-lookup"><span data-stu-id="6f027-115">There's a naming format as well, \<scriptname\>$h$m$s.txt.</span></span> <span data-ttu-id="6f027-116">Portanto, se você tiver ArchivingPolicy.ps1 às 12h15, obterá um arquivo de log chamado ArchivingPolicy121500.txt.</span><span class="sxs-lookup"><span data-stu-id="6f027-116">So if you ran the ArchivingPolicy.ps1 at 12:15 PM, you'll get a log file named ArchivingPolicy121500.txt.</span></span>
    
5. <span data-ttu-id="6f027-117">Embora fornecemos esses exemplos para sua configuração de servidor, você pode modificar sua configuração e restaurá-los ou reverter depois que você terminar de executar o teste de carga.</span><span class="sxs-lookup"><span data-stu-id="6f027-117">While we've provided these examples for your server configuration, it's up to you to both modify your configuration and restore or roll it back after you've finished running the load testing.</span></span>
    

