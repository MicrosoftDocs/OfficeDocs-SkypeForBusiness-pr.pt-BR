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
# <a name="connect-the-patients-app-to-azure-api-for-fhir"></a>Conecte o aplicativo de pacientes à API do Azure para FHIR

> [!NOTE]
> A partir de 30 de outubro de 2020, o aplicativo Pacientes será retirado e substituído pelo [aplicativo de Listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) no Teams. Os dados do aplicativo Pacientes são armazenados na caixa de correio do grupo do Office 365 que apoia a equipe. Todos os dados associados ao aplicativo Pacientes são mantidos neste grupo, mas não podem mais ser acessados por meio da interface do usuário. Os usuários podem criar suas listas usando o [aplicativo Listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).
>
>Com o Lists, as equipes de atendimento em sua organização de saúde podem criar listas de pacientes para cenários que variam desde reuniões gerais com a equipe de atendimento até o monitoramento geral dos pacientes. Confira o modelo Pacientes no Lists para começar. Para saber mais sobre como gerenciar o aplicativo Lists em sua organização, consulte [Gerenciar o aplicativo Lists](../../manage-lists-app.md).

Siga estas etapas para permitir que o aplicativo Patients no Microsoft Teams acesse uma API do Azure para instância FHIR. Este artigo supõe que você tenha uma [API do Azure para instância FHIR](https://azure.microsoft.com/services/azure-api-for-fhir/) configurada e configurada em seu locatário.  Se você ainda não criou uma API do Azure para instância FHIR em seu locatário, consulte Início rápido: Implantar a [API do Azure para FHIR](/azure/healthcare-apis/fhir-paas-portal-quickstart)usando o portal do Azure .

1. Clique [aqui para](https://login.microsoftonline.com/common/adminConsent?client_id=4aee3506-b263-43e0-ba31-1468fa7b2806) conceder o consentimento do administrador para o aplicativo Pacientes. Quando solicitado, entre usando suas credenciais de administrador de locatário ou administrador global e clique em **Aceitar** para conceder as permissões necessárias.

    ![Captura de tela da solicitação de permissão para o Aplicativo de Pacientes](../../media/patients-app-permissions-request.png)

    Depois de aceitar, feche a janela. Você verá uma página que pode ter esta aparência. Você pode ignorar a mensagem de erro na página. É inofensivo e indica que o consentimento é concedido. (Estamos trabalhando em uma página mais fácil de usar para essa URL. Fique atento!)

    ![Captura de tela da solicitação de permissão para o Aplicativo de Pacientes](../../media/patients-app-permissions-request-granted.png)

2. Entre no [portal do Azure](https://portal.azure.com) com suas credenciais de administrador.

3. Na navegação à esquerda, selecione **Azure Active Directory** e, em seguida, selecione **Aplicativos Empresariais**.

    Procure uma linha chamada **Patients (dev)** e copie o valor na coluna **ID** do objeto para sua área de transferência.

    ![Captura de tela da linha Pacientes (dev) no portal do Azure](../../media/patients-app-azure-portal-object-id.png)

4. Vá para a instância de recurso da API do Azure para FHIR à qual você deseja conectar o aplicativo Patients (pesquisando por ele ou navegando por seus recursos) e abra as configurações dessa instância.

    ![Captura de tela da API do Azure para configurações de instância FHIR no portal do Azure](../../media/patients-app-azure-portal-instance-settings.png)

5. Clique **em Autenticação** e, em seguida, colar a ID do objeto que você copiou na etapa 3 para a caixa **IDs** de objeto Permitido. Isso permite que o aplicativo Patients acesse o servidor FHIR. Depois de colar a ID do objeto, o Azure Active Directory a valida e uma marca de seleção verde aparece ao lado dele.

    ![Captura de tela das configurações de autenticação no portal do Azure](../../media/patients-app-azure-portal-authentication.png)

6. Clique em **Salvar**. Isso reimplanta a instância, que pode levar alguns minutos.

7. Clique **em Visão** Geral e copie a URL do ponto de extremidade de **metadados FHIR.** Remova a marca de metadados para obter a URL do servidor FHIR. Por exemplo, `https://test02-teamshealth.azurehealthcareapis.com/` .

    ![o ponto de extremidade de metadados no portal do Azure](../../media/patients-app-azure-portal-metadata-endpoint.png)

8. No Teams, vá para a instância do aplicativo Pacientes carregada em sua equipe, clique em Configurações **e,** na caixa **Link,** insira a URL do ponto de extremidade do servidor FHIR. Em seguida, **clique em Conectar** para estabelecer uma conexão e pesquisar e adicionar pacientes à sua lista.  

    ![ Configurações de aplicativos de pacientes no Teams](../../media/patients-app-teams.png)

    Se você receber um erro ao se conectar ao Teams durante esta etapa, envie uma captura de tela detalhada do erro, logs do [Fiddler](https://www.telerik.com/download/fiddler) e qualquer outra etapa de repro em um email com uma linha de assunto de "Solução de problemas de modo de aplicativo de pacientes – emr" para teamsforhealthcare@service.microsoft.com [.](mailto:teamsforhealthcare@service.microsoft.com)

## <a name="related-topics"></a>Tópicos relacionados

- [Visão geral do aplicativo de pacientes](patients-app-overview.md)
- [Integração dos Registros Eletrônicos de Saúde no Microsoft Teams](patients-app.md)