---
title: Relatório de Diagnósticos no Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b389dbd9-f2e8-4184-93d0-2e504796ac16
description: 'Resumo: Saiba mais sobre o relatório de diagnóstico no Skype para Business Server 2015.'
ms.openlocfilehash: 86639f5687cb6d19ff18c9aafb869a74fb777113
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="diagnostic-report-in-skype-for-business-server-2015"></a>Relatório de Diagnósticos no Skype for Business Server 2015
 
**Resumo:** Saiba mais sobre o relatório de diagnóstico no Skype para Business Server 2015.
  
O Relatório de diagnóstico fornece diagnósticos e informações para a solução de problemas de uma sessão com falha. Essas informações incluem a ID de diagnóstico e o cabeçalho de Diagnóstico que foram importados quando a sessão falhou. A ID de diagnóstico é um identificador exclusivo (na forma de um cabeçalho ms-diagnostics) que é anexado a uma mensagem SIP, enquanto a cabeçalho de Diagnóstico fornece uma descrição da ID de diagnóstico. O relatório também pode conter detalhes importantes para a solução de problemas e que são conhecidos pelo componente de relatório. Por exemplo:
  
- O código de motivo fornecido pelo gateway da PSTN que gerou a falha. Quando uma chamada de saída falha na rede PSTN, um código de causa ISUP (parte de usuário ISDN, em inglês) é gerado automaticamente. Por exemplo, um gateway PSTN pode enviar o código de causa 34 para indicar que nenhum circuito ou canal estava disponível para completar a chamada.
    
- FQDN do par, porta e erros de Winsock para falhas de conectividade.
    
- Nomes pesquisados por falhas de resolução de DNS. A resolução DNS ocorre sempre que um cliente entra em contato com um servidor de nomes e solicita o endereço IP que corresponde ao nome de dispositivo especificado.
    
## <a name="accessing-the-diagnostic-report"></a>Acessando o relatório de diagnósticos

O relatório de diagnóstico pode ser acessado clicando na métrica relatório de diagnóstico (detalhe) no [relatório de detalhes de sessão ponto a ponto no Skype para Business Server 2015](peer-to-peer-session-detail-report.md) ou o relatório de detalhe da conferência.
  
## <a name="filters"></a>Filtros

Nenhum. Não é possível filtrar o Relatório de Diagnóstico.
  
## <a name="metrics"></a>Métricas

A tabela a seguir lista as informações fornecidas no Relatório de Diagnóstico para cada sessão.
  
**Métricas do relatório de diagnóstico**

|**Nome**|**Você pode classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Hora do relatório** <br/> |Não  <br/> |Data e hora do registro do relatório.  <br/> |
|**Código da resposta** <br/> |Não  <br/> |Código da resposta SIP enviado quando a sessão falhou.  <br/> |
|**Tipo de solicitação** <br/> |Não  <br/> |Tipo de solicitação SIP que falhou. Por exemplo, CONVIDAR, ATÉ LOGO ou SERVIÇO.  <br/> |
|**Origem** <br/> |Não  <br/> |Origem do erro.  <br/> |
|**URI do usuário de origem** <br/> |Não  <br/> |Endereço SIP do usuário que iniciou a sessão.  <br/> |
|**Representante do usuário de origem** <br/> |Não  <br/> |Software usado pelo ponto de extremidade do usuário que iniciou a sessão.  <br/> |
|**ID do Diagnóstico** <br/> |Não  <br/> |Identificador exclusivo (na forma de um cabeçalho de diagnóstico-ms) anexado a uma mensagem SIP que fornece informações úteis sobre os erros de solução de problemas.  <br/> |
|**Tipo de conteúdo** <br/> |Não  <br/> |Tipo de conteúdo de mídia que falhou. Por exemplo, um tipo de conteúdo comum é Application/sdp. SDP (Protocolo de descrição de sessão) é um protocolo padrão de Internet usado para anúncios de sessão, convites de sessão e outras formas de início de sessão multimídia.  <br/> |
|**Aplicativo** <br/> |Não  <br/> |Aplicativo envolvido no erro.  <br/> |
|**URI do usuário de destino** <br/> |Não  <br/> |Endereço SIP do usuário convidado para a sessão.  <br/> |
|**Hora de ingresso de conferência (ms)** <br/> |Não  <br/> |Tempo (em milissegundos) que o usuário precisou para ingressar na conferência.  <br/> |
|**Cabeçalho do diagnóstico** <br/> |Não  <br/> |Descrição do ID de diagnóstico.  <br/> |
   
Uma lista de erros de diagnósticos pode ser encontrada na [página de cabeçalho Ms-Diagnostics](https://msdn.microsoft.com/en-us/library/gg132446%28v=office.12%29.aspx).
  

