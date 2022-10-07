---
title: Log de auditoria no Portal do MTR Pro
author: altsou
ms.author: altsou
manager: serdars
ms.reviewer: altsou
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_MTRP
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Log de auditoria para o Portal do MTR Pro.
f1keywords: ''
ms.openlocfilehash: 0436618e257128deb38d890cb92813ae13921e7d
ms.sourcegitcommit: 64c01699022b47fdfec8dc6e2ca279e57eae3baa
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2022
ms.locfileid: "68243912"
---
# <a name="audit-logging-in-the-mtr-pro-portal"></a>Log de auditoria no Portal do MTR Pro

Os logs de auditoria do Portal do MTR Pro permitem que você pesquise registros de auditoria para atividades executadas por usuários e administradores. Esse recurso é habilitado por padrão. Somente o Administrador de Serviços Gerenciados tem permissão para exportar e, em seguida, exibir os logs.

> [!NOTE]
> As ações executadas no Portal do MTR Pro não são registradas no Microsoft 365 ou Office 365 auditoria 

## <a name="exporting-logs"></a>Exportando logs

Quando você exporta todos os resultados para uma pesquisa de log de auditoria, os dados brutos do log de auditoria unificado são copiados para um arquivo CSV (valor separado por vírgula) que é baixado para o computador local. 

**Para baixar logs** 

1. Vá para **Configurações > Logs > Auditoria**.
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


