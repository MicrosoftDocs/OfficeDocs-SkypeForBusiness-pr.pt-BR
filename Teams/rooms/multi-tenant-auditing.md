---
title: Auditoria multilocatário
author: donnah007
ms.author: v-donnahill
manager: serdars
ms.reviewer: dstrome
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Log de auditoria para TRM.
f1keywords: ''
ms.openlocfilehash: 3681f50f0e15a7688a944c14e69907ba53dd2817
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676603"
---
# <a name="audit-logging-in-the-teams-rooms-managed-service"></a>Log de auditoria no serviço Salas do Teams Gerenciado

A auditoria Salas do Teams serviço gerenciado (TRM) permite pesquisar registros de auditoria para atividades executadas no portal por usuários e administradores. Esse recurso é habilitado por padrão. Somente o Administrador de Serviços Gerenciados tem permissão para exportar e, em seguida, exibir os logs.

> [!NOTE]
> As ações executadas no serviço TRM não são conectadas Microsoft 365 ou Office 365 auditoria 

## <a name="exporting-logs"></a>Exportando logs

Quando você exporta todos os resultados para uma pesquisa de log de auditoria, os dados brutos do log de auditoria unificado são copiados para um arquivo CSV (valor separado por vírgula) que é baixado para o computador local. 

**Para baixar logs** 

1. Vá para **Configurações > logs > auditoria**.
1. Para definir o intervalo de datas para logs de interesse, insira a **data de início** e **a data de término.**

   > [!NOTE]
   > Os logs só estão disponíveis por até 180 dias.

1. Selecione **Baixar logs.**

   ![Intervalo de datas do log de auditoria](../media/multi-tenant-auditing.png)

   Uma mensagem exibida na parte inferior da janela solicita que você abra ou salve o arquivo CSV. 

1. Selecione **Salvar** > **como** e salve o arquivo CSV no computador local. 

1. Leva algum tempo para baixar muitos resultados de pesquisa ao pesquisar todas as atividades ou em um amplo intervalo de datas. Quando o arquivo CSV terminar de ser baixado, uma mensagem na parte inferior da janela será exibida.

## <a name="detailed-properties-in-the-audit-log"></a>Propriedades detalhadas no log de auditoria

A tabela a seguir descreve as propriedades incluídas no CSV.

|Propriedade|Descrição|
| - | - |
|activity.category|<p>A categoria do objeto no qual a ação foi executada. Valores possíveis:</p><p>**Usuário, Atribuição, PartnerInvitation, Função**</p>|
|activity.objectName|O nome do objeto que foi modificado.|
|activity.operation|O tipo de operação executada. Os valores possíveis são: **Criar, Atualizar, Excluir** |
|activity.resultStatus|<p>Indica se a ação (especificada na propriedade **activity.operation** ) foi bem-sucedida ou não.</p><p>O valor é **Bem-sucedido** ou **Falhou**.</p>|
|activity.tenantId|O GUID do locatário no qual a ação foi executada|
|Creationtime|A data e a hora em UTC (Tempo Universal Coordenado) no formato ISO quando o usuário realizou a atividade.|
|user.userId|O usuário que executou a ação que resultou no registro sendo registrado.|
|user.userTenantId|O GUID do locatário para o usuário que executou a ação|


