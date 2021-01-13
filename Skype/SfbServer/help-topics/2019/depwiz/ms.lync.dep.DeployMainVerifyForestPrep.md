---
title: Verificar a Replicação da Preparação da Floresta
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainVerifyForestPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 94e87632-7c28-43df-9238-f5a47c1c43c0
ROBOTS: NOINDEX, NOFOLLOW
description: 'Para confirmar se a replicação do Catálogo Global e a criação de objetos durante a Preparação da Floresta foi bem-sucedida, faça o seguinte:'
ms.openlocfilehash: 299b738bbfa14ad13825e5c08e87c03167c9f4cc
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801591"
---
# <a name="verify-replication-of-forest-preparation"></a><span data-ttu-id="ed505-103">Verificar a Replicação da Preparação da Floresta</span><span class="sxs-lookup"><span data-stu-id="ed505-103">Verify Replication of Forest Preparation</span></span>
 
<span data-ttu-id="ed505-104">Para confirmar se a replicação do Catálogo Global e a criação de objetos durante a Preparação da Floresta foi bem-sucedida, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="ed505-104">To confirm that the replication of the Global Catalog and the creation of objects during Forest Preparation have been successful, do the following:</span></span>
  
1. <span data-ttu-id="ed505-105">Em um controlador de domínio (preferencialmente em um site remoto de outros controladores de domínio), na floresta na qual a Preparação da Floresta foi executada, abra **Usuários e Computadores do Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="ed505-105">On a domain controller (preferably in a remote site from the other domain controllers), in the forest where the Forest Preparation was run, open **Active Directory Users and Computers**.</span></span>
    
2. <span data-ttu-id="ed505-106">Em **Usuários e Computadores do Active Directory**, expanda o nome do domínio de sua floresta ou domínio filho.</span><span class="sxs-lookup"><span data-stu-id="ed505-106">In **Active Directory Users and Computers**, expand the domain name of your forest or a child domain.</span></span>
    
3. <span data-ttu-id="ed505-107">Clique no **contêiner** Usuários no painel esquerdo e procure o grupo Universal CsAdministrator no painel direito.</span><span class="sxs-lookup"><span data-stu-id="ed505-107">Click the **Users** container on the left side pane and look for the Universal group CsAdministrator in the right side pane.</span></span> <span data-ttu-id="ed505-108">Se CsAdministrator (entre oito outros novos grupos Universais que começam com Cs) estiver presente, a replicação da Preparação da Floresta foi bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="ed505-108">If CsAdministrator (among eight other new Universal groups that begin with Cs) is present, replication of the Forest Preparation has been successful.</span></span>
    
4. <span data-ttu-id="ed505-p102">Caso o(s) grupo(s) ainda não estejam presentes, você pode forçar a replicação ou aguardar 15 minutos e atualizar o painel do lado direito. A replicação está completa quando os grupos estiverem presentes.</span><span class="sxs-lookup"><span data-stu-id="ed505-p102">If the group(s) is not yet present, you can force the replication or wait 15 minutes and refresh the right side pane. When the groups are present, replication is complete.</span></span>
    
> [!TIP]
> <span data-ttu-id="ed505-111">Se você quiser revisar os arquivos de log criados pelo Assistente de Implantação do Skype for Business Server, poderá encontrá-los no computador no qual o Assistente de Implantação foi executado, no diretório Usuários do usuário dos Serviços de Domínio Active Directory que executaram a etapa.</span><span class="sxs-lookup"><span data-stu-id="ed505-111">If you want to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory Domain Services user who ran the step.</span></span> <span data-ttu-id="ed505-112">Por exemplo, se o usuário fez logon como administrador de domínio no domínio Contoso.net, os arquivos de log estão localizados em: C:\Users\Administrator.Contoso\AppData\Local\Temp</span><span class="sxs-lookup"><span data-stu-id="ed505-112">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp</span></span> 
  

