---
title: Configurar o Painel de Qualidade de Chamada (CQD)
author: CarolynRowe
ms.author: crowe
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
description: Saiba mais sobre como ativar e usar o Painel de Qualidade de Chamadas e obter relatórios resumidos de qualidade de chamadas.
ms.openlocfilehash: 052b38634d17aa6d0086c80ed2a638a7818a729f
ms.sourcegitcommit: 4d88637f510a78d5709d1213c3e285d83a022014
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/14/2022
ms.locfileid: "66797376"
---
# <a name="set-up-call-quality-dashboard"></a>Configurar o Painel de Qualidade de Chamadas

Abra o Painel de Qualidade de Chamada da Microsoft (CQD) em [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) (entre com suas credenciais de administrador). Ou vá para o Centro de administração do Teams e selecione **Painel de Qualidade de Chamada & análise** > **.**

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard3.png" alt-text="Captura de tela do botão Painel de qualidade de chamada no Centro de administração do Teams.":::

Na página que é aberta, clique **em Entrar e** insira suas informações de conta de Administrador Global ou de Administrador do Microsoft Teams. Após a primeira vez que você entrar, o CQD começará a coletar e processar dados. Tenha em mente que pode levar uma ou mais horas para processar dados suficientes para exibir resultados significativos nos relatórios.

O CQD mostra a qualidade de chamadas e reuniões, em nível de toda a organização, para o Microsoft Teams, o Skype for Business Online e o Skype for Business Server 2019. 

> [!IMPORTANT]
> Para usar o CQD com Skype for Business Server 2019, você precisará configurar [o Conector de Dados de Chamada](/skypeforbusiness/hybrid/configure-call-data-connector). Consulte [Plan Call Data Connector](/skypeforbusiness/hybrid/plan-call-data-connector) antes de começar.


## <a name="assign-admin-roles-for-access-to-cqd"></a>Atribuir funções de administrador para acesso ao CQD

[Atribua](/microsoft-365/admin/add-users/about-admin-roles) funções para acessar o CQD às pessoas que precisam usá-lo.

Se você quiser que usuários não administradores (como engenheiros de suporte e agentes de assistência técnica) usem o Painel de Qualidade de Chamadas, atribua a esses usuários uma das funções a seguir, que fornece acesso ao CQD. 


|&nbsp;  |Exibir relatórios  |Exibir campos EUII  |Criar relatórios  |Carregar dados de compilação  |
|---------|:-------:|:-------:|:-------:|:-------:|
|Administrador Global     |Sim         |Sim         |Sim         |Sim         |
|Administrador do Teams     |Sim         |Sim         |Sim         |Sim         |
|Administrador de Comunicações de Equipes     |Sim         |Sim         |Sim         |Sim         |
|Engenheiro de Suporte de Comunicações de Equipes     |Sim         |Sim         |Sim         |Não         |
|Especialista em Suporte de Comunicações do Teams     |Sim         |Não         |Sim         |Não         |
|Skype for Business administrador     |Sim         |Sim         |Sim         |Sim         |
|Leitor Global |Sim         |Sim         |Sim         |Não         |
|Leitor de Relatórios<sup>1</sup>     |Sim         |Não         |Sim         |Não         |

<sup>1</sup> Além de ler relatórios do CQD, o Leitor de Relatórios pode exibir todos os relatórios [](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) de atividades no centro de administração e todos os relatórios do pacote de conteúdo de Adoção do [Microsoft 365](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f).

> [!NOTE]
> Se você não estiver vendo [EUII (](CQD-data-and-reports.md#euii-data) informações de identificação do usuário final) e tiver uma das funções que têm permissão para ver essas informações, tenha em mente que o CQD mantém apenas EUII por 28 dias. Qualquer coisa com mais de 28 dias é excluída.

Para obter mais informações sobre essas funções, consulte [About Office 365 admin.](/office365/admin/add-users/about-admin-roles)


Após a primeira vez que você entrar, o CQD começará a coletar e processar dados.

## <a name="use-power-bi-to-analyze-cqd-data"></a>Usar o Power BI para analisar dados CQD

Novidade em janeiro de 2020: [baixe modelos de consulta do Power BI para CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true). Modelos personalizáveis do Power BI que você pode usar para analisar e relatar seus dados CQD.

Leia [Use o Power BI para analisar dados CQD](CQD-Power-BI-query-templates.md) para saber mais.

## <a name="related-topics"></a>Tópicos relacionados

[Melhorar e monitorar a qualidade da chamada para o Teams](monitor-call-quality-qos.md)

[O que é CQD?](CQD-what-is-call-quality-dashboard.md)

[Carregar dados de locatário e de criação](CQD-upload-tenant-building-data.md)

[Dados e relatórios do CQD](CQD-data-and-reports.md)

[Usar o CQD para gerenciar a qualidade da chamada e da reunião](quality-of-experience-review-guide.md)

[Dimensões e medidas disponíveis no CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classificação de fluxo no CQD](stream-classification-in-call-quality-dashboard.md)

[Usar o Power BI para analisar dados CQD](CQD-Power-BI-query-templates.md)
