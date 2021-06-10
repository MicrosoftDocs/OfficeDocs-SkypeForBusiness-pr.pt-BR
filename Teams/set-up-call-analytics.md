---
title: Configurar análise de chamada para Microsoft Teams
ms.author: serdars
author: SerdarSoysal
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
description: Configurar a análise de chamada por usuário para identificar e solucionar problemas Microsoft Teams de qualidade de chamada.
ms.openlocfilehash: 209fcad851f5ba7b0183a9988372e249f99cc4fd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117129"
---
# <a name="set-up-call-analytics-for-microsoft-teams"></a><span data-ttu-id="c6eb0-103">Configurar análise de chamada para Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c6eb0-103">Set up call analytics for Microsoft Teams</span></span>

<span data-ttu-id="c6eb0-104">Como administrador Microsoft Teams, você pode usar a análise de chamada por usuário para solucionar problemas de Teams de conexão e qualidade de chamada para **usuários individuais.**</span><span class="sxs-lookup"><span data-stu-id="c6eb0-104">As a Microsoft Teams admin, you can use per-user call analytics to troubleshoot Teams call quality and connection problems for **individual users**.</span></span> <span data-ttu-id="c6eb0-105">Para aproveitar ao máximo a análise de chamada, de configurar o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c6eb0-105">To take full advantage of call analytics, set up the following:</span></span>
  
- <span data-ttu-id="c6eb0-106">Atribua funções de suporte especializadas a pessoas, como agentes auxiliares, para permitir que eles exibirem a análise de chamada para usuários.</span><span class="sxs-lookup"><span data-stu-id="c6eb0-106">Assign specialized support roles to people, such as helpdesk agents, to let them view call analytics for users.</span></span> <span data-ttu-id="c6eb0-107">Essas funções de suporte não podem acessar o restante do Teams de administração.</span><span class="sxs-lookup"><span data-stu-id="c6eb0-107">These support roles can't access the rest of the Teams admin center.</span></span> 
    
- <span data-ttu-id="c6eb0-108">Adicione informações de construção, site e locatário à análise de chamada por usuário carregando um arquivo de dados .tsv ou .csv de dados.</span><span class="sxs-lookup"><span data-stu-id="c6eb0-108">Add building, site, and tenant information to per-user call analytics by uploading a .tsv or .csv data file.</span></span>
    
<span data-ttu-id="c6eb0-109">Quando estiver pronto para começar a usar a análise de chamada por usuário, leia [Use per-user call analytics to](use-call-analytics-to-troubleshoot-poor-call-quality.md)troubleshoot poor call quality .</span><span class="sxs-lookup"><span data-stu-id="c6eb0-109">When you're ready to start using per-user call analytics, read [Use per-user call analytics to troubleshoot poor call quality](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span></span>
  
## <a name="give-permission-to-support-and-helpdesk-staff"></a><span data-ttu-id="c6eb0-110">Dar permissão para suporte e equipe de suporte técnico</span><span class="sxs-lookup"><span data-stu-id="c6eb0-110">Give permission to support and helpdesk staff</span></span>

<span data-ttu-id="c6eb0-111">Como administrador Teams, você tem acesso total a informações de análise de chamada para todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="c6eb0-111">As the Teams admin, you have full access to call analytics information for all users.</span></span> <span data-ttu-id="c6eb0-112">Criamos algumas funções de Azure Active Directory que você pode atribuir para dar suporte a funcionários e agentes de assistência técnica para que eles também possam acessar a análise de chamada por usuário (sem ter acesso ao restante do centro de administração do Teams).</span><span class="sxs-lookup"><span data-stu-id="c6eb0-112">We've created some specialized Azure Active Directory roles that you can assign to support staff and helpdesk agents so they can also access per-user call analytics (without having access to the rest of the Teams admin center).</span></span> <span data-ttu-id="c6eb0-113">Atribua a **Teams de** suporte de comunicações a usuários que devem ter uma visão limitada da análise de chamada por usuário (suporte à Camada 1).</span><span class="sxs-lookup"><span data-stu-id="c6eb0-113">Assign the **Teams communications support specialist** role to users who should have a limited view of per-user call analytics (Tier 1 support).</span></span> <span data-ttu-id="c6eb0-114">Atribua a **Teams de** engenheiro de suporte de comunicações aos usuários que precisam de acesso total à análise de chamada por usuário (suporte à Camada 2).</span><span class="sxs-lookup"><span data-stu-id="c6eb0-114">Assign the **Teams communications support engineer** role to users who need full access to per-user call analytics (Tier 2 support).</span></span> <span data-ttu-id="c6eb0-115">Nenhuma função tem acesso ao restante do Teams de administração.</span><span class="sxs-lookup"><span data-stu-id="c6eb0-115">Neither role has access to the rest of the Teams admin center.</span></span>

<span data-ttu-id="c6eb0-116">Para saber o que cada uma dessas funções faz, leia O que cada função Teams [suporte faz?](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do)</span><span class="sxs-lookup"><span data-stu-id="c6eb0-116">To learn what each of these roles does, read [What does each Teams Support role do](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do)?</span></span>

