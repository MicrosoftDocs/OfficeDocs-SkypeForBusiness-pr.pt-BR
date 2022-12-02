---
title: Configuração do CQD (Painel de Qualidade de Chamada)
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
description: Saiba mais sobre como ativar e usar o Painel de Qualidade de Chamada e obter relatórios de resumo da qualidade das chamadas.
ms.openlocfilehash: 5f3b9fbb42199892136569ac179907b18da4e460
ms.sourcegitcommit: aef1ab47fb9cb4502cb49bc3c7ffafcd62e54c82
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/02/2022
ms.locfileid: "69245727"
---
# <a name="set-up-the-call-quality-dashboard"></a>Configurar o Painel de Qualidade de Chamada

Abra o CQD (Painel de Qualidade de Chamada) Microsoft em [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) (entre com suas credenciais de administrador). Ou vá para o centro de administração do Teams e selecione **Análise & relatórios** > **Chame Painel de Qualidade**.

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard3.png" alt-text="Captura de tela do botão Painel de qualidade chamar no centro de administração do Teams.":::

Na página aberta, clique **em Entrar** e insira sua conta de Administrador Global ou Microsoft informações da conta do Administrador do Teams. Após a primeira vez que você entrar, o CQD começará a coletar e processar dados. Tenha em mente que pode levar uma ou mais horas para processar dados suficientes para exibir resultados significativos nos relatórios.

O CQD mostra a qualidade da chamada e da reunião, em um nível de organização, para Microsoft Teams, Skype for Business Online e Skype for Business Server 2019. 

> [!IMPORTANT]
> Para usar o CQD com Skype for Business Server 2019, você precisará [configurar o Conector de Dados de Chamada](/skypeforbusiness/hybrid/configure-call-data-connector). Consulte [Planejar Conector de Dados de Chamada](/skypeforbusiness/hybrid/plan-call-data-connector) antes de começar.


## <a name="assign-admin-roles-for-access-to-cqd"></a>Atribuir funções de administrador para acesso ao CQD

Atribua [funções](/microsoft-365/admin/add-users/about-admin-roles) para acessar o CQD às pessoas que precisam usá-lo.

Se você quiser que usuários não administradores (como engenheiros de suporte e agentes auxiliares) usem o Painel de Qualidade de Chamada, você pode atribuir a esses usuários uma das funções a seguir, que dá acesso ao CQD. 


|&nbsp;  |Exibir relatórios  |Exibir campos EUII  |Criar relatórios  |Carregar dados de construção  |
|---------|:-------:|:-------:|:-------:|:-------:|
|Administrador Global     |Sim         |Sim         |Sim         |Sim         |
|Administrador do Teams     |Sim         |Sim         |Sim         |Sim         |
|Administrador de Comunicações de Equipes     |Sim         |Sim         |Sim         |Sim         |
|Engenheiro de Suporte de Comunicações de Equipes     |Sim         |Sim         |Sim         |Não         |
|Especialista em Suporte de Comunicações do Teams     |Sim         |Não         |Sim         |Não         |
|Administrador Skype for Business     |Sim         |Sim         |Sim         |Sim         |
|Leitor Global |Sim         |Sim         |Sim         |Não         |
|Leitor<sup>de Relatórios 1</sup>     |Sim         |Não         |Sim         |Não         |

<sup>1</sup> Além de ler relatórios do CQD, o Leitor de Relatórios pode exibir todos os [relatórios de atividade](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) no centro de administração e todos os relatórios do [pacote de conteúdo de adoção do Microsoft 365](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f).

> [!NOTE]
> Se você não estiver vendo [EUII (informações identificáveis do usuário final)](CQD-data-and-reports.md#euii-data) e tiver uma das funções permitidas para ver essas informações, tenha em mente que o CQD só mantém EUII por 28 dias. Qualquer coisa com mais de 28 dias é excluída.

Para obter mais informações sobre essas funções, consulte [Sobre Office 365 funções de administrador](/office365/admin/add-users/about-admin-roles).


Após a primeira vez que você entrar, o CQD começará a coletar e processar dados.

## <a name="use-power-bi-to-analyze-cqd-data"></a>Usar o Power BI para analisar dados do CQD

Novidades em janeiro de 2020: [baixe modelos de consulta do Power BI para CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true). Modelos personalizáveis do Power BI que você pode usar para analisar e relatar seus dados do CQD.

Leia [Usar o Power BI para analisar dados CQD](CQD-Power-BI-query-templates.md) para saber mais.

## <a name="related-topics"></a>Tópicos relacionados

[Melhorar e monitorar a qualidade da chamada para o Teams](monitor-call-quality-qos.md)

[O que é CQD?](CQD-what-is-call-quality-dashboard.md)

[Carregar dados de locatário e de construção](CQD-upload-tenant-building-data.md)

[Dados e relatórios do CQD](CQD-data-and-reports.md)

[Usar o CQD para gerenciar a qualidade da chamada e da reunião](quality-of-experience-review-guide.md)

[Dimensões e medidas disponíveis no CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classificação de fluxo no CQD](stream-classification-in-call-quality-dashboard.md)

[Usar o Power BI para analisar dados do CQD](CQD-Power-BI-query-templates.md)
