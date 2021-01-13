---
title: Planejar o Servidor de Interop de Vídeo no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
f1.keywords:
- ms.lync.plan.VideoInterop
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4a8daf23-77ba-428b-bcbc-161f6af52c11
description: 'Resumo: Revise este tópico ao planejar a integração do Skype for Business Server com dispositivos de teleconferência de terceiros.'
ms.openlocfilehash: c14d92042922f30ca5dd43acce12d11ef50a8683
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831941"
---
# <a name="plan-for-video-interop-server-in-skype-for-business-server"></a>Planejar o Servidor de Interop de Vídeo no Skype for Business Server
 
**Resumo:** Revise este tópico ao planejar a integração do Skype for Business Server com dispositivos de teleconferência de terceiros.
  
O Skype for Business Server agora permite que você se integre a determinadas soluções de VTC (Video Teleconferencing System) de terceiros. A nova função de servidor que habilita essa interoperabilidade de videoconferência é o Servidor de Interoperabilidade de Vídeo (VIS), atualmente implementado como uma função de servidor autônoma disponível apenas para instalações locais. Um VIS atua como intermediário entre um sistema de teleconferência de terceiros e uma implantação do Skype for Business Server. Para esta versão, o VIS concentra-se na interoperabilidade com sistemas de vídeo da Cisco/Tandberg. Revise este artigo para determinar se esse recurso deve ser usado em sua instalação do Skype for Business Server.
  
## <a name="device-interoperability"></a>Interoperabilidade do dispositivo

A interoperação é testada e tem suporte com os VTCs da Cisco que se registram com o Cisco Unified Communications Manager (CallManager ou CUCM) versão 10.5 e troncos SIP TCP definidos entre o CUCM e o VIS.
  
Os VTCs atualmente suportados são:
  
- Cisco C40
    
- Cisco C60
    
- Cisco C90
    
- Cisco MX200
    
- Cisco MX300
    
- Cisco DX80
    
- Cisco EX60
    
- Cisco EX90
    
- Cisco SX20
    
> [!NOTE]
>  A versão TC7.0.0 ou superior de software da Cisco é necessária nesses sistemas para que a integração com o Skype for Business Server funcione conforme o esperado.
  
## <a name="sip-trunks"></a>Troncos SIP

O Servidor de Interop de Vídeo funciona no modo de tronco SIP, onde os VTCs continuam a se registrar com a infraestrutura da Cisco existente, por exemplo, o Cisco Call Manager (CUCM). Um tronco SIP de vídeo é definido entre o CUCM e o VIS para que as chamadas possam ser roteados entre os dois sistemas. Somente as chamadas pelo tronco SIP do VTC para o VIS são suportadas. Assim, os VTCs podem discar para uma conferência do Skype for Business (discando o número de telefone associado ao Atendente Automatizado de Chamadas), mas não podem ser arrastados e arrastados para a conferência.
  
![Diagrama do VIS no SfB](../media/87753af5-b1d9-4107-9216-fde45a1af197.png)
  
## <a name="features"></a>Recursos

Esta função de servidor fornece:
  
- Conversão entre os formatos H.264 usados por sistemas de vídeo de terceiros e a implantação do Skype for Business Server.
    
- Conversão de um único fluxo de vídeo em uma determinada resolução de um VTC em vários fluxos simulcast de diferentes resoluções para uso na implantação do Skype for Business Server. Esses fluxos podem ser enviados para o AVMCU e, em seguida, para os pontos de extremidade do Skype for Business Server e outros sistemas de vídeo que solicitaram resoluções diferentes. Essa conversão também é usada quando o sistema de vídeo de terceiros está envolvido em uma chamada de conferência A/V do Skype for Business. Depois que o limite de transcodificação for atingido em um determinado servidor VIS, todas as solicitações a seguir para resoluções diferentes receberão apenas um fluxo com a resolução mais baixa. 
    
- Suporte para um tronco SIP de vídeo entre o gateway CUCM e um Servidor de Interop de Vídeo do Skype for Business Server; Os VTCs continuam a se registrar no gateway da Cisco e iniciam chamadas para a implantação do Skype for Business por meio do gateway. As chamadas são roteados do gateway para o Skype for Business Video Interop Server pelo tronco SIP de vídeo.
    
- Suporte para um usuário em uma sala de conferência com um sistema de vídeo com suporte para discar desse sistema para ingressar em uma conferência aberta ou fechada. Essa chamada atravessará o tronco SIP de vídeo.
    
- Suporte para um usuário em uma sala de conferência com um sistema de vídeo com suporte para chamar um cliente do Skype for Business. A chamada atravessará o tronco SIP.
    
- Suporte para o controle de chamadas médias do lado do Skype for Business Server ou do sistema VTC com suporte para chamadas ponto a ponto e multiponto, incluindo mudo/mudo de áudio, pausar/retomar vídeo, bloquear vídeo e chamada de espera/não espera.
    
## <a name="known-limitations"></a>Limitações conhecidas

Esta função de servidor tem as seguintes limitações:
  
