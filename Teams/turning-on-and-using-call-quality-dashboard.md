---
title: Configurar o painel de qualidade da chamada (CQD)
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.teamsadmincenter.directrouting.cqd
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: Saiba mais sobre como ativar e usar o painel de qualidade de chamada e obter relatórios resumidos de qualidade das chamadas.
ms.openlocfilehash: 60363ed86e4e073b7ca5a752261ac806188900b1
ms.sourcegitcommit: ac73536f790f83a61eeb2eb8c6b71662f7bd26fc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2021
ms.locfileid: "50112841"
---
# <a name="set-up-call-quality-dashboard-cqd"></a><span data-ttu-id="a92bd-103">Configurar o painel de qualidade da chamada (CQD)</span><span class="sxs-lookup"><span data-stu-id="a92bd-103">Set up Call Quality Dashboard (CQD)</span></span>

<span data-ttu-id="a92bd-104">Abra o painel de qualidade da chamada da Microsoft (CQD) em [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) (entre com suas credenciais de administrador).</span><span class="sxs-lookup"><span data-stu-id="a92bd-104">Open the Microsoft Call Quality Dashboard (CQD) at [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) (sign in with your admin credentials).</span></span> <span data-ttu-id="a92bd-105">Ou acesse o centro de administração do Teams e selecione **painel de qualidade de chamada**.</span><span class="sxs-lookup"><span data-stu-id="a92bd-105">Or go to the Teams admin center and select **Call Quality Dashboard**.</span></span> 

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard3.png" alt-text="Captura de tela do botão painel de qualidade de chamada no centro de administração do teams":::

<span data-ttu-id="a92bd-107">Na página que é aberta, clique em **entrar** e digite sua conta de administrador global ou as informações da conta de administrador do Microsoft Teams Service.</span><span class="sxs-lookup"><span data-stu-id="a92bd-107">On the page that opens, click **Sign in** and enter your Global Administrator account or Microsoft Teams Service Administrator account information.</span></span> <span data-ttu-id="a92bd-108">Após a primeira vez que você se conectar, o CQD começará a coletar e processar dados.</span><span class="sxs-lookup"><span data-stu-id="a92bd-108">After the first time you sign in, CQD will begin collecting and processing data.</span></span> <span data-ttu-id="a92bd-109">Tenha em mente que pode levar uma ou mais horas para processar dados suficientes para exibir resultados significativos nos relatórios.</span><span class="sxs-lookup"><span data-stu-id="a92bd-109">Keep in mind that it may take one or more hours to process enough data to display meaningful results in the reports.</span></span>

<span data-ttu-id="a92bd-110">CQD mostra a qualidade da chamada e da reunião, em um nível da organização, para Microsoft Teams, Skype for Business Online e Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="a92bd-110">CQD shows call and meeting quality, at an org-wide level, for Microsoft Teams, Skype for Business Online, and Skype for Business Server 2019.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="a92bd-111">Para usar o CQD com o Skype for Business Server 2019, você terá que [Configurar o conector de dados de chamadas](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-call-data-connector).</span><span class="sxs-lookup"><span data-stu-id="a92bd-111">To use CQD with Skype for Business Server 2019, you'll have to [Configure Call Data Connector](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-call-data-connector).</span></span> <span data-ttu-id="a92bd-112">Consulte [planejar ligar para conector de dados](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-call-data-connector) antes de começar.</span><span class="sxs-lookup"><span data-stu-id="a92bd-112">See [Plan Call Data Connector](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-call-data-connector) before you start.</span></span>


## <a name="assign-admin-roles-for-access-to-cqd"></a><span data-ttu-id="a92bd-113">Atribuir funções de administrador para acessar o CQD</span><span class="sxs-lookup"><span data-stu-id="a92bd-113">Assign admin roles for access to CQD</span></span>

<span data-ttu-id="a92bd-114">Atribua [funções](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) para acessar o CQD para as pessoas que precisam usá-lo.</span><span class="sxs-lookup"><span data-stu-id="a92bd-114">Assign [roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) for accessing CQD to the people who need to use it.</span></span>

<span data-ttu-id="a92bd-115">Se quiser que usuários não administradores (como engenheiros de suporte e agentes de assistência técnica) usem o painel de qualidade de chamada, você pode atribuir a esses usuários uma das funções a seguir, que fornece acesso ao CQD.</span><span class="sxs-lookup"><span data-stu-id="a92bd-115">If you want non-admin users (such as support engineers and helpdesk agents) to use Call Quality Dashboard, you can assign those users one of the following roles, which gives access to CQD.</span></span> 


