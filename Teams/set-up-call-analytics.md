---
title: Configurar a análise de chamadas do Microsoft Teams
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, vkorlep
ms.topic: article
ms.assetid: fbf7247a-84ae-46cc-9204-2c45b1c734cd
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
description: Configurar a análise de chamadas por usuário para identificar e solucionar problemas de qualidade de chamada do Microsoft Teams.
ms.openlocfilehash: 233d91a60ea783238e10ed1baa02334494ef6e08
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085307"
---
# <a name="set-up-call-analytics-for-microsoft-teams"></a><span data-ttu-id="7f613-103">Configurar a análise de chamadas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7f613-103">Set up call analytics for Microsoft Teams</span></span>

<span data-ttu-id="7f613-104">Como administrador do Microsoft Teams, você pode usar a análise de chamadas por usuário para solucionar problemas com a qualidade das chamadas e problemas de conexão para **usuários individuais**.</span><span class="sxs-lookup"><span data-stu-id="7f613-104">As a Microsoft Teams admin, you can use per-user call analytics to troubleshoot Teams call quality and connection problems for **individual users**.</span></span> <span data-ttu-id="7f613-105">Para aproveitar ao máximo a análise de chamadas, configure o seguinte:</span><span class="sxs-lookup"><span data-stu-id="7f613-105">To take full advantage of call analytics, set up the following:</span></span>
  
- <span data-ttu-id="7f613-106">Atribua funções de suporte especializadas a pessoas, como agentes de assistência técnica, para permitir que eles vejam a análise de chamadas para os usuários.</span><span class="sxs-lookup"><span data-stu-id="7f613-106">Assign specialized support roles to people, such as helpdesk agents, to let them view call analytics for users.</span></span> <span data-ttu-id="7f613-107">Essas funções de suporte não podem acessar o restante do centro de administração do teams.</span><span class="sxs-lookup"><span data-stu-id="7f613-107">These support roles can't access the rest of the Teams admin center.</span></span> 
    
- <span data-ttu-id="7f613-108">Adicione informações de construção, site e locatário às análises de chamadas por usuário carregando um arquivo de dados. tsv ou. csv.</span><span class="sxs-lookup"><span data-stu-id="7f613-108">Add building, site, and tenant information to per-user call analytics by uploading a .tsv or .csv data file.</span></span>
    
