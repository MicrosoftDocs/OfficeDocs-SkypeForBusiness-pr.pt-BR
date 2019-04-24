---
title: Preparar Esquema
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainSchemaPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 337aa234-c5f3-4468-a047-2023848e942c
ROBOTS: NOINDEX, NOFOLLOW
description: Para preparar o esquema do Active Directory Domain Services, você executar a etapa de preparação de esquema no Skype para o Assistente de implantação de servidor de negócios. Clique em Executar para iniciar a preparação do esquema.
ms.openlocfilehash: fc9981e5a6f298d4d7697b00cde2798dd0b859ef
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32216140"
---
# <a name="prepare-schema"></a><span data-ttu-id="fa6e6-104">Preparar Esquema</span><span class="sxs-lookup"><span data-stu-id="fa6e6-104">Prepare Schema</span></span>
 
<span data-ttu-id="fa6e6-105">Para preparar o esquema do Active Directory Domain Services, você executar a etapa de preparação de esquema no Skype para o Assistente de implantação de servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="fa6e6-105">To prepare the schema for Active Directory Domain Services, you run the Prepare Schema step in the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="fa6e6-106">Clique em **Executar** para iniciar a preparação do esquema.</span><span class="sxs-lookup"><span data-stu-id="fa6e6-106">Click **Run** to begin the preparation of the schema.</span></span> <span data-ttu-id="fa6e6-107">A etapa de preparar esquema lê o esquema fornecido arquivos de definição no \Program Files\Skype para o diretório de 2019\Deployment\Setup Business Server no sistema que está executando o Assistente para implantação.</span><span class="sxs-lookup"><span data-stu-id="fa6e6-107">The Prepare Schema step reads the supplied schema definition files in the \Program Files\Skype for Business Server 2019\Deployment\Setup directory on the system that the Deployment Wizard is running on.</span></span> <span data-ttu-id="fa6e6-108">Esses arquivos também estão disponíveis na mídia de instalação no diretório \Support\Schema.</span><span class="sxs-lookup"><span data-stu-id="fa6e6-108">These files are also available on the installation media in the \Support\Schema directory.</span></span> <span data-ttu-id="fa6e6-109">A etapa Preparar Esquema estenderá o esquema e informará o status do processo.</span><span class="sxs-lookup"><span data-stu-id="fa6e6-109">The Prepare Schema step will extend the schema and report the status of the process.</span></span> <span data-ttu-id="fa6e6-110">Você também será notificado quando o processo for concluído.</span><span class="sxs-lookup"><span data-stu-id="fa6e6-110">It will also notify you when the process is complete.</span></span> <span data-ttu-id="fa6e6-111">A tela de resumo permitirá que você exiba os logs do processo.</span><span class="sxs-lookup"><span data-stu-id="fa6e6-111">The summary screen will enable you to view the logs of the process.</span></span> <span data-ttu-id="fa6e6-112">Revise os logs para ter certeza de que a preparação foi concluída e teve êxito.</span><span class="sxs-lookup"><span data-stu-id="fa6e6-112">Review the logs to be sure that the preparation was complete and successful.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="fa6e6-113">Para estender o esquema, é necessário estar conectado ao domínio como membro do grupo Administradores de Esquema e do grupo Administradores de Empresa.</span><span class="sxs-lookup"><span data-stu-id="fa6e6-113">To extend the schema, you must be logged into the domain as a member of the Schema Admins group and the Enterprise Admins group.</span></span> 
  