- Não há suporte para novas chamadas da implantação do Skype for Business para os VTCs pelo tronco SIP de vídeo. . Isso significa que apenas novas chamadas dos VTCs para a implantação do Skype for Business são suportadas pelo tronco SIP de vídeo. A presença para o sistema de vídeo suportado não estará disponível pelo tronco SIP de vídeo para o VIS. 
    
- Somente um pool de VIS autônomo terá suporte para o modo de tronco SIP de vídeo.
    
-  TLS + SRTP ou TCP + RTP serão suportados para comunicações entre o VTC e o VIS sobre o tronco SIP de vídeo.
    
- Não há suporte para compartilhamento de aplicativos. Um usuário do Skype for Business na sala de conferência precisa ingressar na conferência do Skype for Business (por exemplo, por meio de um laptop) e exibir as telas de compartilhamento de aplicativos em um dos monitores gratuitos na sala de conferência não associados ao VTC.
    
- Não há suporte para a capacidade de um VTC ingressar em uma reunião federada via VIS.
    
- Não há suporte para a capacidade de um VTC ingressar em uma reunião online via VIS.
    
- Chamadas de um VTC para a PSTN via VIS não são suportadas.
    
- Chamadas do PSTN para um VTC via VIS não são suportadas.
    
## <a name="resiliency-mechanisms"></a>Mecanismos de resiliência
<a name="resiliency"> </a>

O VIS dá suporte a chamadas de entrada de um CUCM que são transportada sobre um tronco SIP de vídeo. É possível perder a conectividade upstream ou downstream, portanto, para uma resiliência robusta, considere ambas as possibilidades:
  
1. **Failover do pool do VIS** Se o pool de VIS principal que o gateway de vídeo aponta estiver inostado, a recuperação será possível se o gateway de vídeo tiver troncos definidos para dois (ou mais) pools de VIS. Se o gateway de vídeo determinar que não pode fazer chamadas para o pool vis primário, ele simplesmente encaminha as chamadas para um pool de VIS secundário.
    
     ![Diagrama de failover do pool do VIS](../media/390d93c3-e132-4bbd-8d5a-c70ead9cdfad.png)
  
    Um pool de VIS específico pode ter troncos para vários gateways, mas normalmente um gateway específico não pode ter troncos para vários pools DE VIS, portanto, um truque precisa ser feito para dar suporte a esse failover: definir 2 FDQNs no DNS que são resolvidos para o mesmo endereço IP de um gateway de vídeo. Represente cada FQDN como um gateway de vídeo separado no Documento de Topologia onde cada gateway de vídeo tem um tronco para um pool de VIS diferente, e a recuperação agora é possível. (Se o TLS for usado, os vários nomes precisarão estar no SAN do certificado de gateway de vídeo.)
    
    > [!NOTE]
    > O VIS só permite chamadas de entrada de gateways configurados no Documento de Topologia. 
  
2. **Failover de Front End** Se um pool de VIS receber uma chamada do CUCM, mas não puder alcançar seu Registrador primário de próximo salto ou pool de Front-End, as chamadas serão roteados para um pool de front-end de backup.
    
     ![Diagrama de failover de front-end](../media/6ddc08ec-4708-4c23-9e77-0f88899a2a96.png)
  
    O VIS acompanhará o status de seu pool de Front-End principal e seu pool de Front-End de backup (a configuração é encontrada na configuração de backup do serviço Registrador no Documento de Topologia). Ele envia as sondagens de Opções uma vez por minuto para ambos os pools e, se houver cinco falhas consecutivas, o VIS assumirá que um pool de Front End específico está ino mesmo. Se o pool de front-end primário estiver marcado como inostado e houver um backup configurado disponível, o VIS enviará novas chamadas do gateway para o pool de front-end de backup. Depois que o pool de front-end primário voltar, o VIS será retomado usando o pool de front-end primário para novas chamadas.
    
    O VIS também implementará um temporizador de 10 segundos para chamadas do tronco SIP de vídeo. Se o pool de Front End do próximo salto primário tiver sido usado para uma chamada do tronco SIP de vídeo e o pool de Front End do próximo salto principal não responder com alguma mensagem SIP (incluindo 100 Tentando) para o Convite enviado a ele dentro desse valor de timer, o proxy de próximo salto de backup para a chamada deverá ser tentado se configurado. 
    
    > [!NOTE]
    > Se o próximo salto de backup for tentado primeiro, o primário não será tentado em seguida. 
  
    O administrador também pode usar o comando de failover do Windows PowerShell para forçar o VIS a usar o pool de front-end de backup, por exemplo, quando a manutenção precisa ser executada no pool de Front-End principal.
    
## <a name="co-existence-of-voice-and-video-trunks-to-the-same-gateway-peer"></a>Co-existência de troncos de voz e vídeo para o mesmo par de gateway
<a name="resiliency"> </a>

O Skype for Business Server oferece suporte para troncos SIP de voz e vídeo usarem o mesmo par de gateway. Portanto, a mesma implantação do CUCM poderia ter troncos SIP de voz para o Servidor de Mediação e troncos SIP de vídeo para VIS.
  
