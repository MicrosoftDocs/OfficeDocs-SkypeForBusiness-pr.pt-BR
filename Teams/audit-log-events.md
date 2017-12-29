---
title: Pesquisar o registro de auditoria de eventos no Microsoft Teams | Suporte da Microsoft
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: Saiba como recuperar dados do Microsoft Teams a partir do registro de auditoria.
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: b63f6b88d950038ec2e40e7b32eb74bc551cbdf1
ms.sourcegitcommit: 83aa84750e0bd210c24b3bd7315020a451d3f056
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/16/2017
---
<a name="search-the-audit-log-for-events-in-microsoft-teams"></a>Pesquisar o registro de auditoria de eventos no Microsoft Teams
==================================================

O registro de auditoria oferece recursos de pesquisa ad-hoc de eventos notáveis nos serviços do Office 365. Especificamente para o Microsoft Teams, seguem abaixo alguns exemplos de eventos capturados:

-   Criação de equipes

-   Exclusão de equipes

-   Canal adicionado

-   Configuração de canal

A lista completa de eventos do Office 365 é bastante extensa e pode ser encontrada [aqui](https://support.office.com/en-us/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c?ui=en-US&rs=en-US&ad=US#ID0EABAAA=Audited_activities).

Antes que você possa se aprofundar em insights de auditoria, a auditoria precisa primeiro ser habilitada. Para habilitar a auditoria, vá até o Centro de Administração de *Segurança e Conformidade*. Em *Pesquisa por atividade*, clique em **Iniciar registro agora**. Depois de 24 horas, os dados de auditoria estarão disponíveis via *Pesquisa de Log de Auditoria*, localizada na guia *Pesquisa e Investigação*.


> [!IMPORTANT]
> Os dados de auditoria estão disponíveis apenas a partir do ponto em que a auditoria foi habilitada.



![Captura de tela da página de pesquisa de registros de Auditoria do Centro de Segurança e Conformidade.](media/Search_the_audit_log_for_events_in_Microsoft_Teams_image2.png)

Agora, vamos dar uma olhada em como recuperar dados do Microsoft Teams a partir do registro de auditoria:

1.  Para recuperar as informações de registro de auditoria, navegue até o [Centro de Administração de Segurança e Conformidade](https://go.microsoft.com/fwlink/?linkid=855775). Em *Pesquisa e Investigação*, selecione **Pesquisa por registro de auditoria.**

    a.  O Microsoft Teams determinou que as atividades de auditoria podem ser selecionadas conforme mostrado abaixo.

![Captura de tela da página de pesquisa de registros de Auditoria do Centro de Segurança e Conformidade.](media/Search_the_audit_log_for_events_in_Microsoft_Teams_image3.png)

2.  Depois de selecionar as atividades de seu interesse, insira um intervalo de datas e usuários para recuperar as informações do Microsoft Teams. Clique em **Pesquisar** para recuperar os resultados.

3.  Essas informações podem ser exportadas para o Excel e filtradas conforme a necessidade.


> [!IMPORTANT]
> Se a auditoria ainda não tiver sido habilitada, será necessário habilitá-la para que os dados sejam exibidos no Log de auditoria.


