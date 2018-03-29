---
title: Configurar o Servidor de Interoperabilidade de Vídeo no Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0fde142b-70b1-46c6-b1f9-f9d70115371d
description: 'Resumo: Configure a função de servidor de interoperabilidade de vídeo (VIS) no Skype para Business Server 2015.'
ms.openlocfilehash: 7192135f5822e3086de7533afbdc8492194a3889
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-the-video-interop-server-in-skype-for-business-server-2015"></a>Configurar o Servidor de Interoperabilidade de Vídeo no Skype for Business Server 2015
 
**Resumo:** Configure a função de servidor de interoperabilidade de vídeo (VIS) no Skype para Business Server 2015.
  
 Defina as configurações que o VIS associará troncos de vídeos usando o Windows PowerShell. Uma configuração de tronco de vídeo com escopo global é criada assim que o serviço VIS é instalado. Esta configuração de vídeo é aplicada pelo VIS a todos os troncos que não têm uma configuração de tronco com um escopo mais específico. Observe que a configuração do tronco de vídeo é uma coleção de configurações que pode ser aplicada a troncos de vídeo.
  
## <a name="configure-video-trunk-and-dial-plan"></a>Configurar tronco de vídeo e plano de discagem

Use os seguintes comandos do Windows PowerShell para especificar a configuração do tronco de vídeo e discagem planeja estar associada a trunk(s) recém-definida definidos no documento de topologia entre o VIS e todos os Gateways de vídeo. Todas essas configurações podem ser definidas nos níveis de serviço (Gateway de Vídeo), de site ou global. 
  
Um plano de discagem com escopo global é criado por Skype para implantação de servidor de negócios. Esse plano de discagem é aplicado pelo VIS a todos os troncos que não têm nenhum plano de discagem com escopo mais específico. 
  
### <a name="configure-the-vis-using-windows-powershell"></a>Configurar o VIS usando o Windows PowerShell

1. Crie uma nova configuração de tronco de vídeo (uma coleção de definições) para usar no tronco entre o VIS e CUCM, usando o seguinte cmdlet do Windows PowerShell:
    
   ```
   New-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls $true(or $false)
   ```

    Se houver um tronco existente de vídeo que precisa ser modificado, use o seguinte cmdlet do Windows PowerShell:
    
   ```
   Set-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls  $true(or $false)
   ```

    Para exibir as definições associadas a uma configuração de tronco de vídeo específico, use o seguinte cmdlet do Windows PowerShell:
    
   ```
   Get-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

    Para remover uma configuração de tronco de vídeo específico, use o seguinte cmdlet do Windows PowerShell (Observe que a configuração do tronco globalmente com escopo de vídeo será aplicada se não houver uma configuração de tronco vídeo mais especificamente com escopo para um determinado tronco):
    
   ```
   Remove-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

2. Estabelece um plano de discagem para associar o tronco, usando os seguintes cmdlets do Windows PowerShell:
    
   ```
   New-CsDialPlan -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -SimpleName "TrunkTestDialPlan" 
   New-CsVoiceNormalizationRule -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/SevenDigitRule" -Pattern '^(\d{7})$' -Translation '+1425$1' 
   Get-CsDialPlan -Identity "Service:CUCMVIS1.CUCMInterop.contoso.com"
   Remove-CsVoiceNormalizationRule -Identity  "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/Keep All"
   ```

O comando **Remove-CsVoiceNormalizationRule** é necessário para substituir uma regra padrão que interfira com a interação esperada entre VIS e CUCM.
> [!NOTE]
> [Remove-Csdialplanpara](https://docs.microsoft.com/powershell/module/skype/remove-csdialplan?view=skype-ps) pode ser usado para remover um plano de discagem.
  
Para uma chamada de vídeo tronco SIP de um Gateway de vídeo cujo URI de solicitação contém um número não e. 164, VIS lê o nome do plano de discagem associado ao tronco associado e incluirá o nome do plano de discagem na parte de contexto de telefone do URI de solicitação no convite da que VI S envia para o Front-End. O Aplicativo de Conversão no Front-End extrai e aplica as regras de normalização associadas ao plano plano de discagem ao URI de Solicitação.
## <a name="trunk-configuration-options"></a>Opções de configuração de tronco

Cmdlets do Windows PowerShell para configuração de tronco de vídeo mencionado anteriormente são novo para o Skype para Business Server 2015. As configurações associadas ao tronco de vídeo demandam uma breve explicação.
  
 **GatewaySendsRtcpForActiveCalls** Este parâmetro determina se os pacotes RTCP são enviados do VTC para o VIS chamadas ativas. Nesse contexto, uma chamada ativa é aquela na qual a mídia tem permissão para fluir em pelo menos uma direção. Se GatewaySendsRtcpForActiveCalls estiver configurado como Verdadeiro, o VIS poderá encerrar uma chamada se não receber pacotes RTCP dento de um intervalo acima de 30 segundos. O padrão é **Verdadeiro**.
  
 **GatewaySendsRtcpForCallsOnHold** Esse parâmetro determina se os pacotes RTCP continuarão a ser enviados através do tronco para chamadas que tiverem sido colocadas em espera e esperados sem pacotes de mídia flua em ambas as direções. O VIS poderá encerrar a chamada se não houver nenhum pacote RTCP fluindo do VTC para o VIS enquanto a chamada está em espera. O padrão é **Verdadeiro**. Quando o protocolo SIPTransport é configurado para TCP, essa configuração é ignorada.
  
 **EnableMediaEncryptionForSipOverTls** Este parâmetro habilita ou desabilita o SRTP para a mídia quando o protocolo SIPTransport estiver definido como TLS. O padrão é **Verdadeiro**. Quando o protocolo SIPTransport é configurado para TCP, essa configuração é ignorada.
  
 **EnableSessionTimer** Este parâmetro habilita ou desabilita os cronômetros de sessão no lado VIS para cada caixa de diálogo SIP associado ao tronco SIP vídeo. A padrão é **Falso**.
  
 **ForwardErrorCorrectionType** Esse parâmetro é usado para determinar se encaminhar erro correção (FEC) de fluxos de vídeo deve ser aplicada no trecho entre o servidor de interoperabilidade de vídeo e um Gateway de vídeo. Configuração ForwardErrorCorrectionType como "None" desativa FEC entre VIS e Gateway/VTC de vídeo. Definindo ForwardErrorCorrectionType "Cisco" habilita o FEC compatível com os Gateways de vídeo pela Cisco, como Cisco Unified Communications Manager (CUCM). O padrão é **Nenhum**.
  
## <a name="see-also"></a>Consulte também

#### 

[Configurar CUCM para interoperação com Skype para Business Server 2015](configure-cucm-for-interoperation.md)

