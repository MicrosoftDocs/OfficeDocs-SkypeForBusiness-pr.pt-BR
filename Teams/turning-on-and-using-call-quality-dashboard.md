---
title: Configurar o Painel de Qualidade de Chamada (CQD)
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.teamsadmincenter.directrouting.cqd
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: Saiba como ativar e usar o Painel de Qualidade de Chamadas e obter relatórios resumidos de qualidade das chamadas.
ms.openlocfilehash: 292fa240b9298bd60715d812ec95d8e53403c489
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58750027"
---
# <a name="how-to-set-up-call-quality-dashboard"></a>Como configurar o painel de qualidade de chamada

Abra o Painel de Qualidade de Chamada da Microsoft (CQD) em [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) (entre com suas credenciais de administrador). Ou vá para o centro de administração Teams e selecione **Painel de Qualidade de Chamada**. 

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard3.png" alt-text="Captura de tela do botão Painel de qualidade de chamada no Teams de administração.":::

Na página aberta, clique em **Entrar e** insira sua conta de Administrador Global ou Microsoft Teams informações da conta de administrador. Após a primeira vez que você entrar, o CQD começará a coletar e processar dados. Lembre-se de que pode levar uma ou mais horas para processar dados suficientes para exibir resultados significativos nos relatórios.

O CQD mostra a qualidade de chamada e reunião, no nível de toda a organização, para Microsoft Teams, Skype for Business Online e Skype for Business Server 2019. 

> [!IMPORTANT]
> Para usar o CQD com Skype for Business Server 2019, você terá que [configurar o Conector de Dados de Chamada.](/skypeforbusiness/hybrid/configure-call-data-connector) Consulte [Plan Call Data Connector](/skypeforbusiness/hybrid/plan-call-data-connector) before you start.


## <a name="assign-admin-roles-for-access-to-cqd"></a>Atribuir funções de administrador para acesso ao CQD

Atribua [funções](/microsoft-365/admin/add-users/about-admin-roles) para acessar o CQD às pessoas que precisam usá-lo.

Se você quiser que os usuários que não são administradores (como engenheiros de suporte e agentes do helpdesk) usem o Painel de Qualidade de Chamada, você pode atribuir a esses usuários uma das seguintes funções, que dá acesso ao CQD. 


|&nbsp;  |Exibir relatórios  |Exibir campos EUII  |Criar relatórios  |Upload criar dados  |
|---------|:-------:|:-------:|:-------:|:-------:|
|Administrador Global     |Sim         |Sim         |Sim         |Sim         |
|Administrador do Teams     |Sim         |Sim         |Sim         |Sim         |
|Administrador de Comunicações de Equipes     |Sim         |Sim         |Sim         |Sim         |
|Engenheiro de Suporte de Comunicações de Equipes     |Sim         |Sim         |Sim         |Não         |
|Teams Especialista em Suporte de Comunicações     |Sim         |Não         |Sim         |Não         |
|Skype for Business Administrador     |Sim         |Sim         |Sim         |Sim         |
|Leitor Global |Sim         |Sim         |Sim         |Não         |
|Leitor de Relatórios<sup>1</sup>     |Sim         |Não         |Sim         |Não         |

<sup>1 Além</sup> de ler relatórios CQD, o [](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) Leitor de Relatórios pode exibir todos os relatórios de atividades no centro de administração e quaisquer relatórios do pacote de conteúdo Microsoft 365 [Adoção.](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f)

> [!NOTE]
> Se você não estiver vendo [EUII (informações](CQD-data-and-reports.md#euii-data) de identificação do usuário final) e tiver uma das funções que têm permissão para ver essas informações, tenha em mente que o CQD só mantém a EUII por 28 dias. Qualquer coisa com mais de 28 dias é excluída.

Para obter mais informações sobre essas funções, consulte [About Office 365 admin roles](/office365/admin/add-users/about-admin-roles).


Após a primeira vez que você entrar, o CQD começará a coletar e processar dados.




## <a name="use-power-bi-to-analyze-cqd-data"></a>Usar Power BI para analisar dados CQD

Novidade em janeiro de 2020: [Baixar Power BI de consulta para CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true). Modelos de Power BI personalizáveis que você pode usar para analisar e relatar seus dados CQD.

Leia [Use Power BI para analisar dados CQD](CQD-Power-BI-query-templates.md) para saber mais.


## <a name="related-topics"></a>Tópicos relacionados

[Melhorar e monitorar a qualidade de chamada para Teams](monitor-call-quality-qos.md)

[O que é CQD?](CQD-what-is-call-quality-dashboard.md)

[Upload locatário e a criação de dados](CQD-upload-tenant-building-data.md)

[Dados e relatórios do CQD](CQD-data-and-reports.md)

[Usar o CQD para gerenciar a qualidade de chamada e reunião](quality-of-experience-review-guide.md)

[Dimensões e medidas disponíveis no CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classificação de fluxo no CQD](stream-classification-in-call-quality-dashboard.md)

[Usar Power BI para analisar dados CQD](CQD-Power-BI-query-templates.md)