<span data-ttu-id="fa6e6-114">Classes e atributos são adicionados para estender o esquema do Active Directory Domain Services para suportar Skype para servidor Business Server, serviço e objetos de usuário.</span><span class="sxs-lookup"><span data-stu-id="fa6e6-114">Classes and attributes are added to extend the Active Directory Domain Services schema to support Skype for Business Server server, service, and user objects.</span></span> <span data-ttu-id="fa6e6-115">Antes de estender o esquema, é necessário fazer o backup do Estado do Sistema do controlador de domínio que detém a função de mestre de esquema.</span><span class="sxs-lookup"><span data-stu-id="fa6e6-115">Before extending the schema, you should take a System State backup of the domain controller that holds the schema master role.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="fa6e6-116">A extensão do esquema não é reversível.</span><span class="sxs-lookup"><span data-stu-id="fa6e6-116">Extending the schema is not reversible.</span></span> <span data-ttu-id="fa6e6-117">Faça o máximo para limitar o possível impacto de uma extensão de esquema sem sucesso e para assegurar que a extensão do esquema terá êxito.</span><span class="sxs-lookup"><span data-stu-id="fa6e6-117">You should make all possible efforts to limit the potential impact of a failed schema extension, and to ensure that the extension of the schema will be successful.</span></span> <span data-ttu-id="fa6e6-118">Isso é fundamental no caso de uma perda de comunicação ou de qualquer outra falha no servidor.</span><span class="sxs-lookup"><span data-stu-id="fa6e6-118">This is particularly critical in the event of loss of communication or any other failure at the server.</span></span> <span data-ttu-id="fa6e6-119">Você deve executar um backup do controlador de domínio mestre de esquema e um backup completo do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="fa6e6-119">You should perform a backup of the schema master domain controller and a complete backup of Active Directory.</span></span> 
  
<span data-ttu-id="fa6e6-120">Para realizar um backup do controlador de domínio mestre de esquema e um backup completo do Active Directory:</span><span class="sxs-lookup"><span data-stu-id="fa6e6-120">To perform a backup of the schema master domain controller and a complete backup of Active Directory:</span></span>
  
1. <span data-ttu-id="fa6e6-121">Desconecte da rede o controlador de domínio que detém a função de mestre de esquema.</span><span class="sxs-lookup"><span data-stu-id="fa6e6-121">Disconnect the domain controller that holds the schema master role from the network.</span></span>
    
2. <span data-ttu-id="fa6e6-122">Execute um backup do Estado do Sistema do controlador de domínio que detém a função de mestre de esquema.</span><span class="sxs-lookup"><span data-stu-id="fa6e6-122">Perform a System State backup of the domain controller that holds the schema master.</span></span>
    
3. <span data-ttu-id="fa6e6-123">Estenda o esquema.</span><span class="sxs-lookup"><span data-stu-id="fa6e6-123">Extend the schema.</span></span>
    
4. <span data-ttu-id="fa6e6-124">Após o êxito da extensão do esquema, reconecte o controlador de domínio à rede e saiba que a replicação está ativa e funcionando.</span><span class="sxs-lookup"><span data-stu-id="fa6e6-124">When the schema extension is successful, reconnect the domain controller to the network, and be sure that replication is active and working.</span></span>
    
5. <span data-ttu-id="fa6e6-125">Na hipótese remota de uma expansão fracassada de esquema, restaure o estado do sistema do controlador de domínio e do Active Directory usando o backup do estado do sistema realizado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="fa6e6-125">In the unlikely event of a schema extension failure, restore the systems state of the domain controller and Active Directory by using the System State backup that you took earlier.</span></span>
    
> [!NOTE]
> <span data-ttu-id="fa6e6-126">Se você precisar revisar os arquivos de log são criados pelo Skype para o Assistente de implantação de servidor de negócios, você pode encontrar os arquivos no computador onde o Assistente de implantação foi executado, no diretório de usuários do usuário do Active Directory que executou a etapa.</span><span class="sxs-lookup"><span data-stu-id="fa6e6-126">If you need to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find the files on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory user who ran the step.</span></span> <span data-ttu-id="fa6e6-127">Por exemplo, se o usuário logado como administrador de domínio no domínio Contoso.net, os arquivos de log estão localizados em: C:\Users\Administrator.Contoso\AppData\Local\Temp</span><span class="sxs-lookup"><span data-stu-id="fa6e6-127">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp</span></span> 
  

