---
title: Conecte o aplicativo de pacientes à API do Azure para FHIR
author: lanachin
ms.author: v-lanac
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: Saiba como conectar o aplicativo pacientes no Microsoft Teams ao Azure API para FHIR (recursos de interoperabilidade rápida da assistência médica).
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: e3ff2f42953d59d1eecbc96179759f2ad9024f82
ms.sourcegitcommit: 18b5e3487ba1350c5d2e6d676a4ab582b5b638d4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "48772252"
---
# <a name="connect-the-patients-app-to-azure-api-for-fhir"></a><span data-ttu-id="db814-103">Conecte o aplicativo de pacientes à API do Azure para FHIR</span><span class="sxs-lookup"><span data-stu-id="db814-103">Connect the Patients app to Azure API for FHIR</span></span>

> [!NOTE]
> <span data-ttu-id="db814-104">A partir de 30 de outubro de 2020, o aplicativo pacientes foi desativado e substituído pelo [aplicativo listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) no Teams.</span><span class="sxs-lookup"><span data-stu-id="db814-104">Effective October 30, 2020, the Patients app has been retired and replaced by the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span></span> <span data-ttu-id="db814-105">Com listas, equipes de cuidado em sua organização de assistência médica podem criar listas de pacientes para cenários que vão desde rodadas e reuniões interdisciplinares de equipe até o monitoramento geral do paciente.</span><span class="sxs-lookup"><span data-stu-id="db814-105">With Lists, care teams in your healthcare organization can create patient lists for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span> <span data-ttu-id="db814-106">Confira o modelo pacientes em listas para começar.</span><span class="sxs-lookup"><span data-stu-id="db814-106">Check out the Patients template in Lists to get started.</span></span> <span data-ttu-id="db814-107">Para saber mais sobre como gerenciar o aplicativo listas em sua organização, consulte [gerenciar o aplicativo listas](../../manage-lists-app.md)</span><span class="sxs-lookup"><span data-stu-id="db814-107">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md)</span></span>