|  |<span data-ttu-id="a92bd-116">Exibir relatórios</span><span class="sxs-lookup"><span data-stu-id="a92bd-116">View reports</span></span>  |<span data-ttu-id="a92bd-117">Exibir campos EUII</span><span class="sxs-lookup"><span data-stu-id="a92bd-117">View EUII fields</span></span>  |<span data-ttu-id="a92bd-118">Criar relatórios</span><span class="sxs-lookup"><span data-stu-id="a92bd-118">Create reports</span></span>  |<span data-ttu-id="a92bd-119">Carregar dados de construção</span><span class="sxs-lookup"><span data-stu-id="a92bd-119">Upload building data</span></span>  |
|---------|:-------:|:-------:|:-------:|:-------:|
|<span data-ttu-id="a92bd-120">Administrador global</span><span class="sxs-lookup"><span data-stu-id="a92bd-120">Global Administrator</span></span>     |<span data-ttu-id="a92bd-121">Sim</span><span class="sxs-lookup"><span data-stu-id="a92bd-121">Yes</span></span>         |<span data-ttu-id="a92bd-122">Sim</span><span class="sxs-lookup"><span data-stu-id="a92bd-122">Yes</span></span>         |<span data-ttu-id="a92bd-123">Sim</span><span class="sxs-lookup"><span data-stu-id="a92bd-123">Yes</span></span>         |<span data-ttu-id="a92bd-124">Sim</span><span class="sxs-lookup"><span data-stu-id="a92bd-124">Yes</span></span>         |
|<span data-ttu-id="a92bd-125">Administrador de Serviço do Teams</span><span class="sxs-lookup"><span data-stu-id="a92bd-125">Teams Service Administrator</span></span>     |<span data-ttu-id="a92bd-126">Sim</span><span class="sxs-lookup"><span data-stu-id="a92bd-126">Yes</span></span>         |<span data-ttu-id="a92bd-127">Sim</span><span class="sxs-lookup"><span data-stu-id="a92bd-127">Yes</span></span>         |<span data-ttu-id="a92bd-128">Sim</span><span class="sxs-lookup"><span data-stu-id="a92bd-128">Yes</span></span>         |<span data-ttu-id="a92bd-129">Sim</span><span class="sxs-lookup"><span data-stu-id="a92bd-129">Yes</span></span>         |
|<span data-ttu-id="a92bd-130">Administrador de Comunicações de Equipes</span><span class="sxs-lookup"><span data-stu-id="a92bd-130">Teams Communications Administrator</span></span>     |<span data-ttu-id="a92bd-131">Sim</span><span class="sxs-lookup"><span data-stu-id="a92bd-131">Yes</span></span>         |<span data-ttu-id="a92bd-132">Sim</span><span class="sxs-lookup"><span data-stu-id="a92bd-132">Yes</span></span>         |<span data-ttu-id="a92bd-133">Sim</span><span class="sxs-lookup"><span data-stu-id="a92bd-133">Yes</span></span>         |<span data-ttu-id="a92bd-134">Sim</span><span class="sxs-lookup"><span data-stu-id="a92bd-134">Yes</span></span>         |
|<span data-ttu-id="a92bd-135">Engenheiro de Suporte de Comunicações de Equipes</span><span class="sxs-lookup"><span data-stu-id="a92bd-135">Teams Communications Support Engineer</span></span>     |<span data-ttu-id="a92bd-136">Sim</span><span class="sxs-lookup"><span data-stu-id="a92bd-136">Yes</span></span>         |<span data-ttu-id="a92bd-137">Sim</span><span class="sxs-lookup"><span data-stu-id="a92bd-137">Yes</span></span>         |<span data-ttu-id="a92bd-138">Sim</span><span class="sxs-lookup"><span data-stu-id="a92bd-138">Yes</span></span>         |<span data-ttu-id="a92bd-139">Não</span><span class="sxs-lookup"><span data-stu-id="a92bd-139">No</span></span>         |
|<span data-ttu-id="a92bd-140">Especialista em suporte do teams Communications</span><span class="sxs-lookup"><span data-stu-id="a92bd-140">Teams Communications Support Specialist</span></span>     |<span data-ttu-id="a92bd-141">Sim</span><span class="sxs-lookup"><span data-stu-id="a92bd-141">Yes</span></span>         |<span data-ttu-id="a92bd-142">Não</span><span class="sxs-lookup"><span data-stu-id="a92bd-142">No</span></span>         |<span data-ttu-id="a92bd-143">Sim</span><span class="sxs-lookup"><span data-stu-id="a92bd-143">Yes</span></span>         |<span data-ttu-id="a92bd-144">Não</span><span class="sxs-lookup"><span data-stu-id="a92bd-144">No</span></span>         |
|<span data-ttu-id="a92bd-145">Administrador do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="a92bd-145">Skype for Business Administrator</span></span>     |<span data-ttu-id="a92bd-146">Sim</span><span class="sxs-lookup"><span data-stu-id="a92bd-146">Yes</span></span>         |<span data-ttu-id="a92bd-147">Sim</span><span class="sxs-lookup"><span data-stu-id="a92bd-147">Yes</span></span>         |<span data-ttu-id="a92bd-148">Sim</span><span class="sxs-lookup"><span data-stu-id="a92bd-148">Yes</span></span>         |<span data-ttu-id="a92bd-149">Sim</span><span class="sxs-lookup"><span data-stu-id="a92bd-149">Yes</span></span>         |
|<span data-ttu-id="a92bd-150">Leitor global</span><span class="sxs-lookup"><span data-stu-id="a92bd-150">Global Reader</span></span> |<span data-ttu-id="a92bd-151">Sim</span><span class="sxs-lookup"><span data-stu-id="a92bd-151">Yes</span></span>         |<span data-ttu-id="a92bd-152">Sim</span><span class="sxs-lookup"><span data-stu-id="a92bd-152">Yes</span></span>         |<span data-ttu-id="a92bd-153">Sim</span><span class="sxs-lookup"><span data-stu-id="a92bd-153">Yes</span></span>         |<span data-ttu-id="a92bd-154">Não</span><span class="sxs-lookup"><span data-stu-id="a92bd-154">No</span></span>         |
|<span data-ttu-id="a92bd-155">Leitor de relatórios<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="a92bd-155">Reports Reader<sup>1</sup></span></span>     |<span data-ttu-id="a92bd-156">Sim</span><span class="sxs-lookup"><span data-stu-id="a92bd-156">Yes</span></span>         |<span data-ttu-id="a92bd-157">Não</span><span class="sxs-lookup"><span data-stu-id="a92bd-157">No</span></span>         |<span data-ttu-id="a92bd-158">Sim</span><span class="sxs-lookup"><span data-stu-id="a92bd-158">Yes</span></span>         |<span data-ttu-id="a92bd-159">Não</span><span class="sxs-lookup"><span data-stu-id="a92bd-159">No</span></span>         |

