---
title: Verificar a conclusão da replicação de usuário
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Ao executar o cmdlet Move-CsUser, você pode ter uma falha porque as informações do usuário entre os serviços de domínio Active Directory (AD DS) e os bancos de dados do Skype for Business Server 2019 estão fora de sincronia porque a replicação inicial está incompleta. O tempo necessário para a conclusão bem-sucedida da sincronização inicial do serviço Duplicador de usuários do Skype for Business Server 2019 depende do número de controladores de domínio hospedados na floresta do Active Directory que hospeda o Skype for Business Server 2019 pool. O processo de sincronização inicial do serviço Duplicador de usuários do Skype for Business Server 2019 ocorre quando o servidor front-end do Skype for Business Server 2019 é iniciado pela primeira vez. Depois disso, a sincronização é baseada no intervalo de Duplicador do usuário. Conclua as etapas a seguir para verificar se a replicação do usuário foi concluída antes de executar o cmdlet Move-CsUser.
ms.openlocfilehash: 31f4f9f1045367e376d4536df54c32be14580312
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812649"
---
# <a name="verify-user-replication-has-completed"></a><span data-ttu-id="d2e27-107">Verificar a conclusão da replicação de usuário</span><span class="sxs-lookup"><span data-stu-id="d2e27-107">Verify user replication has completed</span></span>

<span data-ttu-id="d2e27-108">Ao executar o cmdlet **move-CsUser** , você pode ter uma falha se as informações do usuário entre os serviços de domínio Active Directory (AD DS) e os bancos de dados do Skype for Business Server 2019 estiverem fora de sincronia porque a replicação inicial está incompleta.</span><span class="sxs-lookup"><span data-stu-id="d2e27-108">When running the **Move-CsUser** cmdlet, you may experience a failure if user information between Active Directory Domain Services (AD DS) and the Skype for Business Server 2019 databases are out of sync because the initial replication is incomplete.</span></span> <span data-ttu-id="d2e27-109">O tempo necessário para a conclusão bem-sucedida da sincronização inicial do serviço Duplicador de usuários do Skype for Business Server 2019 depende do número de controladores de domínio hospedados na floresta do Active Directory que hospeda o Skype for Business Server 2019 pool.</span><span class="sxs-lookup"><span data-stu-id="d2e27-109">The time it takes for the successful completion of the Skype for Business Server 2019 User Replicator service's initial synchronization depends on the number of domain controllers that are hosted in the Active Directory forest that hosts the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="d2e27-110">O processo de sincronização inicial do serviço Duplicador de usuários do Skype for Business Server 2019 ocorre quando o servidor front-end do Skype for Business Server 2019 é iniciado pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="d2e27-110">The Skype for Business Server 2019 User Replicator service initial synchronization process occurs when the Skype for Business Server 2019 Front End Server is started for the first time.</span></span> <span data-ttu-id="d2e27-111">Depois disso, a sincronização é baseada no intervalo do Duplicador do usuário.</span><span class="sxs-lookup"><span data-stu-id="d2e27-111">After that, the synchronization is based on the User Replicator interval.</span></span> <span data-ttu-id="d2e27-112">Conclua as etapas a seguir para verificar se a duplicação do usuário foi concluída antes de executar o cmdlet **move-CsUser** .</span><span class="sxs-lookup"><span data-stu-id="d2e27-112">Complete the following steps to verify that user replication has completed before running the **Move-CsUser** cmdlet.</span></span> 
  
### <a name="to-verify-that-user-replication-has-completed"></a><span data-ttu-id="d2e27-113">Para verificar se a duplicação do usuário foi concluída</span><span class="sxs-lookup"><span data-stu-id="d2e27-113">To verify that user replication has completed</span></span>

1. <span data-ttu-id="d2e27-114">Faça logon no computador no qual o Construtor de Topologias está instalado como um membro do grupo Admins. do Domínio ou do grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="d2e27-114">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="d2e27-115">Clique no menu **Iniciar** e, em seguida, clique em **executar**.</span><span class="sxs-lookup"><span data-stu-id="d2e27-115">Click the **Start** menu, and then click **Run**.</span></span> 
    
3. <span data-ttu-id="d2e27-116">Insira **eventvwr. exe**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="d2e27-116">Enter **eventvwr.exe**, and then click **OK**.</span></span>
    
4. <span data-ttu-id="d2e27-117">Em Visualizador de eventos, clique em **logs de aplicativos e serviços** para expandi-lo e, em seguida, selecione Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d2e27-117">In Event Viewer, click **Applications and Services logs** to expand it, and then select Skype for Business Server.</span></span> 
    
5. <span data-ttu-id="d2e27-118">No painel **ações** , clique em **Filtrar log atual**.</span><span class="sxs-lookup"><span data-stu-id="d2e27-118">In the **Actions** pane, click **Filter Current Log**.</span></span>
    
6. <span data-ttu-id="d2e27-119">Na lista **fontes de eventos** , clique em **Duplicador de usuários ls**.</span><span class="sxs-lookup"><span data-stu-id="d2e27-119">From the **Event sources** list, click **LS User Replicator**.</span></span>
    
7. <span data-ttu-id="d2e27-120">Em \*\* \<todas as identificações\>de evento\*\*, insira **30024**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="d2e27-120">In **\<All Event IDs\>**, enter **30024**, and then click **OK**.</span></span> 
    
8. <span data-ttu-id="d2e27-121">Na lista eventos filtrados, na guia **geral** , procure por uma entrada que declara que a duplicação do usuário foi concluída com êxito.</span><span class="sxs-lookup"><span data-stu-id="d2e27-121">In the filtered events list, on the **General** tab, look for an entry that states that user replication has completed successfully.</span></span> 
    

