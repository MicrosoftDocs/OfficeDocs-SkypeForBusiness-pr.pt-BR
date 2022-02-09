---
title: Relatório de Diagnóstico no Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b389dbd9-f2e8-4184-93d0-2e504796ac16
description: 'Resumo: saiba mais sobre o Relatório de Diagnóstico no Skype for Business Server.'
ms.openlocfilehash: 9ab417619828f4c48695ce19d68a5d1bc0f91171
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62397775"
---
# <a name="diagnostic-report-in-skype-for-business-server"></a>Relatório de Diagnóstico no Skype for Business Server
 
**Resumo:** Saiba mais sobre o Relatório de Diagnóstico Skype for Business Server.
  
O Relatório de diagnóstico fornece diagnósticos e informações para a solução de problemas de uma sessão com falha. Essas informações incluem a ID de diagnóstico e o cabeçalho de Diagnóstico que foram importados quando a sessão falhou. A ID de diagnóstico é um identificador exclusivo (na forma de um cabeçalho ms-diagnostics) que é anexado a uma mensagem SIP, enquanto a cabeçalho de Diagnóstico fornece uma descrição da ID de diagnóstico. O relatório também pode conter detalhes importantes para a solução de problemas e que são conhecidos pelo componente de relatório. Por exemplo:
  
- O código de motivo fornecido pelo gateway da PSTN que gerou a falha. Quando uma chamada de saída falha na rede PSTN, um código de causa ISUP (parte de usuário ISDN, em inglês) é gerado automaticamente. Por exemplo, um gateway PSTN pode enviar o código de causa 34 para indicar que nenhum circuito ou canal estava disponível para completar a chamada.
    
- FQDN do par, porta e erros de Winsock para falhas de conectividade.
    
- Nomes pesquisados por falhas de resolução de DNS. A resolução DNS ocorre sempre que um cliente entra em contato com um servidor de nomes e solicita o endereço IP que corresponde ao nome de dispositivo especificado.
    
## <a name="accessing-the-diagnostic-report"></a>Acessando o relatório de diagnósticos

O Relatório de Diagnóstico pode ser acessado clicando na métrica Relatório de Diagnóstico (Detalhes) no Relatório de Detalhes de Sessão Ponto [a](peer-to-peer-session-detail-report.md) Ponto no Skype for Business Server ou no Relatório de Detalhes da Conferência.
  
## <a name="filters"></a>Filtros

Nenhum. Não é possível filtrar o Relatório de Diagnóstico.
  
## <a name="metrics"></a>Métrica

A tabela a seguir lista as informações fornecidas no Relatório de Diagnóstico para cada sessão.
  
**Métricas do Relatório de Diagnóstico**

|**Name**|**É possível classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Hora do relatório** <br/> |Não  <br/> |Data e hora do registro do relatório.  <br/> |
|**Código da resposta** <br/> |Não  <br/> |Código da resposta SIP enviado quando a sessão falhou.  <br/> |
|**Tipo de solicitação** <br/> |Não  <br/> |Tipo de solicitação SIP que falhou. Por exemplo, CONVIDAR, ATÉ LOGO ou SERVIÇO.  <br/> |
|**Fonte** <br/> |Não  <br/> |Origem do erro.  <br/> |
|**URI do usuário de origem** <br/> |Não  <br/> |Endereço SIP do usuário que iniciou a sessão.  <br/> |
|**Representante do usuário de origem** <br/> |Não  <br/> |Software usado pelo ponto de extremidade do usuário que iniciou a sessão.  <br/> |
|**ID do Diagnóstico** <br/> |Não  <br/> |Identificador exclusivo (no formato de um cabeçalho ms-diagnostics) anexado a uma mensagem SIP que frequentemente oferece informações úteis para resolução de erros.  <br/> |
|**Tipo de conteúdo** <br/> |Não  <br/> |Tipo de conteúdo de mídia que falhou. Por exemplo, um tipo de conteúdo comum é Application/sdp. SDP (Protocolo de descrição de sessão) é um protocolo padrão de Internet usado para anúncios de sessão, convites de sessão e outras formas de início de sessão multimídia.  <br/> |
|**Aplicativo** <br/> |Não  <br/> |Aplicativo envolvido no erro.  <br/> |
|**URI do usuário de destino** <br/> |Não  <br/> |Endereço SIP do usuário convidado para a sessão.  <br/> |
|**Hora de ingresso de conferência (ms)** <br/> |Não  <br/> |Tempo (em milissegundos) que o usuário precisou para ingressar na conferência.  <br/> |
|**Cabeçalho do diagnóstico** <br/> |Não  <br/> |Descrição do ID de diagnóstico.  <br/> |
   
Uma lista de erros de diagnóstico pode ser encontrada na [página Ms-Diagnostics Header](/openspecs/office_protocols/ms-ocer/f6787b39-0842-43ca-94a2-6afadda5f0a3).
