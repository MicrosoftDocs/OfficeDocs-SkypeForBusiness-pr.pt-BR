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
# <a name="set-up-call-quality-dashboard-cqd"></a>Configurar o painel de qualidade da chamada (CQD)

Abra o painel de qualidade da chamada da Microsoft (CQD) em [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) (entre com suas credenciais de administrador). Ou acesse o centro de administração do Teams e selecione **painel de qualidade de chamada**. 

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard3.png" alt-text="Captura de tela do botão painel de qualidade de chamada no centro de administração do teams":::

Na página que é aberta, clique em **entrar** e digite sua conta de administrador global ou as informações da conta de administrador do Microsoft Teams Service. Após a primeira vez que você se conectar, o CQD começará a coletar e processar dados. Tenha em mente que pode levar uma ou mais horas para processar dados suficientes para exibir resultados significativos nos relatórios.

CQD mostra a qualidade da chamada e da reunião, em um nível da organização, para Microsoft Teams, Skype for Business Online e Skype for Business Server 2019. 

> [!IMPORTANT]
> Para usar o CQD com o Skype for Business Server 2019, você terá que [Configurar o conector de dados de chamadas](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-call-data-connector). Consulte [planejar ligar para conector de dados](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-call-data-connector) antes de começar.


## <a name="assign-admin-roles-for-access-to-cqd"></a>Atribuir funções de administrador para acessar o CQD

Atribua [funções](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) para acessar o CQD para as pessoas que precisam usá-lo.

Se quiser que usuários não administradores (como engenheiros de suporte e agentes de assistência técnica) usem o painel de qualidade de chamada, você pode atribuir a esses usuários uma das funções a seguir, que fornece acesso ao CQD. 


|  |Exibir relatórios  |Exibir campos EUII  |Criar relatórios  |Carregar dados de construção  |
|---------|:-------:|:-------:|:-------:|:-------:|
|Administrador global     |Sim         |Sim         |Sim         |Sim         |
|Administrador de Serviço do Teams     |Sim         |Sim         |Sim         |Sim         |
|Administrador de Comunicações de Equipes     |Sim         |Sim         |Sim         |Sim         |
|Engenheiro de Suporte de Comunicações de Equipes     |Sim         |Sim         |Sim         |Não         |
|Especialista em suporte do teams Communications     |Sim         |Não         |Sim         |Não         |
|Administrador do Skype for Business     |Sim         |Sim         |Sim         |Sim         |
|Leitor global |Sim         |Sim         |Sim         |Não         |
|Leitor de relatórios<sup>1</sup>     |Sim         |Não         |Sim         |Não         |

<sup>1</sup> além de ler relatórios do CQD, o leitor de relatórios pode exibir todos os [relatórios de atividades](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) no centro de administração e todos os relatórios do pacote de conteúdo de adoção do [365](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f).

> [!NOTE]
> Se você não estiver vendo [EUII (informações identificáveis pelo usuário final)](CQD-data-and-reports.md#euii-data) e tiver uma das funções que tem permissão para ver essas informações, lembre-se de que CQD só mantém EUII por 28 dias. Qualquer item mais antigo que 28 dias é excluído.

Para obter mais informações sobre essas funções, consulte [sobre as funções de administrador do Office 365](/office365/admin/add-users/about-admin-roles).


Após a primeira vez que você se conectar, o CQD começará a coletar e processar dados. A partir de dezembro de 2019, você ainda pode acessar a versão mais antiga do CQD (cqd.lync.com), embora o portal herdado forneça um link para o CQD mais recente (cqd.teams.microsoft.com). Por fim, a versão mais antiga do CQD será descomissionada. A partir de 1 ° de julho de 2020, a versão mais antiga do CQD acessa os dados do CQD mais recente.


## <a name="migrate-building-data-and-reports-from-previous-version-of-cqd"></a>Migrar dados e relatórios de construção de uma versão anterior do CQD

> [!IMPORTANT]
> A partir de 1 ° de julho de 2020, você não pode mais migrar dados de construção e relatórios do antigo CQD ( https://CQD.lync.com) . 



## <a name="use-power-bi-to-analyze-cqd-data"></a>Usar o Power BI para analisar dados do CQD

Novidades em janeiro de 2020: [Baixe os modelos de consulta do Power bi para CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true). Modelos personalizáveis do Power BI que você pode usar para analisar e relatar seus dados do CQD.

Leia [use o Power bi para analisar dados do CQD](CQD-Power-BI-query-templates.md) para saber mais.


## <a name="related-topics"></a>Tópicos relacionados

[Melhorar e monitorar a qualidade da chamada para equipes](monitor-call-quality-qos.md)

[O que é CQD?](CQD-what-is-call-quality-dashboard.md)

[Carregar dados do locatário e construção](CQD-upload-tenant-building-data.md)

[Dados e relatórios do CQD](CQD-data-and-reports.md)

[Usar o CQD para gerenciar a qualidade da chamada e da reunião](quality-of-experience-review-guide.md)

[Dimensões e medidas disponíveis no CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classificação de fluxo no CQD](stream-classification-in-call-quality-dashboard.md)

[Usar o Power BI para analisar dados do CQD](CQD-Power-BI-query-templates.md)
