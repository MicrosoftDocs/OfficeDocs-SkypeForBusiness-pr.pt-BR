---
title: Preparar Esquema
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeployMainSchemaPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 337aa234-c5f3-4468-a047-2023848e942c
ROBOTS: NOINDEX, NOFOLLOW
description: Para preparar o esquema para os serviços de domínio Active Directory, execute a etapa preparar esquema no assistente de implantação do Skype for Business Server. Clique em Executar para iniciar a preparação do esquema.
ms.openlocfilehash: 4b0d24ff89badf1b026e6c57a4fbb75f2d46936f
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41691796"
---
# <a name="prepare-schema"></a><span data-ttu-id="9f5cf-104">Preparar Esquema</span><span class="sxs-lookup"><span data-stu-id="9f5cf-104">Prepare Schema</span></span>
 
<span data-ttu-id="9f5cf-105">Para preparar o esquema para os serviços de domínio Active Directory, execute a etapa preparar esquema no assistente de implantação do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="9f5cf-105">To prepare the schema for Active Directory Domain Services, you run the Prepare Schema step in the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="9f5cf-106">Clique em **Executar** para iniciar a preparação do esquema.</span><span class="sxs-lookup"><span data-stu-id="9f5cf-106">Click **Run** to begin the preparation of the schema.</span></span> <span data-ttu-id="9f5cf-107">A etapa preparar esquema lê os arquivos de definição de esquema fornecidos no diretório \Program Files\Skype for Business Server 2019 \ Deployment\Setup no sistema em que o assistente de implantação está sendo executado.</span><span class="sxs-lookup"><span data-stu-id="9f5cf-107">The Prepare Schema step reads the supplied schema definition files in the \Program Files\Skype for Business Server 2019\Deployment\Setup directory on the system that the Deployment Wizard is running on.</span></span> <span data-ttu-id="9f5cf-108">Esses arquivos também estão disponíveis na mídia de instalação no diretório \Support\Schema.</span><span class="sxs-lookup"><span data-stu-id="9f5cf-108">These files are also available on the installation media in the \Support\Schema directory.</span></span> <span data-ttu-id="9f5cf-109">A etapa Preparar Esquema estenderá o esquema e informará o status do processo.</span><span class="sxs-lookup"><span data-stu-id="9f5cf-109">The Prepare Schema step will extend the schema and report the status of the process.</span></span> <span data-ttu-id="9f5cf-110">Você também será notificado quando o processo for concluído.</span><span class="sxs-lookup"><span data-stu-id="9f5cf-110">It will also notify you when the process is complete.</span></span> <span data-ttu-id="9f5cf-111">A tela de resumo permitirá que você exiba os logs do processo.</span><span class="sxs-lookup"><span data-stu-id="9f5cf-111">The summary screen will enable you to view the logs of the process.</span></span> <span data-ttu-id="9f5cf-112">Revise os logs para ter certeza de que a preparação foi concluída e teve êxito.</span><span class="sxs-lookup"><span data-stu-id="9f5cf-112">Review the logs to be sure that the preparation was complete and successful.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="9f5cf-113">Para estender o esquema, é necessário estar conectado ao domínio como membro do grupo Administradores de Esquema e do grupo Administradores de Empresa.</span><span class="sxs-lookup"><span data-stu-id="9f5cf-113">To extend the schema, you must be logged into the domain as a member of the Schema Admins group and the Enterprise Admins group.</span></span> 
  
