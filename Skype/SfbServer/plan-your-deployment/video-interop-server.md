---
title: Planejar o servidor de interoperabilidade de vídeo no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
f1.keywords:
- NOCSH
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4a8daf23-77ba-428b-bcbc-161f6af52c11
description: 'Resumo: revise este tópico ao planejar a integração do Skype for Business Server com dispositivos de teleconferência de terceiros.'
ms.openlocfilehash: af7618efa0b5f13419be216b37a4f1e7d4065e97
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815559"
---
# <a name="plan-for-video-interop-server-in-skype-for-business-server"></a>Planejar o servidor de interoperabilidade de vídeo no Skype for Business Server
 
**Resumo:** Revise este tópico ao planejar a integração do Skype for Business Server com dispositivos de teleconferência de terceiros.
  
Agora, o Skype for Business Server permite que você se integre com determinadas soluções de VTC (sistema de videoconferências) de terceiros. A nova função de servidor que permite esta interoperabilidade de videoconferência é o servidor de interoperabilidade de vídeo (VIS), que atualmente é implementado como uma função de servidor autônomo disponível somente para instalações locais. Um VIS atua como intermediário entre um sistema de teleconferência de terceiros e uma implantação do Skype for Business Server. Nesta versão, o enfoque do VIS está na interoperabilidade com sistemas de vídeo da Cisco e da Tandberg. Revise este artigo para determinar se esse recurso deve ser usado na instalação do Skype for Business Server.
  
## <a name="device-interoperability"></a>Interoperabilidade de dispositivos

A interoperação é testada e compatível com o registro do Cisco VTCs com o Gerenciador de comunicações unificadas da Cisco (CallManager ou CUCM) versão 10,5 e troncos TCP SIP configurados entre o CUCM e o VIS.
  
Os VTCs atualmente compatíveis são:
  
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
>  A versão TC 7.0.0 ou superior do Cisco software é necessária nesses sistemas para que a integração com o Skype for Business Server funcione conforme o esperado.
  
## <a name="sip-trunks"></a>Troncos SIP

O servidor de interoperabilidade de vídeo funciona no modo de tronco SIP, em que o VTCs continuar a se registrar na infraestrutura da Cisco existente, por exemplo, Cisco Call Manager (CUCM). Define-se um tronco SIP de vídeo entre o CUCM e o VIS, de forma que as chamadas possam ser roteadas entre os dois sistemas. Somente as chamadas pelo tronco SIP feitas pelo VTC são compatíveis. Portanto, o VTCs pode discar para uma conferência do Skype for Business (discando o número de telefone associado ao atendente automatizado de chamada), mas não pode ser arrastado e solto na conferência.
  
![Diagrama de VIS no SfB](../media/87753af5-b1d9-4107-9216-fde45a1af197.png)
  
## <a name="features"></a>Recursos

Esta função de servidor oferece:
  
- Conversão entre os formatos H. 264 usados por sistemas de vídeo de terceiros e a implantação do Skype for Business Server.
    
- Conversão de um único fluxo de vídeo em uma determinada resolução de um VTC em vários fluxos simulcast de diferentes resoluções para uso na implantação do Skype for Business Server. Esses fluxos podem ser enviados para o AVMCU e, em seguida, para pontos de extremidade do Skype for Business Server e outros sistemas de vídeo que solicitaram resoluções diferentes. Essa conversão também é usada quando o sistema de vídeo de terceiros está envolvido em uma chamada em conferência do Skype for Business A/V. Quando o limite de transcodificação for atingido em um determinado servidor VIS, quaisquer solicitações a seguir para resoluções diferentes só receberão um fluxo com a resolução mais baixa. 
    
- Suporte para um tronco de vídeo SIP entre o gateway do CUCM e um servidor de interoperabilidade de vídeo do Skype for Business Server; O VTCs continuará a se registrar com o gateway Cisco e iniciará chamadas para a implantação do Skype for Business por meio do gateway. As chamadas são roteadas do gateway para o servidor de interoperabilidade de vídeo do Skype for Business por meio do tronco SIP de vídeo.
    
- Suporte a um usuário em uma sala de conferência com sistema de vídeo compatível para fazer a discagem por esse sistema e, assim, entrar em uma conferência aberta ou fechada. Essa chamada atravessará o tronco SIP de vídeo.
    
- Suporte para um usuário em uma sala de conferência com um sistema de vídeo com suporte para chamar um cliente Skype for Business. Essa chamada atravessará o tronco SIP.
    
- Suporte para o controle de chamada mid do lado do servidor do Skype for Business ou do sistema VTC com suporte para chamadas ponto a ponto e multiponto, incluindo áudio de mudo/desativação, vídeo de pausa/retomada, vídeo de cadeado e chamada em espera/sem retenção.
    
## <a name="known-limitations"></a>Limitações conhecidas

Esta função de servidor tem as seguintes limitações:
  
