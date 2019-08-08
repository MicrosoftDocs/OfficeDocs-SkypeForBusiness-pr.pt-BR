---
title: Verificar a conclusão da replicação de usuário
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Ao executar o cmdlet Move-CsUser, você pode ter uma falha porque as informações do usuário entre os serviços de domínio Active Directory (AD DS) e os bancos de dados do Skype for Business Server 2019 estão fora de sincronia porque a replicação inicial está incompleta. O tempo necessário para a conclusão bem-sucedida da sincronização inicial do serviço Duplicador de usuários do Skype for Business Server 2019 depende do número de controladores de domínio hospedados na floresta do Active Directory que hospeda o Skype for Business Server 2019 pool. O processo de sincronização inicial do serviço Duplicador de usuários do Skype for Business Server 2019 ocorre quando o servidor front-end do Skype for Business Server 2019 é iniciado pela primeira vez. Depois disso, a sincronização é baseada no intervalo de Duplicador do usuário. Conclua as etapas a seguir para verificar se a replicação do usuário foi concluída antes de executar o cmdlet Move-CsUser.
ms.openlocfilehash: 12bb3c29f703287934358f331dc945830e318afb
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243708"
---
# <a name="verify-user-replication-has-completed"></a><span data-ttu-id="9e5c7-107">Verificar a conclusão da replicação de usuário</span><span class="sxs-lookup"><span data-stu-id="9e5c7-107">Verify user replication has completed</span></span>

<span data-ttu-id="9e5c7-108">Ao executar o cmdlet **move-CsUser** , você pode ter uma falha se as informações do usuário entre os serviços de domínio Active Directory (AD DS) e os bancos de dados do Skype for Business Server 2019 estiverem fora de sincronia porque a replicação inicial está incompleta.</span><span class="sxs-lookup"><span data-stu-id="9e5c7-108">When running the **Move-CsUser** cmdlet, you may experience a failure if user information between Active Directory Domain Services (AD DS) and the Skype for Business Server 2019 databases are out of sync because the initial replication is incomplete.</span></span> <span data-ttu-id="9e5c7-109">O tempo necessário para a conclusão bem-sucedida da sincronização inicial do serviço Duplicador de usuários do Skype for Business Server 2019 depende do número de controladores de domínio hospedados na floresta do Active Directory que hospeda o Skype for Business Server 2019 pool.</span><span class="sxs-lookup"><span data-stu-id="9e5c7-109">The time it takes for the successful completion of the Skype for Business Server 2019 User Replicator service's initial synchronization depends on the number of domain controllers that are hosted in the Active Directory forest that hosts the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="9e5c7-110">O processo de sincronização inicial do serviço Duplicador de usuários do Skype for Business Server 2019 ocorre quando o servidor front-end do Skype for Business Server 2019 é iniciado pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="9e5c7-110">The Skype for Business Server 2019 User Replicator service initial synchronization process occurs when the Skype for Business Server 2019 Front End Server is started for the first time.</span></span> <span data-ttu-id="9e5c7-111">Depois disso, a sincronização é baseada no intervalo do Duplicador do usuário.</span><span class="sxs-lookup"><span data-stu-id="9e5c7-111">After that, the synchronization is based on the User Replicator interval.</span></span> <span data-ttu-id="9e5c7-112">Conclua as etapas a seguir para verificar se a duplicação do usuário foi concluída antes de executar o cmdlet **move-CsUser** .</span><span class="sxs-lookup"><span data-stu-id="9e5c7-112">Complete the following steps to verify that user replication has completed before running the **Move-CsUser** cmdlet.</span></span> 
  
### <a name="to-verify-that-user-replication-has-completed"></a><span data-ttu-id="9e5c7-113">Para verificar se a duplicação do usuário foi concluída</span><span class="sxs-lookup"><span data-stu-id="9e5c7-113">To verify that user replication has completed</span></span>

1. <span data-ttu-id="9e5c7-114">Faça logon no computador no qual o Construtor de Topologias está instalado como um membro do grupo Admins. do Domínio ou do grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="9e5c7-114">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="9e5c7-115">Clique no menu **Iniciar** e, em seguida, clique em **executar**.</span><span class="sxs-lookup"><span data-stu-id="9e5c7-115">Click the **Start** menu, and then click **Run**.</span></span> 
    
3. <span data-ttu-id="9e5c7-116">Insira **eventvwr. exe**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="9e5c7-116">Enter **eventvwr.exe**, and then click **OK**.</span></span>
    
4. <span data-ttu-id="9e5c7-117">Em Visualizador de eventos, clique em **logs de aplicativos e serviços** para expandi-lo e, em seguida, selecione Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="9e5c7-117">In Event Viewer, click **Applications and Services logs** to expand it, and then select Skype for Business Server.</span></span> 
    
5. <span data-ttu-id="9e5c7-118">No painel **ações** , clique em **Filtrar log atual**.</span><span class="sxs-lookup"><span data-stu-id="9e5c7-118">In the **Actions** pane, click **Filter Current Log**.</span></span>
    
6. <span data-ttu-id="9e5c7-119">Na lista **fontes de eventos** , clique em duplicador de **usuários ls**.</span><span class="sxs-lookup"><span data-stu-id="9e5c7-119">From the **Event sources** list, click **LS User Replicator**.</span></span>
    
7. <span data-ttu-id="9e5c7-120">Em \*\* \<todas as\>identificações de evento\*\*, insira **30024**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="9e5c7-120">In **\<All Event IDs\>**, enter **30024**, and then click **OK**.</span></span> 
    
8. <span data-ttu-id="9e5c7-121">Na lista eventos filtrados, na guia **geral** , procure por uma entrada que declara que a duplicação do usuário foi concluída com êxito.</span><span class="sxs-lookup"><span data-stu-id="9e5c7-121">In the filtered events list, on the **General** tab, look for an entry that states that user replication has completed successfully.</span></span> 
    

