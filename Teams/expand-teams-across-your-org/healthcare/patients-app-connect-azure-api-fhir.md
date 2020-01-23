---
title: Conectar o aplicativo pacientes à API do Azure para FHIR
author: lanachin
ms.author: v-lanac
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
MS.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: Saiba como conectar o aplicativo pacientes no Microsoft Teams ao Azure API para FHIR (recursos de interoperabilidade rápida da assistência médica).
ms.openlocfilehash: e532aa9f9fbecb472db63a1ddad4cd71518a8041
ms.sourcegitcommit: d7fab927e96954f294f28dfb33c0889f736b3ab5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2020
ms.locfileid: "41259070"
---
# <a name="connect-the-patients-app-to-azure-api-for-fhir"></a><span data-ttu-id="3ec04-103">Conectar o aplicativo pacientes à API do Azure para FHIR</span><span class="sxs-lookup"><span data-stu-id="3ec04-103">Connect the Patients app to Azure API for FHIR</span></span>

<span data-ttu-id="3ec04-104">Siga estas etapas para permitir que o aplicativo pacientes no Microsoft Teams acesse uma API do Azure para a instância FHIR.</span><span class="sxs-lookup"><span data-stu-id="3ec04-104">Follow these steps to allow the Patients app in Microsoft Teams access to an Azure API for FHIR instance.</span></span> <span data-ttu-id="3ec04-105">Este artigo pressupõe que você tenha uma [API do Azure para a instância FHIR](https://azure.microsoft.com/services/azure-api-for-fhir/) configurada e configurada em seu locatário.</span><span class="sxs-lookup"><span data-stu-id="3ec04-105">This article assumes that you have an [Azure API for FHIR instance](https://azure.microsoft.com/services/azure-api-for-fhir/) set up and configured in your tenant.</span></span>  <span data-ttu-id="3ec04-106">Se você ainda não criou uma API do Azure para a instância do FHIR em seu locatário, consulte [início rápido: implantar a API do Azure para FHIR usando o portal do Azure](https://docs.microsoft.com/azure/healthcare-apis/fhir-paas-portal-quickstart).</span><span class="sxs-lookup"><span data-stu-id="3ec04-106">If you haven’t yet created an Azure API for FHIR instance in your tenant, see [Quickstart: Deploy Azure API for FHIR using Azure portal](https://docs.microsoft.com/azure/healthcare-apis/fhir-paas-portal-quickstart).</span></span>


1. <span data-ttu-id="3ec04-107">Clique [aqui](https://login.microsoftonline.com/common/adminConsent?client_id=4aee3506-b263-43e0-ba31-1468fa7b2806) para conceder consentimento de administrador para o aplicativo pacientes.</span><span class="sxs-lookup"><span data-stu-id="3ec04-107">Click [here](https://login.microsoftonline.com/common/adminConsent?client_id=4aee3506-b263-43e0-ba31-1468fa7b2806) to grant admin consent for the Patients app.</span></span> <span data-ttu-id="3ec04-108">Quando solicitado, entre usando o administrador de locatários ou as credenciais de administrador global e, em seguida, clique em **aceitar** para conceder as permissões necessárias.</span><span class="sxs-lookup"><span data-stu-id="3ec04-108">When prompted, sign in using your tenant admin or global admin credentials, and then click **Accept** to grant the required permissions.</span></span>

    ![Captura de tela de solicitação de permissão para o aplicativo pacientes](../../media/patients-app-permissions-request.png)

    <span data-ttu-id="3ec04-110">Depois de aceitar, feche a janela.</span><span class="sxs-lookup"><span data-stu-id="3ec04-110">After you accept, close the window.</span></span> <span data-ttu-id="3ec04-111">Você verá uma página que pode ter a seguinte aparência.</span><span class="sxs-lookup"><span data-stu-id="3ec04-111">You'll see a page that may look like this.</span></span> <span data-ttu-id="3ec04-112">Você pode ignorar a mensagem de erro na página.</span><span class="sxs-lookup"><span data-stu-id="3ec04-112">You can ignore the error message on the page.</span></span> <span data-ttu-id="3ec04-113">É inofensivo e indica que o consentimento é concedido.</span><span class="sxs-lookup"><span data-stu-id="3ec04-113">It's harmless and indicates that consent is granted.</span></span> <span data-ttu-id="3ec04-114">(Estamos trabalhando em uma página mais fácil de usar para esta URL.</span><span class="sxs-lookup"><span data-stu-id="3ec04-114">(We're working on a more user-friendly page for this URL.</span></span> <span data-ttu-id="3ec04-115">Fique atento!)</span><span class="sxs-lookup"><span data-stu-id="3ec04-115">Stay tuned!)</span></span>

    ![Captura de tela de solicitação de permissão para o aplicativo pacientes](../../media/patients-app-permissions-request-granted.png)
2. <span data-ttu-id="3ec04-117">Entre no [portal do Azure](https://portal.azure.com) com suas credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="3ec04-117">Sign in to the [Azure portal](https://portal.azure.com) with your admin credentials.</span></span>
3. <span data-ttu-id="3ec04-118">Na navegação à esquerda, selecione **Azure Active Directory**e, em seguida, selecione **aplicativos corporativos**.</span><span class="sxs-lookup"><span data-stu-id="3ec04-118">In the left navigation, select **Azure Active Directory**, and then select **Enterprise Applications**.</span></span>
    <span data-ttu-id="3ec04-119">Procure por uma linha chamada **pacientes (dev)** e, em seguida, copie o valor na coluna **ID do objeto** para a área de transferência.</span><span class="sxs-lookup"><span data-stu-id="3ec04-119">Look for a row named **Patients (dev)**, and then copy the value in the **Object ID** column to your clipboard.</span></span>
    <span data-ttu-id="3ec04-120">![Captura de tela da linha pacientes (dev) no portal do Azure](../../media/patients-app-azure-portal-object-id.png)</span><span class="sxs-lookup"><span data-stu-id="3ec04-120">![Screenshot of Patients (dev) row in Azure portal](../../media/patients-app-azure-portal-object-id.png)</span></span>
4. <span data-ttu-id="3ec04-121">Vá para a API do Azure para a instância de recursos do FHIR à qual você deseja conectar o aplicativo pacientes (ou procurando por ele ou navegando pelos recursos) e abra as configurações dessa instância.</span><span class="sxs-lookup"><span data-stu-id="3ec04-121">Go to the Azure API for FHIR resource instance to which you want to connect the Patients app (either by searching for it or by browsing through your resources), and then open the settings for that instance.</span></span>

    ![Captura de tela da API do Azure para configurações de instância do FHIR no portal do Azure](../../media/patients-app-azure-portal-instance-settings.png)

5. <span data-ttu-id="3ec04-123">Clique em **autenticação**e cole a ID do objeto que você copiou na etapa 3 para a caixa **IDs de objeto permitidos** .</span><span class="sxs-lookup"><span data-stu-id="3ec04-123">Click **Authentication**, and then paste the object ID that you copied in step 3 to the **Allowed object IDs** box.</span></span> <span data-ttu-id="3ec04-124">Isso permite que o aplicativo pacientes acesse o servidor FHIR.</span><span class="sxs-lookup"><span data-stu-id="3ec04-124">This allows the Patients app to access the FHIR server.</span></span> <span data-ttu-id="3ec04-125">Depois que você colar a identificação do objeto, o Azure Active Directory a validará, e uma marca de seleção verde aparecerá ao lado dela.</span><span class="sxs-lookup"><span data-stu-id="3ec04-125">After you paste the object ID, Azure Active Directory validates it, and a green check mark appears next to it.</span></span>

    ![Captura de tela das configurações de autenticação no portal do Azure](../../media/patients-app-azure-portal-authentication.png)

6. <span data-ttu-id="3ec04-127">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="3ec04-127">Click **Save**.</span></span> <span data-ttu-id="3ec04-128">Isso reimplanta a instância, o que pode levar alguns minutos.</span><span class="sxs-lookup"><span data-stu-id="3ec04-128">This redeploys the instance, which can take a few minutes.</span></span>
7. <span data-ttu-id="3ec04-129">Clique em **visão geral**e copie a URL do **ponto de extremidade de metadados FHIR**.</span><span class="sxs-lookup"><span data-stu-id="3ec04-129">Click **Overview**, and then copy the URL from **FHIR metadata endpoint**.</span></span> <span data-ttu-id="3ec04-130">Remova a marca Metadata para obter a URL do servidor do FHIR.</span><span class="sxs-lookup"><span data-stu-id="3ec04-130">Remove the metadata tag to get the FHIR server URL.</span></span> <span data-ttu-id="3ec04-131">Por exemplo, https://test02-teamshealth.azurehealthcareapis.com/.</span><span class="sxs-lookup"><span data-stu-id="3ec04-131">For example, https://test02-teamshealth.azurehealthcareapis.com/.</span></span> 

    ![Captura de tela do ponto de extremidade de metadados no portal do Azure](../../media/patients-app-azure-portal-metadata-endpoint.png)

8. <span data-ttu-id="3ec04-133">No Teams, vá para a instância do aplicativo pacientes que está carregada na sua equipe, clique em **configurações**e, na caixa **link** , digite a URL do ponto de extremidade do servidor FHIR.</span><span class="sxs-lookup"><span data-stu-id="3ec04-133">In Teams, go to the Patients app instance that's loaded in your team, click **Settings**, and then in the **Link** box, enter the FHIR server endpoint URL.</span></span> <span data-ttu-id="3ec04-134">Em seguida, clique em **conectar** para estabelecer uma conexão e pesquisar e adicionar pacientes à sua lista.</span><span class="sxs-lookup"><span data-stu-id="3ec04-134">Then, click **Connect** to establish a connection and search and add patients to your list.</span></span>  

    ![Captura de tela das configurações do aplicativo pacientes no Teams](../../media/patients-app-teams.png)
    
    <span data-ttu-id="3ec04-136">Se você receber um erro ao se conectar ao Microsoft Teams durante esta etapa, envie uma captura de tela detalhada do erro, logs do [Fiddler](https://www.telerik.com/download/fiddler) e de quaisquer outras etapas de reprodução em um email com uma linha de assunto "aplicativo pacientes – solução de problemas do modo EMR" para [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="3ec04-136">If you get an error when connecting to Teams during this step, send a detailed screenshot of the error, logs from [Fiddler](https://www.telerik.com/download/fiddler) and any other repro steps in an email with a subject line of “Patients App – EMR mode troubleshooting” to [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com).</span></span>

## <a name="related-topics"></a><span data-ttu-id="3ec04-137">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="3ec04-137">Related topics</span></span>

- [<span data-ttu-id="3ec04-138">Visão geral do aplicativo de pacientes</span><span class="sxs-lookup"><span data-stu-id="3ec04-138">Patients app overview</span></span>](patients-app-overview.md)
- [<span data-ttu-id="3ec04-139">Integração dos Registros Eletrônicos de Saúde no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3ec04-139">Integrating Electronic Healthcare Records into Microsoft Teams</span></span>](patients-app.md)
