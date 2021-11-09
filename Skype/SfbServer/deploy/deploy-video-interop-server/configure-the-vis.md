---
title: Configurar o Servidor de Interop de Vídeo Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 0fde142b-70b1-46c6-b1f9-f9d70115371d
description: 'Resumo: Configure a função Vis (Servidor de Interop de Vídeo) no Skype for Business Server.'
ms.openlocfilehash: 4148cf404fba4718f56c3c8db7ffe180881b3ae7
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60835809"
---
# <a name="configure-the-video-interop-server-in-skype-for-business-server"></a>Configurar o Servidor de Interop de Vídeo Skype for Business Server
 
**Resumo:** Configure a função VIS (Video Interop Server) no Skype for Business Server.
  
 Configure as configurações que o VIS associará aos troncos de vídeo usando Windows PowerShell. Uma configuração de tronco de vídeo com escopo global é criada depois que o serviço VIS é instalado. Essa configuração de tronco de vídeo é aplicada pelo VIS a todos os troncos que não têm configuração de tronco de vídeo com um escopo mais específico. Observe que a configuração do tronco de vídeo é uma coleção de configurações aplicáveis aos troncos de vídeo.
  
## <a name="configure-video-trunk-and-dial-plan"></a>Configurar o tronco de vídeo e o plano de discagem

Use os comandos Windows PowerShell a seguir para especificar a configuração do tronco de vídeo e o plano de discagem a serem associados aos troncos recém-definidos definidos no Documento de Topologia entre o VIS e todos os Gateways de Vídeo. Todas essas configurações podem ser definidas nos níveis Global, Site ou Service (Video Gateway). 
  
Um plano de discagem com escopo global é criado por Skype for Business Server implantação. Esse plano de discagem é aplicado pelo VIS a todos os troncos que não têm nenhum plano de discagem com escopo mais específico. 
  
### <a name="configure-the-vis-using-windows-powershell"></a>Configurar o VIS usando Windows PowerShell

1. Crie uma nova configuração de tronco de vídeo (uma coleção de configurações) a ser usada no tronco entre o VIS e o Cisco Unified Communications Manager (CallManager ou CUCM), usando o seguinte cmdlet Windows PowerShell:
    
   ```powershell
   New-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls $true(or $false)
   ```

    Se houver um tronco de vídeo existente que precise ser modificado, use o seguinte cmdlet Windows PowerShell:
    
   ```powershell
   Set-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls  $true(or $false)
   ```

    Para exibir as configurações associadas a uma configuração de tronco de vídeo específica, use o seguinte cmdlet Windows PowerShell:
    
   ```powershell
   Get-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

    Para remover uma configuração específica de tronco de vídeo, use o seguinte cmdlet Windows PowerShell (observe que a configuração do tronco de vídeo com escopo global será aplicada se não houver uma configuração de tronco de vídeo mais especificamente com escopo para um tronco específico):
    
   ```powershell
   Remove-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

2. Estabeleça um plano de discagem para associar ao tronco, usando os seguintes cmdlets Windows PowerShell:
    
   ```powershell
   New-CsDialPlan -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -SimpleName "TrunkTestDialPlan" 
   New-CsVoiceNormalizationRule -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/SevenDigitRule" -Pattern '^(\d{7})$' -Translation '+1425$1' 
   Get-CsDialPlan -Identity "Service:CUCMVIS1.CUCMInterop.contoso.com"
   Remove-CsVoiceNormalizationRule -Identity  "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/Keep All"
   ```

O **comando Remove-CsVoiceNormalizationRule** é necessário para substituir uma regra padrão que interferirá na interação esperada do VIS e do CUCM.
> [!NOTE]
> [Remove-CsDialPlan](/powershell/module/skype/remove-csdialplan?view=skype-ps) pode ser usado para remover um plano de discagem.
  
Para uma chamada de tronco SIP de vídeo de um Gateway de Vídeo cujo URI de solicitação contém um número não E.164, o VIS lerá o nome do plano de discagem associado ao tronco associado e incluirá o nome do plano de discagem na parte de contexto de telefone do URI de solicitação no Convite que o VIS envia para o Front-End. Em seguida, o Aplicativo de Tradução no Front-End extrai e aplica as regras de normalização associadas ao plano de discagem ao URI de solicitação.
## <a name="trunk-configuration-options"></a>Opções de configuração de tronco

Os Windows PowerShell cmdlets de configuração de tronco de vídeo mencionados anteriormente eram novos para Skype for Business Server 2015. As configurações associadas à configuração do tronco de vídeo exigem uma breve explicação.
  
 **GatewaySendsRtcpForActiveCalls** Este parâmetro determina se os pacotes RTCP são enviados do VTC para o VIS para chamadas ativas. Nesse contexto, uma chamada ativa é uma chamada na qual a mídia pode partir em pelo menos uma direção. Se GatewaySendsRtcpForActiveCalls estiver definido como True, o VIS poderá encerrar uma chamada se não receber pacotes RTCP por um período superior a 30 segundos. O padrão é **True**.
  
 **GatewaySendsRtcpForCallsOnHold** Este parâmetro determina se os pacotes RTCP continuam a ser enviados pelo tronco para chamadas que foram colocadas em espera e nenhum pacote de mídia deve fluir em qualquer direção. O VIS pode encerrar a chamada, se não houver pacotes RTCP fluindo do VTC para o VIS enquanto a chamada estiver em Espera. O padrão é **True**. Quando o protocolo SIPTransport é definido como TCP, essa configuração é ignorada.
  
 **EnableMediaEncryptionForSipOverTls** Esse parâmetro habilita ou desabilita o SRTP para mídia quando o protocolo SIPTransport é definido como TLS. O padrão é **True**. Quando o protocolo SIPTransport é definido como TCP, essa configuração é ignorada.
  
 **EnableSessionTimer** Esse parâmetro habilita ou desabilita timers de sessão no lado do VIS para cada caixa de diálogo SIP associada ao tronco SIP de vídeo. O padrão é **False**.
  
 **ForwardErrorCorrectionType** Esse parâmetro é usado para determinar se a Correção de Erro de Encaminhamento (FEC) para fluxos de vídeo deve ser aplicada na etapa entre o Servidor de Interop de Vídeo e um Gateway de Vídeo. Definir ForwardErrorCorrectionType como "None" desliga o FEC entre VIS e Gateway de Vídeo/VTC. Definir ForwardErrorCorrectionType como "Cisco" habilita o FEC compatível com gateways de vídeo pela Cisco, como o Cisco Unified Communications Manager (CUCM). O padrão é **None**.
  
## <a name="see-also"></a>Confira também

[Configurar o CUCM para Interoperação com Skype for Business Server](configure-cucm-for-interoperation.md)