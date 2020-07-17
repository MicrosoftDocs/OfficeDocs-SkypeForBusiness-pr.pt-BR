---
title: Verificar a conclusão da replicação de usuário
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Ao executar o cmdlet Move-CsUser, você pode ter uma falha porque as informações do usuário entre os serviços de domínio do Active Directory (AD DS) e os bancos de dados do Skype for Business Server 2019 estão fora de sincronia porque a replicação inicial está incompleta. O tempo necessário para a conclusão bem-sucedida da sincronização inicial do serviço replicador de usuários do Skype for Business Server 2019 depende do número de controladores de domínio hospedados na floresta do Active Directory que hospeda o pool do Skype for Business Server 2019. O processo de sincronização inicial do serviço replicador de usuários do Skype for Business Server 2019 ocorre quando o servidor front-end do Skype for Business Server 2019 é iniciado pela primeira vez. Depois disso, a sincronização se baseia no intervalo do Replicador de Usuário. Conclua as etapas a seguir para verificar se a replicação do usuário foi concluída antes de executar o cmdlet Move-CsUser.
ms.openlocfilehash: 5aa832216cc5eddce1d80cc9401ec9992c9edbf1
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751643"
---
# <a name="verify-user-replication-has-completed"></a><span data-ttu-id="467d9-107">Verificar a conclusão da replicação de usuário</span><span class="sxs-lookup"><span data-stu-id="467d9-107">Verify user replication has completed</span></span>

<span data-ttu-id="467d9-108">Ao executar o cmdlet **move-CsUser** , você pode ter uma falha se as informações do usuário entre os serviços de domínio do Active Directory (AD DS) e os bancos de dados do Skype for Business Server 2019 estão fora de sincronia, pois a replicação inicial está incompleta.</span><span class="sxs-lookup"><span data-stu-id="467d9-108">When running the **Move-CsUser** cmdlet, you may experience a failure if user information between Active Directory Domain Services (AD DS) and the Skype for Business Server 2019 databases are out of sync because the initial replication is incomplete.</span></span> <span data-ttu-id="467d9-109">O tempo necessário para a conclusão bem-sucedida da sincronização inicial do serviço replicador de usuários do Skype for Business Server 2019 depende do número de controladores de domínio hospedados na floresta do Active Directory que hospeda o pool do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="467d9-109">The time it takes for the successful completion of the Skype for Business Server 2019 User Replicator service's initial synchronization depends on the number of domain controllers that are hosted in the Active Directory forest that hosts the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="467d9-110">O processo de sincronização inicial do serviço replicador de usuários do Skype for Business Server 2019 ocorre quando o servidor front-end do Skype for Business Server 2019 é iniciado pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="467d9-110">The Skype for Business Server 2019 User Replicator service initial synchronization process occurs when the Skype for Business Server 2019 Front End Server is started for the first time.</span></span> <span data-ttu-id="467d9-111">Depois, a sincronização é baseada no intervalo do replicador de usuários.</span><span class="sxs-lookup"><span data-stu-id="467d9-111">After that, the synchronization is based on the User Replicator interval.</span></span> <span data-ttu-id="467d9-112">Conclua as etapas a seguir para verificar se a replicação do usuário foi concluída antes de executar o cmdlet **move-CsUser** .</span><span class="sxs-lookup"><span data-stu-id="467d9-112">Complete the following steps to verify that user replication has completed before running the **Move-CsUser** cmdlet.</span></span> 
  
### <a name="to-verify-that-user-replication-has-completed"></a><span data-ttu-id="467d9-113">Para verificar que a replicação de usuário foi concluída</span><span class="sxs-lookup"><span data-stu-id="467d9-113">To verify that user replication has completed</span></span>

1. <span data-ttu-id="467d9-114">Faça logon no computador no qual o Construtor de Topologias está instalado como um membro do grupo Admins. do Domínio ou do grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="467d9-114">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="467d9-115">Clique no menu **Iniciar** e em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="467d9-115">Click the **Start** menu, and then click **Run**.</span></span> 
    
3. <span data-ttu-id="467d9-116">Digite **eventvwr.exe** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="467d9-116">Enter **eventvwr.exe**, and then click **OK**.</span></span>
    
4. <span data-ttu-id="467d9-117">No Visualizador de eventos, clique em **logs de aplicativos e serviços** para expandi-lo e selecione Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="467d9-117">In Event Viewer, click **Applications and Services logs** to expand it, and then select Skype for Business Server.</span></span> 
    
5. <span data-ttu-id="467d9-118">No painel **Ações**, clique em **Filtrar Log Atual**.</span><span class="sxs-lookup"><span data-stu-id="467d9-118">In the **Actions** pane, click **Filter Current Log**.</span></span>
    
6. <span data-ttu-id="467d9-119">Na lista **Fontes de evento**, clique em **Replicador de Usuário LS**.</span><span class="sxs-lookup"><span data-stu-id="467d9-119">From the **Event sources** list, click **LS User Replicator**.</span></span>
    
7. <span data-ttu-id="467d9-120">Em **\<All Event IDs\>** , insira **30024**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="467d9-120">In **\<All Event IDs\>**, enter **30024**, and then click **OK**.</span></span> 
    
8. <span data-ttu-id="467d9-121">Na lista de eventos filtrados, na guia **geral** , procure uma entrada que indique que a replicação do usuário foi concluída com êxito.</span><span class="sxs-lookup"><span data-stu-id="467d9-121">In the filtered events list, on the **General** tab, look for an entry that states that user replication has completed successfully.</span></span> 
    