<span data-ttu-id="db814-108">Siga estas etapas para permitir que o aplicativo pacientes no Microsoft Teams acesse uma API do Azure para a instância FHIR.</span><span class="sxs-lookup"><span data-stu-id="db814-108">Follow these steps to allow the Patients app in Microsoft Teams access to an Azure API for FHIR instance.</span></span> <span data-ttu-id="db814-109">Este artigo pressupõe que você tenha uma [API do Azure para a instância FHIR](https://azure.microsoft.com/services/azure-api-for-fhir/) configurada e configurada em seu locatário.</span><span class="sxs-lookup"><span data-stu-id="db814-109">This article assumes that you have an [Azure API for FHIR instance](https://azure.microsoft.com/services/azure-api-for-fhir/) set up and configured in your tenant.</span></span>  <span data-ttu-id="db814-110">Se você ainda não criou uma API do Azure para a instância do FHIR em seu locatário, consulte [início rápido: implantar a API do Azure para FHIR usando o portal do Azure](https://docs.microsoft.com/azure/healthcare-apis/fhir-paas-portal-quickstart).</span><span class="sxs-lookup"><span data-stu-id="db814-110">If you haven’t yet created an Azure API for FHIR instance in your tenant, see [Quickstart: Deploy Azure API for FHIR using Azure portal](https://docs.microsoft.com/azure/healthcare-apis/fhir-paas-portal-quickstart).</span></span>


1. <span data-ttu-id="db814-111">Clique [aqui](https://login.microsoftonline.com/common/adminConsent?client_id=4aee3506-b263-43e0-ba31-1468fa7b2806) para conceder consentimento de administrador para o aplicativo pacientes.</span><span class="sxs-lookup"><span data-stu-id="db814-111">Click [here](https://login.microsoftonline.com/common/adminConsent?client_id=4aee3506-b263-43e0-ba31-1468fa7b2806) to grant admin consent for the Patients app.</span></span> <span data-ttu-id="db814-112">Quando solicitado, entre usando o administrador de locatários ou as credenciais de administrador global e, em seguida, clique em **aceitar** para conceder as permissões necessárias.</span><span class="sxs-lookup"><span data-stu-id="db814-112">When prompted, sign in using your tenant admin or global admin credentials, and then click **Accept** to grant the required permissions.</span></span>

    ![Captura de tela de solicitação de permissão para o aplicativo pacientes](../../media/patients-app-permissions-request.png)

    <span data-ttu-id="db814-114">Depois de aceitar, feche a janela.</span><span class="sxs-lookup"><span data-stu-id="db814-114">After you accept, close the window.</span></span> <span data-ttu-id="db814-115">Você verá uma página que pode ter a seguinte aparência.</span><span class="sxs-lookup"><span data-stu-id="db814-115">You'll see a page that may look like this.</span></span> <span data-ttu-id="db814-116">Você pode ignorar a mensagem de erro na página.</span><span class="sxs-lookup"><span data-stu-id="db814-116">You can ignore the error message on the page.</span></span> <span data-ttu-id="db814-117">É inofensivo e indica que o consentimento é concedido.</span><span class="sxs-lookup"><span data-stu-id="db814-117">It's harmless and indicates that consent is granted.</span></span> <span data-ttu-id="db814-118">(Estamos trabalhando em uma página mais fácil de usar para esta URL.</span><span class="sxs-lookup"><span data-stu-id="db814-118">(We're working on a more user-friendly page for this URL.</span></span> <span data-ttu-id="db814-119">Fique atento!)</span><span class="sxs-lookup"><span data-stu-id="db814-119">Stay tuned!)</span></span>

    ![Captura de tela de solicitação de permissão para o aplicativo pacientes](../../media/patients-app-permissions-request-granted.png)
    
2. <span data-ttu-id="db814-121">Entre no [portal do Azure](https://portal.azure.com) com suas credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="db814-121">Sign in to the [Azure portal](https://portal.azure.com) with your admin credentials.</span></span>

3. <span data-ttu-id="db814-122">Na navegação à esquerda, selecione **Azure Active Directory** e, em seguida, selecione **aplicativos corporativos** .</span><span class="sxs-lookup"><span data-stu-id="db814-122">In the left navigation, select **Azure Active Directory** , and then select **Enterprise Applications** .</span></span>

    <span data-ttu-id="db814-123">Procure por uma linha chamada **pacientes (dev)** e, em seguida, copie o valor na coluna **ID do objeto** para a área de transferência.</span><span class="sxs-lookup"><span data-stu-id="db814-123">Look for a row named **Patients (dev)** , and then copy the value in the **Object ID** column to your clipboard.</span></span>
    
    ![Captura de tela da linha pacientes (dev) no portal do Azure](../../media/patients-app-azure-portal-object-id.png)
    
4. <span data-ttu-id="db814-125">Vá para a API do Azure para a instância de recursos do FHIR à qual você deseja conectar o aplicativo pacientes (ou procurando por ele ou navegando pelos recursos) e abra as configurações dessa instância.</span><span class="sxs-lookup"><span data-stu-id="db814-125">Go to the Azure API for FHIR resource instance to which you want to connect the Patients app (either by searching for it or by browsing through your resources), and then open the settings for that instance.</span></span>

    ![Captura de tela da API do Azure para configurações de instância do FHIR no portal do Azure](../../media/patients-app-azure-portal-instance-settings.png)

5. <span data-ttu-id="db814-127">Clique em **autenticação** e cole a ID do objeto que você copiou na etapa 3 para a caixa **IDs de objeto permitidos** .</span><span class="sxs-lookup"><span data-stu-id="db814-127">Click **Authentication** , and then paste the object ID that you copied in step 3 to the **Allowed object IDs** box.</span></span> <span data-ttu-id="db814-128">Isso permite que o aplicativo pacientes acesse o servidor FHIR.</span><span class="sxs-lookup"><span data-stu-id="db814-128">This allows the Patients app to access the FHIR server.</span></span> <span data-ttu-id="db814-129">Depois que você colar a identificação do objeto, o Azure Active Directory a validará, e uma marca de seleção verde aparecerá ao lado dela.</span><span class="sxs-lookup"><span data-stu-id="db814-129">After you paste the object ID, Azure Active Directory validates it, and a green check mark appears next to it.</span></span>

    ![Captura de tela das configurações de autenticação no portal do Azure](../../media/patients-app-azure-portal-authentication.png)

6. <span data-ttu-id="db814-131">Clique em **Salvar** .</span><span class="sxs-lookup"><span data-stu-id="db814-131">Click **Save** .</span></span> <span data-ttu-id="db814-132">Isso reimplanta a instância, o que pode levar alguns minutos.</span><span class="sxs-lookup"><span data-stu-id="db814-132">This redeploys the instance, which can take a few minutes.</span></span>

7. <span data-ttu-id="db814-133">Clique em **visão geral** e copie a URL do **ponto de extremidade de metadados FHIR** .</span><span class="sxs-lookup"><span data-stu-id="db814-133">Click **Overview** , and then copy the URL from **FHIR metadata endpoint** .</span></span> <span data-ttu-id="db814-134">Remova a marca Metadata para obter a URL do servidor do FHIR.</span><span class="sxs-lookup"><span data-stu-id="db814-134">Remove the metadata tag to get the FHIR server URL.</span></span> <span data-ttu-id="db814-135">Por exemplo, https://test02-teamshealth.azurehealthcareapis.com/ .</span><span class="sxs-lookup"><span data-stu-id="db814-135">For example, https://test02-teamshealth.azurehealthcareapis.com/.</span></span> 

    ![Captura de tela do ponto de extremidade de metadados no portal do Azure](../../media/patients-app-azure-portal-metadata-endpoint.png)

8. <span data-ttu-id="db814-137">No Teams, vá para a instância do aplicativo pacientes que está carregada na sua equipe, clique em **configurações** e, na caixa **link** , digite a URL do ponto de extremidade do servidor FHIR.</span><span class="sxs-lookup"><span data-stu-id="db814-137">In Teams, go to the Patients app instance that's loaded in your team, click **Settings** , and then in the **Link** box, enter the FHIR server endpoint URL.</span></span> <span data-ttu-id="db814-138">Em seguida, clique em **conectar** para estabelecer uma conexão e pesquisar e adicionar pacientes à sua lista.</span><span class="sxs-lookup"><span data-stu-id="db814-138">Then, click **Connect** to establish a connection and search and add patients to your list.</span></span>  

    ![Captura de tela das configurações do aplicativo pacientes no Teams](../../media/patients-app-teams.png)
    
    <span data-ttu-id="db814-140">Se você receber um erro ao se conectar ao Microsoft Teams durante esta etapa, envie uma captura de tela detalhada do erro, logs do [Fiddler](https://www.telerik.com/download/fiddler) e de quaisquer outras etapas de reprodução em um email com uma linha de assunto "aplicativo pacientes – solução de problemas do modo EMR" para [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="db814-140">If you get an error when connecting to Teams during this step, send a detailed screenshot of the error, logs from [Fiddler](https://www.telerik.com/download/fiddler) and any other repro steps in an email with a subject line of “Patients App – EMR mode troubleshooting” to [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com).</span></span>

## <a name="related-topics"></a><span data-ttu-id="db814-141">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="db814-141">Related topics</span></span>

- [<span data-ttu-id="db814-142">Visão geral do aplicativo de pacientes</span><span class="sxs-lookup"><span data-stu-id="db814-142">Patients app overview</span></span>](patients-app-overview.md)
- [<span data-ttu-id="db814-143">Integração dos Registros Eletrônicos de Saúde no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="db814-143">Integrating Electronic Healthcare Records into Microsoft Teams</span></span>](patients-app.md)
