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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.teamsadmincenter.directrouting.cqd
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: Saiba como ativar e usar o Painel de Qualidade de Chamadas e obter relatórios resumidos da qualidade das chamadas.
ms.openlocfilehash: cf4c6d56e4fa646495383b4998e80789d9cdaca67b9cc35d07f613cda4e70b85
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54300447"
---
# <a name="how-to-set-up-call-quality-dashboard"></a>Como configurar o painel de qualidade de chamada

Abra o Painel de Qualidade de Chamada da Microsoft (CQD) em [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) (entre com suas credenciais de administrador). Ou vá para o centro de administração Teams e selecione **Painel de Qualidade de Chamada**. 

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard3.png" alt-text="Captura de tela do botão Painel de qualidade de chamada no Teams de administração":::

Na página aberta, clique em **Entrar e** insira sua conta de Administrador Global ou Microsoft Teams informações da conta de administrador. Após a primeira vez que você entrar, o CQD começará a coletar e processar dados. Lembre-se de que pode levar uma ou mais horas para processar dados suficientes para exibir resultados significativos nos relatórios.

O CQD mostra a qualidade de chamada e reunião, no nível de toda a organização, para Microsoft Teams, Skype for Business Online e Skype for Business Server 2019. 

> [!IMPORTANT]
> Para usar o CQD com Skype for Business Server 2019, você terá que configurar o Conector de Dados [de Chamada.](/skypeforbusiness/hybrid/configure-call-data-connector) Consulte [Plan Call Data Connector](/skypeforbusiness/hybrid/plan-call-data-connector) before you start.


## <a name="assign-admin-roles-for-access-to-cqd"></a>Atribuir funções de administrador para acesso ao CQD

Atribua [funções](/microsoft-365/admin/add-users/about-admin-roles) para acessar o CQD às pessoas que precisam usá-lo.

Se você quiser que os usuários que não são administradores (como engenheiros de suporte e agentes do helpdesk) usem o Painel de Qualidade de Chamada, você pode atribuir a esses usuários uma das seguintes funções, que dá acesso ao CQD. 


|&nbsp;  |Exibir relatórios  |Exibir campos EUII  |Criar relatórios  |Upload criar dados  |
|---------|:-------:|:-------:|:-------:|:-------:|
|Administrador Global     |Sim         |Sim         |Sim         |Sim         |
|Teams Administrador     |Sim         |Sim         |Sim         |Sim         |
|Administrador de Comunicações do Teams     |Sim         |Sim         |Sim         |Sim         |
|Engenheiro de Suporte de Comunicações de Equipes     |Sim         |Sim         |Sim         |Não         |
|Especialista em suporte à comunicação de equipes     |Sim         |Não         |Sim         |Não         |
|Administrador do Skype for Business     |Sim         |Sim         |Sim         |Sim         |
|Leitor Global |Sim         |Sim         |Sim         |Não         |
|Leitor de Relatórios<sup>1</sup>     |Sim         |Não         |Sim         |Não         |

<sup>1</sup> Além de ler relatórios CQD, o [](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) Leitor de Relatórios pode exibir todos os relatórios de atividades no centro de administração e quaisquer relatórios do pacote de conteúdo Microsoft 365 [Adoção.](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f)

> [!NOTE]
> Se você não estiver vendo [EUII (informações](CQD-data-and-reports.md#euii-data) de identificação do usuário final) e tiver uma das funções que têm permissão para ver essas informações, tenha em mente que o CQD só mantém a EUII por 28 dias. Qualquer coisa com mais de 28 dias é excluída.

Para obter mais informações sobre essas funções, consulte [About Office 365 admin roles](/office365/admin/add-users/about-admin-roles).


Após a primeira vez que você entrar, o CQD começará a coletar e processar dados. A partir de dezembro de 2019, você ainda pode acessar a versão mais antiga do CQD (cqd.lync.com), embora o portal herdado lhe dê um link para o CQD mais recente (cqd.teams.microsoft.com). Eventualmente, a versão mais antiga do CQD será desativada. A partir de 1º de julho de 2020, a versão mais antiga do CQD acessa dados do CQD mais recente.


## <a name="migrate-building-data-and-reports-from-previous-version-of-cqd"></a>Migrar dados de criação e relatórios da versão anterior do CQD

> [!IMPORTANT]
> A partir de 1º de julho de 2020, você não pode mais migrar dados de construção e relatórios do CQD antigo ( https://CQD.lync.com) . 



## <a name="use-power-bi-to-analyze-cqd-data"></a>Usar o Power BI para analisar dados do CQD

Novidade em janeiro de 2020: Baixar Power BI [de consulta para CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true). Modelos de Power BI personalizáveis que você pode usar para analisar e relatar seus dados CQD.

Leia [Use Power BI para analisar dados CQD](CQD-Power-BI-query-templates.md) para saber mais.


## <a name="related-topics"></a>Tópicos relacionados

[Melhorar e monitorar a qualidade de chamada para Teams](monitor-call-quality-qos.md)

[O que é CQD?](CQD-what-is-call-quality-dashboard.md)

[Carregar dados de locatário e de criação](CQD-upload-tenant-building-data.md)

[Dados e relatórios CQD](CQD-data-and-reports.md)

[Use CQD para gerenciar a qualidade da chamada e da reunião](quality-of-experience-review-guide.md)

[Dimensões e medidas disponíveis no CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classificação de fluxo no CQD](stream-classification-in-call-quality-dashboard.md)

[Usar o Power BI para analisar dados do CQD](CQD-Power-BI-query-templates.md)