- Um Gateway PSTN precisará ser definido com um FQDN específico no Documento de Topologia para os troncos SIP de voz.
    
- O ponto para o Gateway PSTN será o Servidor de Mediação.
    
- Vários troncos de voz podem ser definidos, abrangendo desde um Gateway PSTN até vários pools de Servidor de Mediação, se necessário.
    
- Um Gateway de Vídeo precisará ser definido no Documento de Topologia para o tronco SIP de vídeo com o mesmo FQDN que para o Gateway PSTN.
    
- O par para o Gateway de Vídeo será VIS.
    
- Um único tronco de vídeo pode ser definido de um Gateway de Vídeo para um pool vis específico.
    
- O CUCM precisará ser configurado para rotear corretamente as chamadas pelo tronco de voz versus o tronco de vídeo. Por exemplo, um prefixo de discagem especial pode ser usado ao discar do VTC; O CUCM pode associar esse prefixo de discagem a chamadas para VIS, e as regras de conversão apropriadas retirariam esse prefixo do SIP Invite para VIS.
    
## <a name="co-existence-of-vis-in-the-skype-for-business-release-with-previous-releases-of-lync"></a>Co-existência do VIS na versão do Skype for Business com versões anteriores do Lync
<a name="resiliency"> </a>

O VIS só pode ser implantado como parte da implantação do Skype for Business. Ele pode interoperar com conferências e clientes do Lync 2013 que fazem parte de uma implantação existente; Nesses casos, o pool de VIS precisará fazer parte de uma implantação do Skype for Business que inclua um pool de Registrador/FE que seja o próximo salto para o pool de VIS.
  
O VIS não dá suporte à transcodificação entre RTV e H.264. Não há interoperabilidade de vídeo entre clientes pré-Lync 2013 e participantes do VTC em uma conferência.
  
Ter clientes pré-Lync 2013 em uma conferência fará com que clientes móveis enviem usando RTV resultando em VTCs não recebendo vídeo quando o cliente móvel se torna o alto-falante dominante.
  
Para que o Lync 2013 funcione corretamente com o VIS que faz parte de uma implantação do Skype for Business, o Lync 2013 precisa da aplicação da cu apropriada que atualiza o cliente do Lync 2013, CAA e AVMCU para trabalhar com o VIS.
  
A interoperabilidade do VIS com clientes de área de trabalho do Lync 2013 e do Skype for Business foi testada e tem suporte.
  
Interoperabilidade do VIS com não desktop (Android, Ipad, Iphone, Windows Phone, LMX, etc.) Os clientes do Skype for Business disponíveis na Loja de Aplicativos aplicável no momento da versão do VIS foram testados e têm suporte.
  
## <a name="recovery-from-packet-loss-via-fec"></a>Recuperação da perda de pacotes via FEC
<a name="resiliency"> </a>

O FEC pode ser ligado para auxiliar na recuperação da perda de pacotes. Se estiver ligado, 50% mais largura de banda de vídeo será usada na direção de VIS para VTC.
  
## <a name="vis-sizing-and-transcoding-costs"></a>Custos de redução e transcodificação do VIS
<a name="resiliency"> </a>

A transcodificação dos fluxos de vídeo único do Cisco VTC para vários fluxos simulcast usa a capacidade da CPU. Aproximadamente 16 VTCs podem ter seu vídeo transcodificado (supondo que um fluxo de vídeo de 720p de cada VTC seja transcodificado em 3 fluxos simulcast separados em 720p, 360p e 180p) em um único VIS em execução no equivalente à plataforma FE recomendada do Lync 2013. Se a Transcodificação estiver desligada, isso economizará na CPU do VIS. No entanto, a imagem de vídeo solicitada pelo VIS do VTC será a resolução comum mais baixa para atender a todos os receptores no lado do Skype for Business. Observe que, mesmo com a transcodificação desativada, a transcodificação pode ser ativada quando os clientes do Skype for Business solicitam determinadas resoluções baixas que os VTCs não podem enviar.
  
## <a name="call-distribution-from-the-video-gateway-to-vis"></a>Distribuição de chamada do Gateway de Vídeo para VIS
<a name="resiliency"> </a>

A distribuição é realizada por meio de um dos mecanismos de distribuição do CUCM:
  
- Dinamicamente usando DNS.
    
- No lado do CUCM, você pode definir troncos individuais, onde cada tronco termina em um servidor diferente no pool de VIS. O CUCM encaminhará chamadas entre os diferentes troncos.
    
## <a name="no-hybrid-interoperability"></a>Sem interoperabilidade híbrida
<a name="resiliency"> </a>

O suporte para VTCs que participam de reuniões online por meio do VIS local não faz parte do Skype for Business.
  
## <a name="no-federation-support"></a>Sem suporte de federação
<a name="resiliency"> </a>

O suporte para VTCs que participam de reuniões federadas via VIS não faz parte do Skype for Business.
  
## <a name="see-also"></a>Confira também
<a name="resiliency"> </a>

[Implantar o Servidor de Interop de Vídeo no Skype for Business Server](../deploy/deploy-video-interop-server/deploy-video-interop-server.md)
