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
ms.openlocfilehash: 3bd6cdc694eb197c1e8fd45d7e133576732cdc22
ms.sourcegitcommit: f4f5ad1391b472d64390180c81c2680f011a8a10
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/06/2020
ms.locfileid: "48367611"
---
# <a name="connect-the-patients-app-to-azure-api-for-fhir"></a>Conecte o aplicativo de pacientes à API do Azure para FHIR

> [!IMPORTANT]
> **A partir de 30 de outubro de 2020, o aplicativo pacientes será preterido, e os usuários não poderão mais instalá-lo na App Store da equipe. Recomendamos que você comece a usar o [aplicativo listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) no Microsoft Teams hoje mesmo.**
>
>Os dados do aplicativo pacientes são armazenados na caixa de correio do grupo do grupo do Office 365 que faz a equipe. Quando o aplicativo pacientes é desativado, todos os dados associados a ele serão mantidos nesse grupo, mas não poderão mais ser acessados por meio da interface do usuário. Os usuários atuais podem recriar suas listas usando o [aplicativo listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).
>
>O [aplicativo listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) é pré-instalado para todos os usuários do Teams e está disponível como uma guia em cada equipe e canal. Com listas, o cuidado com equipes pode criar listas de pacientes usando o modelo de pacientes incorporado, do zero ou importando dados para o Excel. Para saber mais sobre como gerenciar o aplicativo listas em sua organização, consulte [gerenciar o aplicativo listas](../../manage-lists-app.md).

Siga estas etapas para permitir que o aplicativo pacientes no Microsoft Teams acesse uma API do Azure para a instância FHIR. Este artigo pressupõe que você tenha uma [API do Azure para a instância FHIR](https://azure.microsoft.com/services/azure-api-for-fhir/) configurada e configurada em seu locatário.  Se você ainda não criou uma API do Azure para a instância do FHIR em seu locatário, consulte [início rápido: implantar a API do Azure para FHIR usando o portal do Azure](https://docs.microsoft.com/azure/healthcare-apis/fhir-paas-portal-quickstart).


1. Clique [aqui](https://login.microsoftonline.com/common/adminConsent?client_id=4aee3506-b263-43e0-ba31-1468fa7b2806) para conceder consentimento de administrador para o aplicativo pacientes. Quando solicitado, entre usando o administrador de locatários ou as credenciais de administrador global e, em seguida, clique em **aceitar** para conceder as permissões necessárias.

    ![Captura de tela de solicitação de permissão para o aplicativo pacientes](../../media/patients-app-permissions-request.png)

    Depois de aceitar, feche a janela. Você verá uma página que pode ter a seguinte aparência. Você pode ignorar a mensagem de erro na página. É inofensivo e indica que o consentimento é concedido. (Estamos trabalhando em uma página mais fácil de usar para esta URL. Fique atento!)

    ![Captura de tela de solicitação de permissão para o aplicativo pacientes](../../media/patients-app-permissions-request-granted.png)
2. Entre no [portal do Azure](https://portal.azure.com) com suas credenciais de administrador.
3. Na navegação à esquerda, selecione **Azure Active Directory**e, em seguida, selecione **aplicativos corporativos**.
    Procure por uma linha chamada **pacientes (dev)** e, em seguida, copie o valor na coluna **ID do objeto** para a área de transferência.
    ![Captura de tela da linha pacientes (dev) no portal do Azure](../../media/patients-app-azure-portal-object-id.png)
4. Vá para a API do Azure para a instância de recursos do FHIR à qual você deseja conectar o aplicativo pacientes (ou procurando por ele ou navegando pelos recursos) e abra as configurações dessa instância.

    ![Captura de tela da API do Azure para configurações de instância do FHIR no portal do Azure](../../media/patients-app-azure-portal-instance-settings.png)

5. Clique em **autenticação**e cole a ID do objeto que você copiou na etapa 3 para a caixa **IDs de objeto permitidos** . Isso permite que o aplicativo pacientes acesse o servidor FHIR. Depois que você colar a identificação do objeto, o Azure Active Directory a validará, e uma marca de seleção verde aparecerá ao lado dela.

    ![Captura de tela das configurações de autenticação no portal do Azure](../../media/patients-app-azure-portal-authentication.png)

6. Clique em **Salvar**. Isso reimplanta a instância, o que pode levar alguns minutos.
7. Clique em **visão geral**e copie a URL do **ponto de extremidade de metadados FHIR**. Remova a marca Metadata para obter a URL do servidor do FHIR. Por exemplo, https://test02-teamshealth.azurehealthcareapis.com/ . 

    ![Captura de tela do ponto de extremidade de metadados no portal do Azure](../../media/patients-app-azure-portal-metadata-endpoint.png)

8. No Teams, vá para a instância do aplicativo pacientes que está carregada na sua equipe, clique em **configurações**e, na caixa **link** , digite a URL do ponto de extremidade do servidor FHIR. Em seguida, clique em **conectar** para estabelecer uma conexão e pesquisar e adicionar pacientes à sua lista.  

    ![Captura de tela das configurações do aplicativo pacientes no Teams](../../media/patients-app-teams.png)
    
    Se você receber um erro ao se conectar ao Microsoft Teams durante esta etapa, envie uma captura de tela detalhada do erro, logs do [Fiddler](https://www.telerik.com/download/fiddler) e de quaisquer outras etapas de reprodução em um email com uma linha de assunto "aplicativo pacientes – solução de problemas do modo EMR" para [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com).

## <a name="related-topics"></a>Tópicos relacionados

- [Visão geral do aplicativo de pacientes](patients-app-overview.md)
- [Integração dos Registros Eletrônicos de Saúde no Microsoft Teams](patients-app.md)
