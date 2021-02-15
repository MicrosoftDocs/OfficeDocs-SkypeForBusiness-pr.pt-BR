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
description: Saiba como ativar e usar o Painel de Qualidade da Chamada e obter relatórios resumidos de qualidade das chamadas.
ms.openlocfilehash: 60363ed86e4e073b7ca5a752261ac806188900b1
ms.sourcegitcommit: ac73536f790f83a61eeb2eb8c6b71662f7bd26fc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2021
ms.locfileid: "50112841"
---
# <a name="set-up-call-quality-dashboard-cqd"></a>Configurar o Painel de Qualidade de Chamada (CQD)

Abra o CQD (Microsoft Call Quality Dashboard) em [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) (entre com suas credenciais de administrador). Ou vá para o Centro de administração do Teams e selecione **Painel de Qualidade da Chamada.** 

:::image type="content" source="media/turning-on-and-using-call-quality-dashboard3.png" alt-text="Captura de tela do botão Painel de qualidade de chamada no Centro de administração do Teams":::

Na página que é aberta, clique em **Entrar** e insira suas informações de conta de Administrador Global ou de Administrador de Serviço do Microsoft Teams. Após a primeira vez que você entrar, o CQD começará a coletar e processar dados. Lembre-se de que pode levar uma ou mais horas para processar dados suficientes para exibir resultados significativos nos relatórios.

O CQD mostra a qualidade de chamadas e reuniões, em nível de organização, para o Microsoft Teams, o Skype for Business Online e o Skype for Business Server 2019. 

> [!IMPORTANT]
> Para usar o CQD com o Skype for Business Server 2019, você terá que configurar o Conector de Dados [de Chamada.](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-call-data-connector) Consulte [Planejar o Conector de Dados de Chamada](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-call-data-connector) antes de começar.


## <a name="assign-admin-roles-for-access-to-cqd"></a>Atribuir funções de administrador para acesso ao CQD

[Atribua](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) funções para acessar o CQD às pessoas que precisam usá-lo.

Se quiser que usuários não administradores (como engenheiros de suporte e agentes de suporte) usem o Painel de Qualidade de Chamada, você pode atribuir a esses usuários uma das funções a seguir, o que dá acesso ao CQD. 


|  |Exibir relatórios  |Exibir campos EUII  |Criar relatórios  |Carregar dados de construção  |
|---------|:-------:|:-------:|:-------:|:-------:|
|Administrador Global     |Sim         |Sim         |Sim         |Sim         |
|Administrador de Serviço do Teams     |Sim         |Sim         |Sim         |Sim         |
|Administrador de Comunicações de Equipes     |Sim         |Sim         |Sim         |Sim         |
|Engenheiro de Suporte de Comunicações de Equipes     |Sim         |Sim         |Sim         |Não         |
|Especialista em Suporte de Comunicações do Teams     |Sim         |Não         |Sim         |Não         |
|Administrador do Skype for Business     |Sim         |Sim         |Sim         |Sim         |
|Leitor Global |Sim         |Sim         |Sim         |Não         |
|Leitor de Relatórios<sup>1</sup>     |Sim         |Não         |Sim         |Não         |

<sup>1</sup> Além de ler relatórios do CQD, [](https://support.office.com/article/activity-reports-0d6dfb17-8582-4172-a9a9-aed798150263) o Leitor de Relatórios pode exibir todos os relatórios de atividades no centro de administração e todos os relatórios do pacote de conteúdo de Adoção do [Microsoft 365.](https://support.office.com/article/Office-365-Adoption-content-pack-77ff780d-ab19-4553-adea-09cb65ad0f1f)

> [!NOTE]
> Se você não estiver vendo o [EUII (informações](CQD-data-and-reports.md#euii-data) de identificação do usuário final) e tiver uma das funções que podem ver essas informações, lembre-se de que o CQD mantém apenas o EUII por 28 dias. Qualquer coisa com mais de 28 dias é excluída.

Para saber mais sobre essas funções, consulte Sobre as funções de administrador do [Office 365.](/office365/admin/add-users/about-admin-roles)


Após a primeira vez que você entrar, o CQD começará a coletar e processar dados. A partir de dezembro de 2019, você ainda poderá acessar a versão mais antiga do CQD (cqd.lync.com), embora o portal herdado lhe dê um link para o CQD (cqd.teams.microsoft.com) mais recente. Eventualmente, a versão mais antiga do CQD será desativada. A partir de 1º de julho de 2020, a versão mais antiga do CQD acessa dados do CQD mais recente.


## <a name="migrate-building-data-and-reports-from-previous-version-of-cqd"></a>Migrar dados de criação e relatórios da versão anterior do CQD

> [!IMPORTANT]
> A partir de 1º de julho de 2020, você não poderá mais migrar dados de construção e relatórios do antigo CQD ( https://CQD.lync.com) . 



## <a name="use-power-bi-to-analyze-cqd-data"></a>Usar o Power BI para analisar dados CQD

Novo em janeiro de 2020: Baixe modelos de consulta [do Power BI para CQD.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true) Modelos personalizáveis do Power BI que você pode usar para analisar e relatar seus dados CQD.

Leia [Use o Power BI para analisar dados CQD](CQD-Power-BI-query-templates.md) para saber mais.


## <a name="related-topics"></a>Tópicos relacionados

[Melhorar e monitorar a qualidade da chamada para o Teams](monitor-call-quality-qos.md)

[O que é CQD?](CQD-what-is-call-quality-dashboard.md)

[Carregar dados de locatário e de construção](CQD-upload-tenant-building-data.md)

[Dados e relatórios do CQD](CQD-data-and-reports.md)

[Usar o CQD para gerenciar a qualidade da chamada e da reunião](quality-of-experience-review-guide.md)

[Dimensões e medidas disponíveis no CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Classificação de Fluxo no CQD](stream-classification-in-call-quality-dashboard.md)

[Usar o Power BI para analisar dados CQD](CQD-Power-BI-query-templates.md)