<span data-ttu-id="9f5cf-114">Classes e atributos são adicionados para estender o esquema de serviços de domínio do Active Directory para dar suporte a objetos de servidor, serviço e usuário do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="9f5cf-114">Classes and attributes are added to extend the Active Directory Domain Services schema to support Skype for Business Server server, service, and user objects.</span></span> <span data-ttu-id="9f5cf-115">Antes de estender o esquema, é necessário fazer o backup do Estado do Sistema do controlador de domínio que detém a função de mestre de esquema.</span><span class="sxs-lookup"><span data-stu-id="9f5cf-115">Before extending the schema, you should take a System State backup of the domain controller that holds the schema master role.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="9f5cf-116">A extensão do esquema não é reversível.</span><span class="sxs-lookup"><span data-stu-id="9f5cf-116">Extending the schema is not reversible.</span></span> <span data-ttu-id="9f5cf-117">Faça o máximo para limitar o possível impacto de uma extensão de esquema sem sucesso e para assegurar que a extensão do esquema terá êxito.</span><span class="sxs-lookup"><span data-stu-id="9f5cf-117">You should make all possible efforts to limit the potential impact of a failed schema extension, and to ensure that the extension of the schema will be successful.</span></span> <span data-ttu-id="9f5cf-118">Isso é fundamental no caso de uma perda de comunicação ou de qualquer outra falha no servidor.</span><span class="sxs-lookup"><span data-stu-id="9f5cf-118">This is particularly critical in the event of loss of communication or any other failure at the server.</span></span> <span data-ttu-id="9f5cf-119">Você deve executar um backup do controlador de domínio do mestre de esquema e um backup completo do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="9f5cf-119">You should perform a backup of the schema master domain controller and a complete backup of Active Directory.</span></span> 
  
<span data-ttu-id="9f5cf-120">Para executar um backup do controlador de domínio do mestre de esquema e um backup completo do Active Directory:</span><span class="sxs-lookup"><span data-stu-id="9f5cf-120">To perform a backup of the schema master domain controller and a complete backup of Active Directory:</span></span>
  
1. <span data-ttu-id="9f5cf-121">Desconecte da rede o controlador de domínio que detém a função de mestre de esquema.</span><span class="sxs-lookup"><span data-stu-id="9f5cf-121">Disconnect the domain controller that holds the schema master role from the network.</span></span>
    
2. <span data-ttu-id="9f5cf-122">Execute um backup do Estado do Sistema do controlador de domínio que detém a função de mestre de esquema.</span><span class="sxs-lookup"><span data-stu-id="9f5cf-122">Perform a System State backup of the domain controller that holds the schema master.</span></span>
    
3. <span data-ttu-id="9f5cf-123">Estenda o esquema.</span><span class="sxs-lookup"><span data-stu-id="9f5cf-123">Extend the schema.</span></span>
    
4. <span data-ttu-id="9f5cf-124">Após o êxito da extensão do esquema, reconecte o controlador de domínio à rede e saiba que a replicação está ativa e funcionando.</span><span class="sxs-lookup"><span data-stu-id="9f5cf-124">When the schema extension is successful, reconnect the domain controller to the network, and be sure that replication is active and working.</span></span>
    
5. <span data-ttu-id="9f5cf-125">No evento improvável de uma falha na extensão do esquema, restaure o estado do sistema do controlador de domínio e do Active Directory usando o backup do estado do sistema que você tirou anteriormente.</span><span class="sxs-lookup"><span data-stu-id="9f5cf-125">In the unlikely event of a schema extension failure, restore the systems state of the domain controller and Active Directory by using the System State backup that you took earlier.</span></span>
    
> [!NOTE]
> <span data-ttu-id="9f5cf-126">Se precisar examinar os arquivos de log criados pelo assistente de implantação do Skype for Business Server, você poderá localizar os arquivos no computador em que o assistente de implantação foi executado, no diretório usuários do usuário do Active Directory que executou a etapa.</span><span class="sxs-lookup"><span data-stu-id="9f5cf-126">If you need to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find the files on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory user who ran the step.</span></span> <span data-ttu-id="9f5cf-127">Por exemplo, se o usuário tiver entrado como administrador do domínio no domínio Contoso.net, os arquivos de log serão localizados em: C:\Users\Administrator.Contoso\AppData\Local\Temp</span><span class="sxs-lookup"><span data-stu-id="9f5cf-127">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp</span></span> 
  

