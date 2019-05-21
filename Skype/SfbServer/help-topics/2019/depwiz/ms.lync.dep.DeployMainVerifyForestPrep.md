---
title: Verificar a Replicação da Preparação da Floresta
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainVerifyForestPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 94e87632-7c28-43df-9238-f5a47c1c43c0
ROBOTS: NOINDEX, NOFOLLOW
description: 'Para confirmar se a replicação do catálogo global e a criação de objetos durante a preparação da floresta foram bem-sucedidas, faça o seguinte:'
ms.openlocfilehash: c7fe425dcbecf2bfba02d4862bc3a29b75e16910
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303338"
---
# <a name="verify-replication-of-forest-preparation"></a><span data-ttu-id="50dcd-103">Verificar a Replicação da Preparação da Floresta</span><span class="sxs-lookup"><span data-stu-id="50dcd-103">Verify Replication of Forest Preparation</span></span>
 
<span data-ttu-id="50dcd-104">Para confirmar se a replicação do catálogo global e a criação de objetos durante a preparação da floresta foram bem-sucedidas, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="50dcd-104">To confirm that the replication of the Global Catalog and the creation of objects during Forest Preparation have been successful, do the following:</span></span>
  
1. <span data-ttu-id="50dcd-105">Em um controlador de domínio (preferencialmente em um local remoto de outros controladores de domínio), na floresta na qual a Preparação da floresta foi executada, abra **Usuários e Computadores do Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="50dcd-105">On a domain controller (preferably in a remote site from the other domain controllers), in the forest where the Forest Preparation was run, open **Active Directory Users and Computers**.</span></span>
    
2. <span data-ttu-id="50dcd-106">Em **Usuários e Computadores do Active Directory**, expanda o nome de domínio da sua floresta ou um domínio filho.</span><span class="sxs-lookup"><span data-stu-id="50dcd-106">In **Active Directory Users and Computers**, expand the domain name of your forest or a child domain.</span></span>
    
3. <span data-ttu-id="50dcd-107">Clique no contêiner **usuários** no painel esquerdo e procure o grupo universal CsAdministrator no painel do lado direito.</span><span class="sxs-lookup"><span data-stu-id="50dcd-107">Click the **Users** container on the left side pane and look for the Universal group CsAdministrator in the right side pane.</span></span> <span data-ttu-id="50dcd-108">Se CsAdministrator (entre oito outros novos grupos universais que comecem com o CS) estiver presente, a replicação da preparação da floresta foi bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="50dcd-108">If CsAdministrator (among eight other new Universal groups that begin with Cs) is present, replication of the Forest Preparation has been successful.</span></span>
    
4. <span data-ttu-id="50dcd-109">Se o (s) grupo (s) ainda não estiver presente, você pode forçar a replicação ou aguardar 15 minutos e atualizar o painel do lado direito.</span><span class="sxs-lookup"><span data-stu-id="50dcd-109">If the group(s) is not yet present, you can force the replication or wait 15 minutes and refresh the right side pane.</span></span> <span data-ttu-id="50dcd-110">Quando os grupos estiverem presentes, a replicação será concluída.</span><span class="sxs-lookup"><span data-stu-id="50dcd-110">When the groups are present, replication is complete.</span></span>
    
> [!TIP]
> <span data-ttu-id="50dcd-111">Se desejar examinar os arquivos de log criados pelo assistente de implantação do Skype for Business Server, você poderá encontrá-los no computador em que o assistente de implantação foi executado, no diretório usuários do usuário dos serviços de domínio Active Directory que executou a etapa.</span><span class="sxs-lookup"><span data-stu-id="50dcd-111">If you want to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory Domain Services user who ran the step.</span></span> <span data-ttu-id="50dcd-112">Por exemplo, se o usuário tiver entrado como administrador do domínio no domínio Contoso.net, os arquivos de log serão localizados em: C:\Users\Administrator.Contoso\AppData\Local\Temp</span><span class="sxs-lookup"><span data-stu-id="50dcd-112">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp</span></span> 
  