- Não há suporte para as novas chamadas da implantação do Skype for Business para o VTCs sobre o tronco de vídeo SIP. . Isso significa que apenas novas chamadas do VTCs para a implantação do Skype for Business são compatíveis com o tronco SIP de vídeo. A presença do sistema de vídeo com suporte não estará disponível no tronco SIP de vídeo para o VIS. 
    
- Haverá suporte a somente um pool autônomo de VIS para o modo de tronco SIP de vídeo.
    
-  Haverá suporte para TLS + SRTP ou TCP + RTP para comunicações entre o VTC e o VIS sobre o tronco SIP de vídeo.
    
- Não há suporte para compartilhamento de aplicativos. Um usuário do Skype for Business na sala de conferência precisa participar da conferência do Skype for Business (por meio de um laptop, por exemplo) e exibir as telas de compartilhamento de aplicativo em um dos monitores gratuitos na sala de conferência não associados à VTC.
    
- Não há suporte para o VTC entrar em uma reunião federada via VIS.
    
- Não há suporte para o VTC entrar em uma reunião online via VIS.
    
- Não há suporte para chamadas de um VTC para PSTN via VIS.
    
- Não há suporte para chamadas de um PSTN para um VTC via VIS.
    
## <a name="resiliency-mechanisms"></a>Mecanismos de resiliência
<a name="resiliency"> </a>

O VIS é compatível com chamada recebida de um CUCM que seja transmitido sobre um tronco SIP de vídeo. Como é possível perder conectividade upstream ou downstream, para conseguir uma resiliência robusta é necessário considerar as duas possibilidades:
  
1. **Vis failover de pool** Se o pool principal do VIS para o qual o gateway de vídeo aponta estiver inoperante, a recuperação será possível se o gateway de vídeo tiver definido troncos para dois (ou mais) pools de VIS. Se o gateway de vídeo determinar que não pode fazer chamadas para o pool de VIS primário, ele simplesmente encaminhará as chamadas para o pool de VIS secundário.
    
     ![Diagrama do failover do pool VIS](../media/390d93c3-e132-4bbd-8d5a-c70ead9cdfad.png)
  
    Um determinado pool VIS pode ter troncos para vários gateways, mas normalmente um determinado gateway não pode ter troncos para vários pools de VIS, portanto, é preciso que uma rodada seja feita para dar suporte a esse failover: defina 2 FDQNs no DNS que são resolvidos para o mesmo endereço IP de um gateway de vídeo. Represente cada FQDN como um gateway de vídeo separado no documento de topologia em que cada gateway de vídeo tem um tronco para um pool de VIS diferente e a recuperação agora é possível. (Se TLS for usado, os vários nomes deverão estar na SAN do certificado de gateway de vídeo.)
    
    > [!NOTE]
    > O VIS só permite chamadas de entrada de gateways configurados no Documento de Topologia. 
  
2. **Failover de front-end** Se um pool de VIS receber uma chamada de CUCM, mas não puder alcançar seu registrador de próximo salto primário ou o pool de front-end, as chamadas serão roteadas para um pool de front-ends de backup.
    
     ![Diagrama de failover de front-end](../media/6ddc08ec-4708-4c23-9e77-0f88899a2a96.png)
  
    O VIS acompanhará o status de seu pool de front-end primário e seu pool de front-end de backup (a configuração é encontrada na configuração de backup do serviço registrador no documento de topologia). Ele envia pesquisas de opções uma vez por minuto para ambos os pools e, se houver cinco falhas consecutivas, o VIS pressupõe que um pool de front-end específico está inoperante. Se o pool de front-end primário estiver marcado como inativo e houver um backup configurado disponível, o VIS enviará novas chamadas do gateway para o pool de front-end de backup. Quando o pool de front-end primário voltar, o VIS será retomado usando o pool de front-end primário para novas chamadas.
    
    O VIS também implantará um temporizador de 10 segundos pelo tronco do SIP de vídeo. Se o pool primário de front-hop primário foi usado para uma chamada do tronco SIP de vídeo e o pool primário de front-hop primário não atender com uma mensagem SIP (incluindo 100 tentando) para o convite enviado a ele nesse valor do temporizador, o proxy do próximo salto do backup para a chamada s hould ser tentada se estiver configurada. 
    
    > [!NOTE]
    > Se a primeira tentativa for com o próximo salto de backup, não haverá tentativa com o primário em seguida. 
  
    O administrador também pode usar o comando de failover do Windows PowerShell para forçar o VIS a usar o pool de front-ends do backup, por exemplo, quando a manutenção precisar ser executada no pool de front-ends.
    
## <a name="co-existence-of-voice-and-video-trunks-to-the-same-gateway-peer"></a>Coexistência de troncos de voz e de vídeo para o mesmo par de gateway
<a name="resiliency"> </a>

O Skype for Business Server permite que troncos SIP de voz e vídeo usem o mesmo ponto de gateway. Assim, a mesma implantação de CUCM poderia ter troncos de SIP de voz para o Servidor de Mediação e troncos SIP de vídeo para VIS.
  
- Será necessário definir um gateway de PSTN com um FQDN em particular no Documento de Topologia para os troncos SIP de voz.
    
