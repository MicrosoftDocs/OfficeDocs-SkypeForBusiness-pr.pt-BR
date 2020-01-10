---
title: Configurar o servidor de interoperabilidade de vídeo no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0fde142b-70b1-46c6-b1f9-f9d70115371d
description: 'Resumo: Configure a função do servidor de interoperabilidade de vídeo (VIS) no Skype for Business Server.'
ms.openlocfilehash: fb9dc36bcf2f1a6f1346705f74dd3cf2844a973c
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003051"
---
# <a name="configure-the-video-interop-server-in-skype-for-business-server"></a>Configurar o servidor de interoperabilidade de vídeo no Skype for Business Server
 
**Resumo:** Configurar a função servidor de interoperabilidade de vídeo (VIS) no Skype for Business Server.
  
 Defina as configurações que o VIS associará aos troncos de vídeo usando o Windows PowerShell. Uma configuração de tronco de vídeo com escopo global é criada assim que o serviço VIS é instalado. Esta configuração de vídeo é aplicada pelo VIS a todos os troncos que não têm uma configuração de tronco com um escopo mais específico. Observe que a configuração do tronco de vídeo é uma coleção de configurações que pode ser aplicada a troncos de vídeo.
  
## <a name="configure-video-trunk-and-dial-plan"></a>Configurar tronco de vídeo e plano de discagem

Use os seguintes comandos do Windows PowerShell para especificar a configuração de tronco de vídeo e o plano de discagem a serem associados ao (s) tronco (s) recém-definido (s) definidos no documento de topologia entre o VIS e todos os gateways de vídeo. Todas essas configurações podem ser definidas nos níveis de serviço (Gateway de Vídeo), de site ou global. 
  
Um plano de discagem com escopo global é criado pela implantação do Skype for Business Server. Esse plano de discagem é aplicado pelo VIS a todos os troncos que não têm nenhum plano de discagem com escopo mais específico. 
  
### <a name="configure-the-vis-using-windows-powershell"></a>Configurar o VIS usando o Windows PowerShell

1. Crie uma nova configuração de tronco de vídeo (um conjunto de configurações) para usar no tronco entre o VIS e o Gerenciador de comunicações unificadas da Cisco (CallManager ou CUCM), usando o seguinte cmdlet do Windows PowerShell:
    
   ```powershell
   New-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls $true(or $false)
   ```

    Se houver um tronco de vídeo existente que precisa ser modificado, use o seguinte cmdlet do Windows PowerShell:
    
   ```powershell
   Set-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls  $true(or $false)
   ```

    Para exibir as configurações associadas a uma configuração de tronco de vídeo específica, use o seguinte cmdlet do Windows PowerShell:
    
   ```powershell
   Get-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

    Para remover uma configuração de tronco de vídeo específica, use o seguinte cmdlet do Windows PowerShell (Observe que a configuração de troncos de vídeo globalmente em escopo será aplicada se não houver uma configuração de tronco de vídeo com o escopo mais especificamente para um tronco específico):
    
   ```powershell
   Remove-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

2. Estabeleça um plano de discagem para associar ao tronco usando os seguintes cmdlets do Windows PowerShell:
    
   ```powershell
   New-CsDialPlan -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -SimpleName "TrunkTestDialPlan" 
   New-CsVoiceNormalizationRule -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/SevenDigitRule" -Pattern '^(\d{7})$' -Translation '+1425$1' 
   Get-CsDialPlan -Identity "Service:CUCMVIS1.CUCMInterop.contoso.com"
   Remove-CsVoiceNormalizationRule -Identity  "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/Keep All"
   ```

O comando **Remove-CsVoiceNormalizationRule** é necessário para substituir uma regra padrão que interfira com a interação esperada entre VIS e CUCM.
> [!NOTE]
> [Remove-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-csdialplan?view=skype-ps) pode ser usado para remover um plano de discagem.
  
Para uma chamada de tronco SIP de vídeo de um gateway de vídeo cujo URI de solicitação contém um número que não seja E. 164, VIS lerá o nome do plano de discagem associado ao tronco associado e incluirá o nome do plano de discagem na parte de contexto do telefone do URI de solicitação no convite que o VI S envia para o front-end. O Aplicativo de Conversão no Front-End extrai e aplica as regras de normalização associadas ao plano plano de discagem ao URI de Solicitação.
## <a name="trunk-configuration-options"></a>Opções de configuração de tronco

Os cmdlets do Windows PowerShell para configuração de troncos de vídeo mencionados anteriormente eram novos no Skype for Business Server 2015. As configurações associadas ao tronco de vídeo demandam uma breve explicação.
  
 **GatewaySendsRtcpForActiveCalls** Esse parâmetro determina se os pacotes RTCP são enviados do VTC para o VIS para chamadas ativas. Nesse contexto, uma chamada ativa é aquela na qual a mídia tem permissão para fluir em pelo menos uma direção. Se GatewaySendsRtcpForActiveCalls estiver configurado como Verdadeiro, o VIS poderá encerrar uma chamada se não receber pacotes RTCP dento de um intervalo acima de 30 segundos. O padrão é **Verdadeiro**.
  
 **GatewaySendsRtcpForCallsOnHold** Esse parâmetro determina se os pacotes RTCP continuam a ser enviados pelo tronco para chamadas que foram colocadas em espera, e que nenhum pacote de mídia deve fluir em qualquer direção. O VIS poderá encerrar a chamada se não houver nenhum pacote RTCP fluindo do VTC para o VIS enquanto a chamada está em espera. O padrão é **Verdadeiro**. Quando o protocolo SIPTransport é configurado para TCP, essa configuração é ignorada.
  
 **EnableMediaEncryptionForSipOverTls** Esse parâmetro habilita ou desabilita o SRTP para mídia quando o protocolo SIPTransport é definido como TLS. O padrão é **Verdadeiro**. Quando o protocolo SIPTransport é configurado para TCP, essa configuração é ignorada.
  
 **EnableSessionTimer** Esse parâmetro habilita ou desabilita os temporizadores de sessão no lado VIS para cada caixa de diálogo SIP associada ao tronco SIP de vídeo. A padrão é **Falso**.
  
 **ForwardErrorCorrectionType** Esse parâmetro é usado para determinar se a aplicação de correção de erros de encaminhamento (FEC) para fluxos de vídeo deve ser aplicada no trecho entre o servidor de interoperabilidade de vídeo e um gateway de vídeo. A configuração de ForwardErrorCorrectionType como "nenhum" desativa o FEC entre VIS e o gateway de vídeo/VTC. A configuração de ForwardErrorCorrectionType para "Cisco" habilita a FEC compatível com gateways de vídeo pela Cisco, como o Gerenciador de comunicações unificadas da Cisco (CUCM). O padrão é **Nenhum**.
  
## <a name="see-also"></a>Confira também

[Configurar o CUCM para interoperação com o Skype for Business Server](configure-cucm-for-interoperation.md)