<span data-ttu-id="c6eb0-117">Para obter mais informações sobre Teams funções de administrador, consulte [Use Teams admin roles to manage Teams](using-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="c6eb0-117">For more information about Teams admin roles, see [Use Teams admin roles to manage Teams](using-admin-roles.md).</span></span> <span data-ttu-id="c6eb0-118">Para saber como atribuir funções de administrador Azure Active Directory, consulte [Exibir e atribuir funções em Azure Active Directory](/Azure/active-directory/users-groups-roles/directory-manage-roles-portal).</span><span class="sxs-lookup"><span data-stu-id="c6eb0-118">To learn how to assign admin roles in Azure Active Directory, see [View and assign roles in Azure Active Directory](/Azure/active-directory/users-groups-roles/directory-manage-roles-portal).</span></span>

<span data-ttu-id="c6eb0-119">Para saber como atribuir funções administrativas Azure Active Directory, consulte [Exibir e atribuir](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)funções em Azure Active Directory .</span><span class="sxs-lookup"><span data-stu-id="c6eb0-119">To learn how to assign administrative roles in Azure Active Directory, see [View and assign roles in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-manage-roles-portal).</span></span>

## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a><span data-ttu-id="c6eb0-120">Upload um arquivo .tsv ou .csv para adicionar informações de construção, site e locatário</span><span class="sxs-lookup"><span data-stu-id="c6eb0-120">Upload a .tsv or .csv file to add building, site, and tenant information</span></span>

<span data-ttu-id="c6eb0-121">Você pode adicionar informações de construção, site e locatário à análise de chamada por usuário carregando um arquivo .csv ou .tsv.</span><span class="sxs-lookup"><span data-stu-id="c6eb0-121">You can add building, site, and tenant information to per-user call analytics by uploading a .csv or .tsv file.</span></span> <span data-ttu-id="c6eb0-122">Com todas essas informações, a análise de chamada pode mapear endereços IP para locais físicos.</span><span class="sxs-lookup"><span data-stu-id="c6eb0-122">With all this information, call analytics can map IP addresses to physical locations.</span></span> <span data-ttu-id="c6eb0-123">Os administradores e agentes auxiliares podem usar essas informações para ajudar a detectar tendências em problemas de chamada.</span><span class="sxs-lookup"><span data-stu-id="c6eb0-123">Admins and helpdesk agents can use this information to help spot trends in call problems.</span></span> <span data-ttu-id="c6eb0-124">Por exemplo, por que os usuários no mesmo edifício têm problemas semelhantes de qualidade de chamada?</span><span class="sxs-lookup"><span data-stu-id="c6eb0-124">For example, why are users in the same building having similar call quality problems?</span></span> 

<span data-ttu-id="c6eb0-125">Se você for um administrador Teams ou Skype for Business, poderá usar um locatário existente e criar arquivo de dados a partir do Teams ou do CQD (Painel de Qualidade de Chamada Skype for Business de chamada).</span><span class="sxs-lookup"><span data-stu-id="c6eb0-125">If you're a Teams or Skype for Business admin, you can use an existing tenant and building data file from the Teams or Skype for Business Call Quality Dashboard (CQD).</span></span> <span data-ttu-id="c6eb0-126">Primeiro, você baixa o arquivo do CQD e o carrega para análise de chamada.</span><span class="sxs-lookup"><span data-stu-id="c6eb0-126">First, you download the file from CQD, then upload it to call analytics.</span></span> 

- <span data-ttu-id="c6eb0-127">Para baixar um arquivo de dados existente, vá **para** o centro de administração Microsoft Teams Painel de Qualidade de Chamada  >    >  **Upload agora**.</span><span class="sxs-lookup"><span data-stu-id="c6eb0-127">To download an existing data file, go to **Microsoft Teams admin center** > **Call Quality Dashboard** > **Upload now**.</span></span> <span data-ttu-id="c6eb0-128">Na lista **Meus carregamentos,** clique **em Baixar** ao lado do arquivo que você deseja.</span><span class="sxs-lookup"><span data-stu-id="c6eb0-128">In the **My uploads** list, click **Download** next to the file you want.</span></span> 

- <span data-ttu-id="c6eb0-129">Para carregar o novo arquivo, vá Microsoft Teams centro de administração Locais e selecione Upload de local  >  ou Substituir dados **de localização**. </span><span class="sxs-lookup"><span data-stu-id="c6eb0-129">To upload the new file, go to **Microsoft Teams admin center** > **Locations**, and then select **Upload location data** or **Replace location data**.</span></span>
  
<span data-ttu-id="c6eb0-130">Se você estiver criando o arquivo .tsv ou .csv do zero, [consulte Upload locatário e criar dados](CQD-upload-tenant-building-data.md).</span><span class="sxs-lookup"><span data-stu-id="c6eb0-130">If you're creating the .tsv or .csv file from scratch, see [Upload tenant and building data](CQD-upload-tenant-building-data.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="c6eb0-131">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="c6eb0-131">Related topics</span></span>

[<span data-ttu-id="c6eb0-132">Usar a análise de chamada por usuário para solucionar problemas de qualidade de chamada ruim</span><span class="sxs-lookup"><span data-stu-id="c6eb0-132">Use per-user call analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="c6eb0-133">Solução de problemas do Teams</span><span class="sxs-lookup"><span data-stu-id="c6eb0-133">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)