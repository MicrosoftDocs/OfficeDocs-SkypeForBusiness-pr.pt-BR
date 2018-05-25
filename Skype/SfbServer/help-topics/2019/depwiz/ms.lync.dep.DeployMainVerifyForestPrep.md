---
title: Verificar a replicação da preparação da floresta
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainVerifyForestPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 94e87632-7c28-43df-9238-f5a47c1c43c0
description: 'Para confirmar que tenham a replicação do Catálogo Global e a criação de objetos durante a preparação da floresta foi bem-sucedida, faça o seguinte:'
ms.openlocfilehash: cfb993a9a80bf4b37e76712a58aa6c1fb0c270c3
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2018
---
# <a name="verify-replication-of-forest-preparation"></a><span data-ttu-id="b9502-103">Verificar a replicação da preparação da floresta</span><span class="sxs-lookup"><span data-stu-id="b9502-103">Verify Replication of Forest Preparation</span></span>
 
<span data-ttu-id="b9502-104">Para confirmar que tenham a replicação do Catálogo Global e a criação de objetos durante a preparação da floresta foi bem-sucedida, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b9502-104">To confirm that the replication of the Global Catalog and the creation of objects during Forest Preparation have been successful, do the following:</span></span>
  
1. <span data-ttu-id="b9502-105">Em um controlador de domínio (preferencialmente em um local remoto de outros controladores de domínio), na floresta na qual a Preparação da floresta foi executada, abra **Usuários e Computadores do Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="b9502-105">On a domain controller (preferably in a remote site from the other domain controllers), in the forest where the Forest Preparation was run, open **Active Directory Users and Computers**.</span></span>
    
2. <span data-ttu-id="b9502-106">Em **Usuários e Computadores do Active Directory**, expanda o nome de domínio da sua floresta ou um domínio filho.</span><span class="sxs-lookup"><span data-stu-id="b9502-106">In **Active Directory Users and Computers**, expand the domain name of your forest or a child domain.</span></span>
    
3. <span data-ttu-id="b9502-107">Clique no recipiente de **usuários** no painel esquerdo e procure o grupo Universal CsAdministrator no painel lateral direita.</span><span class="sxs-lookup"><span data-stu-id="b9502-107">Click the **Users** container on the left side pane and look for the Universal group CsAdministrator in the right side pane.</span></span> <span data-ttu-id="b9502-108">Se CsAdministrator (entre oito outros novos grupos universais que começam com Cs) estiver presente, a replicação da preparação da floresta foi bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="b9502-108">If CsAdministrator (among eight other new Universal groups that begin with Cs) is present, replication of the Forest Preparation has been successful.</span></span>
    
4. <span data-ttu-id="b9502-109">Se os grupos ainda não estiver presente, você pode forçar a replicação ou aguarde 15 minutos e atualizar o painel do lado direito.</span><span class="sxs-lookup"><span data-stu-id="b9502-109">If the group(s) is not yet present, you can force the replication or wait 15 minutes and refresh the right side pane.</span></span> <span data-ttu-id="b9502-110">Quando os grupos estiverem presentes, a replicação será concluída.</span><span class="sxs-lookup"><span data-stu-id="b9502-110">When the groups are present, replication is complete.</span></span>
    
> [!TIP]
> <span data-ttu-id="b9502-111">Se desejar examinar os arquivos de log são criados pelo Skype para o Assistente de implantação do Business Server, você pode encontrá-los no computador onde o Assistente de implantação foi executado, no diretório de usuários do usuário Active Directory Domain Services que executou a etapa.</span><span class="sxs-lookup"><span data-stu-id="b9502-111">If you want to review the log files that are created by the Skype for Business Server Deployment Wizard, you can find them on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory Domain Services user who ran the step.</span></span> <span data-ttu-id="b9502-112">Por exemplo, se o usuário logado como administrador de domínio no domínio Contoso.net, os arquivos de log estão localizados em: C:\Users\Administrator.Contoso\AppData\Local\Temp</span><span class="sxs-lookup"><span data-stu-id="b9502-112">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: C:\Users\Administrator.Contoso\AppData\Local\Temp</span></span> 
  

