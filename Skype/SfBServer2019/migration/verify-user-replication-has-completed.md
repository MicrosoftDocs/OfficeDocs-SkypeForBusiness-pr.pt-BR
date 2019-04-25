---
title: Verificar a conclusão da replicação de usuário
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Ao executar o cmdlet Move-CsUser, você pode enfrentar uma falha porque as informações de usuário entre os serviços de domínio Active Directory (AD DS) e o Skype para bancos de dados corporativos Server 2019 estão fora de sincronia porque a replicação inicial está incompleta. O tempo que leva para a conclusão bem-sucedida do Skype para a sincronização inicial do serviço do replicador de usuário do Business Server 2019 depende do número de controladores de domínio que estão hospedados na floresta do Active Directory que hospeda o Skype para negócios Pool de servidor 2019. O Skype para o processo de sincronização inicial do replicador de usuário do Business Server 2019 serviço ocorre quando o Skype para Business Server 2019 servidor Front-End é iniciado pela primeira vez. Depois disso, a sincronização, em seguida, com base no intervalo de replicador de usuários. Conclua as seguintes etapas para verificar se a replicação de usuário foi concluída antes de executar o cmdlet Move-CsUser.
ms.openlocfilehash: bab54e91ebda7a10804980e368e05bb58ff911ff
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231333"
---
# <a name="verify-user-replication-has-completed"></a><span data-ttu-id="3f57b-107">Verificar a conclusão da replicação de usuário</span><span class="sxs-lookup"><span data-stu-id="3f57b-107">Verify user replication has completed</span></span>

<span data-ttu-id="3f57b-108">Ao executar o cmdlet **Move-CsUser** , você pode enfrentar uma falha se as informações do usuário entre os serviços de domínio Active Directory (AD DS) e o Skype para bancos de dados corporativos Server 2019 estão fora de sincronia porque a replicação inicial está incompleta.</span><span class="sxs-lookup"><span data-stu-id="3f57b-108">When running the **Move-CsUser** cmdlet, you may experience a failure if user information between Active Directory Domain Services (AD DS) and the Skype for Business Server 2019 databases are out of sync because the initial replication is incomplete.</span></span> <span data-ttu-id="3f57b-109">O tempo que leva para a conclusão bem-sucedida do Skype para a sincronização inicial do serviço do replicador de usuário do Business Server 2019 depende do número de controladores de domínio que estão hospedados na floresta do Active Directory que hospeda o Skype para negócios Pool de servidor 2019.</span><span class="sxs-lookup"><span data-stu-id="3f57b-109">The time it takes for the successful completion of the Skype for Business Server 2019 User Replicator service's initial synchronization depends on the number of domain controllers that are hosted in the Active Directory forest that hosts the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="3f57b-110">O Skype para o processo de sincronização inicial do replicador de usuário do Business Server 2019 serviço ocorre quando o Skype para Business Server 2019 servidor Front-End é iniciado pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="3f57b-110">The Skype for Business Server 2019 User Replicator service initial synchronization process occurs when the Skype for Business Server 2019 Front End Server is started for the first time.</span></span> <span data-ttu-id="3f57b-111">Depois disso, a sincronização baseia-se no intervalo de replicador de usuários.</span><span class="sxs-lookup"><span data-stu-id="3f57b-111">After that, the synchronization is based on the User Replicator interval.</span></span> <span data-ttu-id="3f57b-112">Conclua as seguintes etapas para verificar se a replicação de usuário que foi concluída antes de executar o cmdlet **Move-CsUser** .</span><span class="sxs-lookup"><span data-stu-id="3f57b-112">Complete the following steps to verify that user replication has completed before running the **Move-CsUser** cmdlet.</span></span> 
  
### <a name="to-verify-that-user-replication-has-completed"></a><span data-ttu-id="3f57b-113">Para verificar se a replicação usuário foi concluída</span><span class="sxs-lookup"><span data-stu-id="3f57b-113">To verify that user replication has completed</span></span>

1. <span data-ttu-id="3f57b-114">Faça logon no computador no qual o Construtor de Topologias está instalado como um membro do grupo Admins. do Domínio ou do grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="3f57b-114">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="3f57b-115">Clique no menu **Iniciar** e, em seguida, clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="3f57b-115">Click the **Start** menu, and then click **Run**.</span></span> 
    
3. <span data-ttu-id="3f57b-116">Insira **eventvwr.exe**e clique em **Okey**.</span><span class="sxs-lookup"><span data-stu-id="3f57b-116">Enter **eventvwr.exe**, and then click **OK**.</span></span>
    
4. <span data-ttu-id="3f57b-117">No Visualizador de eventos, clique em **logs de aplicativos e serviços** para expandi-lo e selecione Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="3f57b-117">In Event Viewer, click **Applications and Services logs** to expand it, and then select Skype for Business Server.</span></span> 
    
5. <span data-ttu-id="3f57b-118">No painel **ações** , clique em **Filtrar Log atual**.</span><span class="sxs-lookup"><span data-stu-id="3f57b-118">In the **Actions** pane, click **Filter Current Log**.</span></span>
    
6. <span data-ttu-id="3f57b-119">Na lista **fontes de evento** , clique em **LS User Replicator**.</span><span class="sxs-lookup"><span data-stu-id="3f57b-119">From the **Event sources** list, click **LS User Replicator**.</span></span>
    
7. <span data-ttu-id="3f57b-120">Em \*\* \<todas as IDs de evento\>\*\*, insira **30024**e clique em **Okey**.</span><span class="sxs-lookup"><span data-stu-id="3f57b-120">In **\<All Event IDs\>**, enter **30024**, and then click **OK**.</span></span> 
    
8. <span data-ttu-id="3f57b-121">Na lista de eventos filtrados, na guia **Geral** , procure uma entrada que afirma que a replicação usuário foi concluída com êxito.</span><span class="sxs-lookup"><span data-stu-id="3f57b-121">In the filtered events list, on the **General** tab, look for an entry that states that user replication has completed successfully.</span></span> 
    