<span data-ttu-id="a92bd-160"><sup>1</sup> além de ler relatórios do CQD, o leitor de relatórios pode exibir todos os [relatórios de atividades](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) no centro de administração e todos os relatórios do pacote de conteúdo de adoção do [365](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f).</span><span class="sxs-lookup"><span data-stu-id="a92bd-160"><sup>1</sup> In addition to reading CQD reports, the Reports Reader can view all the [activity reports](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) in the admin center and any reports from the [Microsoft 365 Adoption content pack](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f).</span></span>

> [!NOTE]
> <span data-ttu-id="a92bd-161">Se você não estiver vendo [EUII (informações identificáveis pelo usuário final)](CQD-data-and-reports.md#euii-data) e tiver uma das funções que tem permissão para ver essas informações, lembre-se de que CQD só mantém EUII por 28 dias.</span><span class="sxs-lookup"><span data-stu-id="a92bd-161">If you're not seeing [EUII (end-user identifiable information)](CQD-data-and-reports.md#euii-data) and you have one of the roles that's permitted to see this information, keep in mind that CQD only keeps EUII for 28 days.</span></span> <span data-ttu-id="a92bd-162">Qualquer item mais antigo que 28 dias é excluído.</span><span class="sxs-lookup"><span data-stu-id="a92bd-162">Anything older than 28 days is deleted.</span></span>

<span data-ttu-id="a92bd-163">Para obter mais informações sobre essas funções, consulte [sobre as funções de administrador do Office 365](/office365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="a92bd-163">For more information about these roles, see [About Office 365 admin roles](/office365/admin/add-users/about-admin-roles).</span></span>


<span data-ttu-id="a92bd-164">Após a primeira vez que você se conectar, o CQD começará a coletar e processar dados.</span><span class="sxs-lookup"><span data-stu-id="a92bd-164">After the first time you sign in, CQD will begin collecting and processing data.</span></span> <span data-ttu-id="a92bd-165">A partir de dezembro de 2019, você ainda pode acessar a versão mais antiga do CQD (cqd.lync.com), embora o portal herdado forneça um link para o CQD mais recente (cqd.teams.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="a92bd-165">As of December 2019, you can still access the older version of CQD (cqd.lync.com), although the legacy portal gives you a link to the latest CQD (cqd.teams.microsoft.com).</span></span> <span data-ttu-id="a92bd-166">Por fim, a versão mais antiga do CQD será descomissionada.</span><span class="sxs-lookup"><span data-stu-id="a92bd-166">Eventually, the older version of CQD will be decommissioned.</span></span> <span data-ttu-id="a92bd-167">A partir de 1 ° de julho de 2020, a versão mais antiga do CQD acessa os dados do CQD mais recente.</span><span class="sxs-lookup"><span data-stu-id="a92bd-167">As of July 1, 2020, the older version of CQD accesses data from the latest CQD.</span></span>


## <a name="migrate-building-data-and-reports-from-previous-version-of-cqd"></a><span data-ttu-id="a92bd-168">Migrar dados e relatórios de construção de uma versão anterior do CQD</span><span class="sxs-lookup"><span data-stu-id="a92bd-168">Migrate building data and reports from previous version of CQD</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a92bd-169">A partir de 1 ° de julho de 2020, você não pode mais migrar dados de construção e relatórios do antigo CQD ( https://CQD.lync.com) .</span><span class="sxs-lookup"><span data-stu-id="a92bd-169">As of July 1, 2020, you can no longer migrate building data and reports from the old CQD (https://CQD.lync.com).</span></span> 



## <a name="use-power-bi-to-analyze-cqd-data"></a><span data-ttu-id="a92bd-170">Usar o Power BI para analisar dados do CQD</span><span class="sxs-lookup"><span data-stu-id="a92bd-170">Use Power BI to analyze CQD data</span></span>

<span data-ttu-id="a92bd-171">Novidades em janeiro de 2020: [Baixe os modelos de consulta do Power bi para CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="a92bd-171">New in January 2020: [Download Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> <span data-ttu-id="a92bd-172">Modelos personalizáveis do Power BI que você pode usar para analisar e relatar seus dados do CQD.</span><span class="sxs-lookup"><span data-stu-id="a92bd-172">Customizable Power BI templates you can use to analyze and report your CQD data.</span></span>

<span data-ttu-id="a92bd-173">Leia [use o Power bi para analisar dados do CQD](CQD-Power-BI-query-templates.md) para saber mais.</span><span class="sxs-lookup"><span data-stu-id="a92bd-173">Read [Use Power BI to analyze CQD data](CQD-Power-BI-query-templates.md) to learn more.</span></span>


## <a name="related-topics"></a><span data-ttu-id="a92bd-174">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="a92bd-174">Related topics</span></span>

[<span data-ttu-id="a92bd-175">Melhorar e monitorar a qualidade da chamada para equipes</span><span class="sxs-lookup"><span data-stu-id="a92bd-175">Improve and monitor call quality for Teams</span></span>](monitor-call-quality-qos.md)

[<span data-ttu-id="a92bd-176">O que é CQD?</span><span class="sxs-lookup"><span data-stu-id="a92bd-176">What is CQD?</span></span>](CQD-what-is-call-quality-dashboard.md)

[<span data-ttu-id="a92bd-177">Carregar dados do locatário e construção</span><span class="sxs-lookup"><span data-stu-id="a92bd-177">Upload tenant and building data</span></span>](CQD-upload-tenant-building-data.md)

[<span data-ttu-id="a92bd-178">Dados e relatórios do CQD</span><span class="sxs-lookup"><span data-stu-id="a92bd-178">CQD data and reports</span></span>](CQD-data-and-reports.md)

[<span data-ttu-id="a92bd-179">Usar o CQD para gerenciar a qualidade da chamada e da reunião</span><span class="sxs-lookup"><span data-stu-id="a92bd-179">Use CQD to manage call and meeting quality</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="a92bd-180">Dimensões e medidas disponíveis no CQD</span><span class="sxs-lookup"><span data-stu-id="a92bd-180">Dimensions and measures available in CQD</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="a92bd-181">Classificação de fluxo no CQD</span><span class="sxs-lookup"><span data-stu-id="a92bd-181">Stream Classification in CQD</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="a92bd-182">Usar o Power BI para analisar dados do CQD</span><span class="sxs-lookup"><span data-stu-id="a92bd-182">Use Power BI to analyze CQD data</span></span>](CQD-Power-BI-query-templates.md)
