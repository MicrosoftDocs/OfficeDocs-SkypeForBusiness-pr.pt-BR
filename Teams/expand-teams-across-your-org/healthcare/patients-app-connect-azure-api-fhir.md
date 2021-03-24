---
title: Conecte o aplicativo de pacientes à API do Azure para FHIR
author: cichur
ms.author: v-cichur
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
description: Saiba como conectar o aplicativo Pacientes no Microsoft Teams à API do Azure para FHIR (Recursos de Interoperabilidade de Saúde Rápida).
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: e06e422765c1d1d633414d24dff48e2801067f15
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096263"
---
# <a name="connect-the-patients-app-to-azure-api-for-fhir"></a><span data-ttu-id="950b9-103">Conecte o aplicativo de pacientes à API do Azure para FHIR</span><span class="sxs-lookup"><span data-stu-id="950b9-103">Connect the Patients app to Azure API for FHIR</span></span>

> [!NOTE]
> <span data-ttu-id="950b9-104">A partir de 30 de outubro de 2020, o aplicativo Pacientes será retirado e substituído pelo [aplicativo de Listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) no Teams.</span><span class="sxs-lookup"><span data-stu-id="950b9-104">Effective October 30, 2020, the Patients app has been retired and replaced by the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span></span> <span data-ttu-id="950b9-105">Os dados do aplicativo Pacientes são armazenados na caixa de correio do grupo do Office 365 que apoia a equipe.</span><span class="sxs-lookup"><span data-stu-id="950b9-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="950b9-106">Todos os dados associados ao aplicativo Pacientes são mantidos neste grupo, mas não podem mais ser acessados por meio da interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="950b9-106">All data associated with the Patients app is retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="950b9-107">Os usuários podem criar suas listas usando o [aplicativo Listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span><span class="sxs-lookup"><span data-stu-id="950b9-107">Users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="950b9-108">Com o Lists, as equipes de atendimento em sua organização de saúde podem criar listas de pacientes para cenários que variam desde reuniões gerais com a equipe de atendimento até o monitoramento geral dos pacientes.</span><span class="sxs-lookup"><span data-stu-id="950b9-108">With Lists, care teams in your healthcare organization can create patient lists for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span> <span data-ttu-id="950b9-109">Confira o modelo Pacientes no Lists para começar.</span><span class="sxs-lookup"><span data-stu-id="950b9-109">Check out the Patients template in Lists to get started.</span></span> <span data-ttu-id="950b9-110">Para saber mais sobre como gerenciar o aplicativo Lists em sua organização, consulte [Gerenciar o aplicativo Lists](../../manage-lists-app.md).</span><span class="sxs-lookup"><span data-stu-id="950b9-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