<span data-ttu-id="7f613-109">Quando estiver pronto para começar a usar a análise de chamadas por usuário, leia [usar a análise de chamadas por usuário para solucionar problemas de qualidade de chamada de baixa qualidade](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span><span class="sxs-lookup"><span data-stu-id="7f613-109">When you're ready to start using per-user call analytics, read [Use per-user call analytics to troubleshoot poor call quality](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span></span>
  
## <a name="give-permission-to-support-and-helpdesk-staff"></a><span data-ttu-id="7f613-110">Conceder permissão para a equipe de suporte e helpdesk</span><span class="sxs-lookup"><span data-stu-id="7f613-110">Give permission to support and helpdesk staff</span></span>

<span data-ttu-id="7f613-111">Como administrador do Teams, você tem acesso completo para fazer chamadas para a análise de todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="7f613-111">As the Teams admin, you have full access to call analytics information for all users.</span></span> <span data-ttu-id="7f613-112">Criamos algumas funções especializadas do Azure Active Directory que você pode atribuir à equipe de suporte e aos agentes de helpdesk para que elas também possam acessar a análise de chamadas por usuário (sem ter acesso ao resto do centro de administração do Teams).</span><span class="sxs-lookup"><span data-stu-id="7f613-112">We've created some specialized Azure Active Directory roles that you can assign to support staff and helpdesk agents so they can also access per-user call analytics (without having access to the rest of the Teams admin center).</span></span> <span data-ttu-id="7f613-113">Atribua a função de **especialista de comunicações do teams** a usuários que devem ter um modo de exibição limitado de análise de chamadas por usuário (suporte de camada 1).</span><span class="sxs-lookup"><span data-stu-id="7f613-113">Assign the **Teams communications support specialist** role to users who should have a limited view of per-user call analytics (Tier 1 support).</span></span> <span data-ttu-id="7f613-114">Atribua a função de **engenheiro de suporte de comunicações ao Teams** a usuários que precisam de acesso completo a análises de chamadas por usuário (suporte a nível 2).</span><span class="sxs-lookup"><span data-stu-id="7f613-114">Assign the **Teams communications support engineer** role to users who need full access to per-user call analytics (Tier 2 support).</span></span> <span data-ttu-id="7f613-115">Nenhuma função tem acesso ao restante do centro de administração do teams.</span><span class="sxs-lookup"><span data-stu-id="7f613-115">Neither role has access to the rest of the Teams admin center.</span></span>

<span data-ttu-id="7f613-116">Para saber o que cada uma dessas funções faz, leia [o que faz cada função de suporte do teams](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do)?</span><span class="sxs-lookup"><span data-stu-id="7f613-116">To learn what each of these roles does, read [What does each Teams Support role do](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do)?</span></span>

<span data-ttu-id="7f613-117">Para obter mais informações sobre as funções de administração do Teams, consulte [usar funções de administração do teams para gerenciar o Teams](using-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="7f613-117">For more information about Teams admin roles, see [Use Teams admin roles to manage Teams](using-admin-roles.md).</span></span> <span data-ttu-id="7f613-118">Para saber como atribuir funções de administrador no Azure Active Directory, consulte [Exibir e atribuir funções no Azure Active Directory](https://docs.microsoft.com/Azure/active-directory/users-groups-roles/directory-manage-roles-portal).</span><span class="sxs-lookup"><span data-stu-id="7f613-118">To learn how to assign admin roles in Azure Active Directory, see [View and assign roles in Azure Active Directory](https://docs.microsoft.com/Azure/active-directory/users-groups-roles/directory-manage-roles-portal).</span></span>

<span data-ttu-id="7f613-119">Para saber como atribuir funções administrativas no Azure Active Directory, consulte [Exibir e atribuir funções no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal).</span><span class="sxs-lookup"><span data-stu-id="7f613-119">To learn how to assign administrative roles in Azure Active Directory, see [View and assign roles in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal).</span></span>

## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a><span data-ttu-id="7f613-120">Carregar um arquivo. tsv ou. csv para adicionar informações de criação, site e locatário</span><span class="sxs-lookup"><span data-stu-id="7f613-120">Upload a .tsv or .csv file to add building, site, and tenant information</span></span>

<span data-ttu-id="7f613-121">Você pode adicionar informações de construção, site e locatário a análises de chamadas por usuário carregando um arquivo. csv ou. TSV.</span><span class="sxs-lookup"><span data-stu-id="7f613-121">You can add building, site, and tenant information to per-user call analytics by uploading a .csv or .tsv file.</span></span> <span data-ttu-id="7f613-122">Com todas essas informações, a análise de chamadas pode mapear endereços IP para locais físicos.</span><span class="sxs-lookup"><span data-stu-id="7f613-122">With all this information, call analytics can map IP addresses to physical locations.</span></span> <span data-ttu-id="7f613-123">Os agentes de administradores e helpdesks podem usar essas informações para ajudar a identificar tendências em problemas com chamadas.</span><span class="sxs-lookup"><span data-stu-id="7f613-123">Admins and helpdesk agents can use this information to help spot trends in call problems.</span></span> <span data-ttu-id="7f613-124">Por exemplo, por que os usuários na mesma criação têm problemas de qualidade de chamada semelhantes?</span><span class="sxs-lookup"><span data-stu-id="7f613-124">For example, why are users in the same building having similar call quality problems?</span></span> 

<span data-ttu-id="7f613-125">Se você for um administrador do teams ou do Skype for Business, poderá usar um locatário existente e construir um arquivo de dados do teams ou do painel de qualidade de chamada do Skype for Business (CQD).</span><span class="sxs-lookup"><span data-stu-id="7f613-125">If you're a Teams or Skype for Business admin, you can use an existing tenant and building data file from the Teams or Skype for Business Call Quality Dashboard (CQD).</span></span> <span data-ttu-id="7f613-126">Primeiro, baixe o arquivo do CQD e carregue-o para a análise de chamadas.</span><span class="sxs-lookup"><span data-stu-id="7f613-126">First, you download the file from CQD, then upload it to call analytics.</span></span> 

- <span data-ttu-id="7f613-127">Para baixar um arquivo de dados existente, acesse o painel de qualidade de chamada **do centro de administração do Microsoft Teams**  >  **Call Quality Dashboard**  >  **agora**.</span><span class="sxs-lookup"><span data-stu-id="7f613-127">To download an existing data file, go to **Microsoft Teams admin center** > **Call Quality Dashboard** > **Upload now**.</span></span> <span data-ttu-id="7f613-128">Na lista **meus uploads** , clique em **baixar** ao lado do arquivo desejado.</span><span class="sxs-lookup"><span data-stu-id="7f613-128">In the **My uploads** list, click **Download** next to the file you want.</span></span> 

- <span data-ttu-id="7f613-129">Para carregar o novo arquivo, vá para locais do **centro de administração do Microsoft Teams**  >  **Locations**e, em seguida, selecione **carregar dados de localização** ou **substituir dados de localização**.</span><span class="sxs-lookup"><span data-stu-id="7f613-129">To upload the new file, go to **Microsoft Teams admin center** > **Locations**, and then select **Upload location data** or **Replace location data**.</span></span>
  
<span data-ttu-id="7f613-130">Se você estiver criando o arquivo. tsv ou. csv do zero, consulte [carregar dados do locatário e construção de dados](CQD-upload-tenant-building-data.md).</span><span class="sxs-lookup"><span data-stu-id="7f613-130">If you're creating the .tsv or .csv file from scratch, see [Upload tenant and building data](CQD-upload-tenant-building-data.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="7f613-131">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="7f613-131">Related topics</span></span>

[<span data-ttu-id="7f613-132">Use a análise de chamadas por usuário para solucionar problemas de qualidade de chamadas ruins</span><span class="sxs-lookup"><span data-stu-id="7f613-132">Use per-user call analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="7f613-133">Solução de problemas do Teams</span><span class="sxs-lookup"><span data-stu-id="7f613-133">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
