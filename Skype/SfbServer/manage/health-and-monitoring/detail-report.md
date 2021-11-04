---
title: Relatório de Detalhes da Conferência Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 1d61cd81-dcfe-40b4-9a41-a73b038bc216
description: 'Resumo: saiba mais sobre o Relatório de Detalhes da Conferência usado Skype for Business Server.'
ms.openlocfilehash: 56fafff71f1700667a2ad982f56db099cb60c45e
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60737797"
---
# <a name="conference-detail-report-in-skype-for-business-server"></a>Relatório de Detalhes da Conferência Skype for Business Server

**Resumo:** Saiba mais sobre o Relatório de Detalhes da Conferência usado Skype for Business Server.

O Relatório de Detalhe da Conferência oferece informações detalhadas sobre todos os usuários que participaram de uma conferência. Por exemplo, você pode ver tal informação como a data e hora que um usuário participou da conferência, a data e hora que o usuário saiu da conferência e o agente do usuário do ponto de extremidade que foi usado para conectar o usuário à conferência. Também é possível ver informações da função do usuário em cada conferência (por exemplo, Apresentador ou Participante). Talvez, o mais importante, você pode ver rapidamente quais usuários participaram com sucesso e concluíram a conferência e quais usuários não puderam participar e concluir a conferência.

## <a name="accessing-the-conference-detail-report"></a>Acessar o Relatório de Detalhe da Conferência

O Relatório de Detalhe da Conferência pode ser acessado pelos seguintes relatórios:

- O [Call Admission Control Report](call-admission-control-report.md) (clicando na métrica Detalhe de uma conferência)

- O [Failure List Report](failure-list-report.md) (clicando na métrica Conferência)

- O [User Activity Report](call-diagnostic-reports-per-user.md) (clicando na métrica URI da conferência)

Do Relatório de Detalhe da Conferência, é possível acessar o [Diagnostic Report](diagnostic-report.md) clicando na métrica Relatório de Diagnóstico (Detalhe).

## <a name="filters"></a>Filtros

Nenhum. Você não pode filtrar o Relatório de Detalhe da Conferência.

## <a name="metrics"></a>Métrica

A tabela a seguir lista as informações fornecidas na seção Informação da Conferência do Relatório de Detalhe da Conferência.

**Métricas de Informação da Conferência**


| **Nome**                 | **Descrição**                                                                                                            |
|:-------------------------|:---------------------------------------------------------------------------------------------------------------------------|
| **URI de Conferência** <br/> | URI atribuído à conferência. Por exemplo:  <br/> sip:kmyer@litwareinc.com;gruu;opaque=app:conf:focus:id:drg2y8v4  <br/> |
| **FQDN do Pool** <br/>      | Nome de domínio totalmente qualificado do pool do Registrador ou Servidor de Borda envolvido em uma sessão.  <br/>                             |
| **Hora inicial** <br/>     | Data e hora que a conferência iniciou.  <br/>                                                                          |
| **Organizador** <br/>      | Endereço SIP do usuário que organizou a conferência.  <br/>                                                               |
| **Hora final** <br/>       | Data e hora que a conferência terminou.  <br/>                                                                            |

A tabela a seguir lista a informação oferecida na Seção de Participação da Conferência do Relatório de Detalhe da Conferência.

**Métricas de Participação da Conferência**

|**Nome**|**Descrição**|
|:-----|:-----|
|**Usuário** <br/> |Endereço SIP do usuário que participou da conferência.  <br/> |
|**Função** <br/> |Função (por exemplo, Apresentador) do participante da conferência.  <br/> |
|**Conectividade** <br/> |Conectividade de rede (geralmente Externa ou Interna) do participante.  <br/> |
|**Hora de participação** <br/> |Data e hora que o participante entrou na conferência.  <br/> |
|**Hora de saída** <br/> |Data e hora que o participante saiu da conferência.  <br/> |
|**Agente do usuário** <br/> |Identificador do software usado pelo ponto de extremidade do participante.  <br/> |
|**Relatórios de diagnóstico** <br/> |Oferece informação de resolução de problemas e diagnóstico. Incluindo códigos de resposta SIP, cabeçalhos de diagnóstico, hora de participação da conferência e IDs de diagnósticos para sessões em falha.  <br/> |

A tabela a seguir lista as informações fornecidas na seção Modalidades de Conferência do Relatório de Detalhes da Conferência.

**Métricas das Modalidades da Conferência**

|**Nome**|**Descrição**|
|:-----|:-----|
|**Usuário** <br/> |Endereço SIP do usuário que participou da conferência.  <br/> |
|**Hora de participação** <br/> |Data e hora que o participante entrou na conferência.  <br/> |
|**Hora de saída** <br/> |Data e hora que um participante deixou a conferência.  <br/> |
|**URI do servidor de conferência** <br/> |URI para o servidor de Conferência usado na conferência.  <br/> |
|**Relatórios de diagnóstico** <br/> |Oferece informação de resolução de problemas e diagnóstico. Incluindo códigos de resposta SIP, cabeçalhos de diagnóstico, hora de participação da conferência e IDs de diagnósticos para sessões em falha.  <br/> |