<span data-ttu-id="950b9-111">Siga estas etapas para permitir que o aplicativo Patients no Microsoft Teams acesse uma API do Azure para instância FHIR.</span><span class="sxs-lookup"><span data-stu-id="950b9-111">Follow these steps to allow the Patients app in Microsoft Teams access to an Azure API for FHIR instance.</span></span> <span data-ttu-id="950b9-112">Este artigo supõe que você tenha uma [API do Azure para instância FHIR](https://azure.microsoft.com/services/azure-api-for-fhir/) configurada e configurada em seu locatário.</span><span class="sxs-lookup"><span data-stu-id="950b9-112">This article assumes that you have an [Azure API for FHIR instance](https://azure.microsoft.com/services/azure-api-for-fhir/) set up and configured in your tenant.</span></span>  <span data-ttu-id="950b9-113">Se você ainda não criou uma API do Azure para instância FHIR em seu locatário, consulte Início rápido: Implantar a [API do Azure para FHIR](/azure/healthcare-apis/fhir-paas-portal-quickstart)usando o portal do Azure .</span><span class="sxs-lookup"><span data-stu-id="950b9-113">If you haven’t yet created an Azure API for FHIR instance in your tenant, see [Quickstart: Deploy Azure API for FHIR using Azure portal](/azure/healthcare-apis/fhir-paas-portal-quickstart).</span></span>

1. <span data-ttu-id="950b9-114">Clique [aqui para](https://login.microsoftonline.com/common/adminConsent?client_id=4aee3506-b263-43e0-ba31-1468fa7b2806) conceder o consentimento do administrador para o aplicativo Pacientes.</span><span class="sxs-lookup"><span data-stu-id="950b9-114">Click [here](https://login.microsoftonline.com/common/adminConsent?client_id=4aee3506-b263-43e0-ba31-1468fa7b2806) to grant admin consent for the Patients app.</span></span> <span data-ttu-id="950b9-115">Quando solicitado, entre usando suas credenciais de administrador de locatário ou administrador global e clique em **Aceitar** para conceder as permissões necessárias.</span><span class="sxs-lookup"><span data-stu-id="950b9-115">When prompted, sign in using your tenant admin or global admin credentials, and then click **Accept** to grant the required permissions.</span></span>

    ![Captura de tela da solicitação de permissão para o Aplicativo de Pacientes](../../media/patients-app-permissions-request.png)

    <span data-ttu-id="950b9-117">Depois de aceitar, feche a janela.</span><span class="sxs-lookup"><span data-stu-id="950b9-117">After you accept, close the window.</span></span> <span data-ttu-id="950b9-118">Você verá uma página que pode ter esta aparência.</span><span class="sxs-lookup"><span data-stu-id="950b9-118">You'll see a page that may look like this.</span></span> <span data-ttu-id="950b9-119">Você pode ignorar a mensagem de erro na página.</span><span class="sxs-lookup"><span data-stu-id="950b9-119">You can ignore the error message on the page.</span></span> <span data-ttu-id="950b9-120">É inofensivo e indica que o consentimento é concedido.</span><span class="sxs-lookup"><span data-stu-id="950b9-120">It's harmless and indicates that consent is granted.</span></span> <span data-ttu-id="950b9-121">(Estamos trabalhando em uma página mais fácil de usar para essa URL.</span><span class="sxs-lookup"><span data-stu-id="950b9-121">(We're working on a more user-friendly page for this URL.</span></span> <span data-ttu-id="950b9-122">Fique atento!)</span><span class="sxs-lookup"><span data-stu-id="950b9-122">Stay tuned!)</span></span>

    ![Captura de tela da solicitação de permissão para o Aplicativo de Pacientes](../../media/patients-app-permissions-request-granted.png)

2. <span data-ttu-id="950b9-124">Entre no [portal do Azure](https://portal.azure.com) com suas credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="950b9-124">Sign in to the [Azure portal](https://portal.azure.com) with your admin credentials.</span></span>

3. <span data-ttu-id="950b9-125">Na navegação à esquerda, selecione **Azure Active Directory** e, em seguida, selecione **Aplicativos Empresariais**.</span><span class="sxs-lookup"><span data-stu-id="950b9-125">In the left navigation, select **Azure Active Directory**, and then select **Enterprise Applications**.</span></span>

    <span data-ttu-id="950b9-126">Procure uma linha chamada **Patients (dev)** e copie o valor na coluna **ID** do objeto para sua área de transferência.</span><span class="sxs-lookup"><span data-stu-id="950b9-126">Look for a row named **Patients (dev)**, and then copy the value in the **Object ID** column to your clipboard.</span></span>

    ![Captura de tela da linha Pacientes (dev) no portal do Azure](../../media/patients-app-azure-portal-object-id.png)

4. <span data-ttu-id="950b9-128">Vá para a instância de recurso da API do Azure para FHIR à qual você deseja conectar o aplicativo Patients (pesquisando por ele ou navegando por seus recursos) e abra as configurações dessa instância.</span><span class="sxs-lookup"><span data-stu-id="950b9-128">Go to the Azure API for FHIR resource instance to which you want to connect the Patients app (either by searching for it or by browsing through your resources), and then open the settings for that instance.</span></span>

    ![Captura de tela da API do Azure para configurações de instância FHIR no portal do Azure](../../media/patients-app-azure-portal-instance-settings.png)

5. <span data-ttu-id="950b9-130">Clique **em Autenticação** e, em seguida, colar a ID do objeto que você copiou na etapa 3 para a caixa **IDs** de objeto Permitido.</span><span class="sxs-lookup"><span data-stu-id="950b9-130">Click **Authentication**, and then paste the object ID that you copied in step 3 to the **Allowed object IDs** box.</span></span> <span data-ttu-id="950b9-131">Isso permite que o aplicativo Patients acesse o servidor FHIR.</span><span class="sxs-lookup"><span data-stu-id="950b9-131">This allows the Patients app to access the FHIR server.</span></span> <span data-ttu-id="950b9-132">Depois de colar a ID do objeto, o Azure Active Directory a valida e uma marca de seleção verde aparece ao lado dele.</span><span class="sxs-lookup"><span data-stu-id="950b9-132">After you paste the object ID, Azure Active Directory validates it, and a green check mark appears next to it.</span></span>

    ![Captura de tela das configurações de autenticação no portal do Azure](../../media/patients-app-azure-portal-authentication.png)

6. <span data-ttu-id="950b9-134">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="950b9-134">Click **Save**.</span></span> <span data-ttu-id="950b9-135">Isso reimplanta a instância, que pode levar alguns minutos.</span><span class="sxs-lookup"><span data-stu-id="950b9-135">This redeploys the instance, which can take a few minutes.</span></span>

7. <span data-ttu-id="950b9-136">Clique **em Visão** Geral e copie a URL do ponto de extremidade de **metadados FHIR.**</span><span class="sxs-lookup"><span data-stu-id="950b9-136">Click **Overview**, and then copy the URL from **FHIR metadata endpoint**.</span></span> <span data-ttu-id="950b9-137">Remova a marca de metadados para obter a URL do servidor FHIR.</span><span class="sxs-lookup"><span data-stu-id="950b9-137">Remove the metadata tag to get the FHIR server URL.</span></span> <span data-ttu-id="950b9-138">Por exemplo, `https://test02-teamshealth.azurehealthcareapis.com/` .</span><span class="sxs-lookup"><span data-stu-id="950b9-138">For example, `https://test02-teamshealth.azurehealthcareapis.com/`.</span></span>

    ![o ponto de extremidade de metadados no portal do Azure](../../media/patients-app-azure-portal-metadata-endpoint.png)

8. <span data-ttu-id="950b9-140">No Teams, vá para a instância do aplicativo Pacientes carregada em sua equipe, clique em Configurações **e,** na caixa **Link,** insira a URL do ponto de extremidade do servidor FHIR.</span><span class="sxs-lookup"><span data-stu-id="950b9-140">In Teams, go to the Patients app instance that's loaded in your team, click **Settings**, and then in the **Link** box, enter the FHIR server endpoint URL.</span></span> <span data-ttu-id="950b9-141">Em seguida, **clique em Conectar** para estabelecer uma conexão e pesquisar e adicionar pacientes à sua lista.</span><span class="sxs-lookup"><span data-stu-id="950b9-141">Then, click **Connect** to establish a connection and search and add patients to your list.</span></span>  

    ![ <span data-ttu-id="950b9-142">Configurações de aplicativos de pacientes no Teams</span><span class="sxs-lookup"><span data-stu-id="950b9-142">Patients app settings in Teams</span></span>](../../media/patients-app-teams.png)

    <span data-ttu-id="950b9-143">Se você receber um erro ao se conectar ao Teams durante esta etapa, envie uma captura de tela detalhada do erro, logs do [Fiddler](https://www.telerik.com/download/fiddler) e qualquer outra etapa de repro em um email com uma linha de assunto de "Solução de problemas de modo de aplicativo de pacientes – emr" para teamsforhealthcare@service.microsoft.com [.](mailto:teamsforhealthcare@service.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="950b9-143">If you get an error when connecting to Teams during this step, send a detailed screenshot of the error, logs from [Fiddler](https://www.telerik.com/download/fiddler) and any other repro steps in an email with a subject line of “Patients App – EMR mode troubleshooting” to [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com).</span></span>

## <a name="related-topics"></a><span data-ttu-id="950b9-144">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="950b9-144">Related topics</span></span>

- [<span data-ttu-id="950b9-145">Visão geral do aplicativo de pacientes</span><span class="sxs-lookup"><span data-stu-id="950b9-145">Patients app overview</span></span>](patients-app-overview.md)
- [<span data-ttu-id="950b9-146">Integração dos Registros Eletrônicos de Saúde no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="950b9-146">Integrating Electronic Healthcare Records into Microsoft Teams</span></span>](patients-app.md)