- O par do Gateway do PSTN será o Servidor de Mediação.
    
- Vários troncos de voz podem ser definidos, variando de um gateway de PSTN até vários pools do Servidor de Mediação, se necessário.
    
- O Gateway de Vídeo precisará ser definido no Documento de Topologia para o tronco do SIP do vídeo com o mesmo FQDN que o do Gateway do PSTN.
    
- O par para o Gateway de Vídeo será VIS.
    
- Um único tronco de vídeo pode ser definido por um Gateway de Vídeo para um pool VIS em particular.
    
- O CUCM precisará ser configurado para encaminhar corretamente as chamadas pelo tronco de voz pelo tronco de vídeo. Por exemplo: um prefixo de discagem especial poderia ser usado ao discar pelo VTC; o CUCM poderia associar o prefixo de discagem com chamadas ao VIS, e regras de conversão adequadas tirariam esse prefixo do SIP Invite para o VIS.
    
## <a name="co-existence-of-vis-in-the-skype-for-business-release-with-previous-releases-of-lync"></a>Coexistência de VIS na versão do Skype for Business com versões anteriores do Lync
<a name="resiliency"> </a>

O VIS só poderá ser implantado como parte da implantação do Skype for Business. A interoperação será possível com conferências do Lync 2013 e clientes que fazem parte de uma implantação existente; nesses casos, o pool do VIS precisará fazer parte de uma implantação do Skype for Business que inclua um pool de Registrador Automático/FE que seja o próximo salto para o pool do VIS.
  
O VIS não é compatível com a transcodificação entre RTV e H.264. Não há interoperabilidade do vídeo entre clientes pré-Lync 2013 e participantes de VTC em uma conferência.
  
Se houver clientes anteriores ao Lync 2013 em uma conferência, os clientes móveis enviarão usando RTV, fazendo com que os VTCs não recebam nenhum vídeo quando o cliente móvel tornar-se o alto-falante dominante.
  
Para o Lync 2013 funcionar corretamente com o VIS que faz parte da implantação do Skype for Business, o Lync 2013 precisará da aplicação do gerenciador de comunicações adequado para atualizar o cliente do Lync 2013, o CAA e o AVMCU.
  
A interoperabilidade do VIS com os clientes de desktop do Lync 2013 e do Skype for Business foi testada e é compatível.
  
Interoperabilidade do VIS com não-desktop (Android, iPad, iPhone, Windows Phone, LMX, etc.) Os clientes do Skype for Business disponíveis na loja de aplicativos aplicáveis no momento do lançamento do VIS foram testados e são suportados.
  
## <a name="recovery-from-packet-loss-via-fec"></a>Recuperação da perda de pacote via FEC
<a name="resiliency"> </a>

O FEC pode ser ativado para ajudar na recuperação da perda do pacote. Se ativado, será usado 50% mais de largura de banda na direção de VIS para VTC.
  
## <a name="vis-sizing-and-transcoding-costs"></a>Custos de dimensionamento e transcodificação de VIS
<a name="resiliency"> </a>

A transcodificação de fluxos de vídeo únicos do Cisco VTC para vários fluxos simulcast usa a capacidade da CPU. Aproximadamente 16 VTCs podem ter seus vídeos transcodificados (pressupondo que um fluxo de vídeo 720p de cada VTC é transcodificado em 3 fluxos de simulcast separados em 720p, 360p e 180p) em uma única VIS em execução no equivalente da plataforma FE do Lync 2013 recomendada. Se a transcodificação for desativada, a CPU do VIS será poupada. No entanto, a imagem de vídeo solicitada pelo VIS do VTC será a mais baixa resolução em comum para atender todos os receptores do lado do Skype for Business. Observe que até mesmo com a transcodificação desativada, ela poderá ser ativada quando os clientes do Skype for Business solicitarem determinadas baixas resoluções que os VTCs não podem enviar.
  
## <a name="call-distribution-from-the-video-gateway-to-vis"></a>Distribuição de chamada do gateway de vídeo para o VIS
<a name="resiliency"> </a>

A distribuição é conquistada por um dos mecanismos de distribuição de CUCM:
  
- Dinamicamente usando DNS.
    
- No lado do CUCM, você pode definir cada um dos troncos, sendo que cada um termina em um servidor diferente do pool de VIS. O CUCM encaminhará as chamadas pelos diferentes troncos.
    
## <a name="no-hybrid-interoperability"></a>Sem interoperabilidade híbrida
<a name="resiliency"> </a>

O suporte a VTCs que entram para reuniões online via VIS local não faz parte do Skype for Business.
  
## <a name="no-federation-support"></a>Sem suporte de federação
<a name="resiliency"> </a>

O suporte a VTCs que entram para reuniões federadas via VIS não faz parte do Skype for Business.
  
## <a name="see-also"></a>Confira também
<a name="resiliency"> </a>

[Implantar o servidor de interoperabilidade de vídeo no Skype for Business Server](../deploy/deploy-video-interop-server/deploy-video-interop-server.md)
