---
title: Requisitos de salas do Microsoft Teams
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
localization_priority: Normal
ms.assetid: 6b2b2684-8e9e-49ea-8c46-1c690964f982
ms.collection:
- M365-collaboration
description: Este artigo resume os requisitos para dar suporte a salas do Microsoft Teams.
ms.openlocfilehash: f9cdb6acd98fed0c20aed74fc5bdce3dff02b3d6
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37573633"
---
# <a name="microsoft-teams-rooms-requirements"></a>Requisitos de salas do Microsoft Teams

Este artigo resume os requisitos para dar suporte a salas do Microsoft Teams.

Sua implantação envolve a criação de conta, conforme descrito em [implantar salas do Microsoft Teams](room-systems-v2.md) e configurar os consoles de reunião, conforme descrito em [configurar um console de salas do Microsoft Teams](console.md).

Além disso, consulte:

- [Licenciamento do complemento Skype for Business](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing)
- [Opções de licença com base em seu plano: salas do Microsoft Teams](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2)

> [!NOTE]
> As salas do Microsoft Teams devem ser usadas com o Microsoft Teams, o Skype for Business Server 2019, o Skype for Business Server 2015 ou o Skype for Business online.
>
> Plataformas anteriores como o Lync Server 2013 não devem funcionar com salas do Microsoft Teams. Não há suporte para salas do Microsoft Teams no Office 365 operado pela 21Vianet ou em ambientes GCC, GCC-superior ou DoD.
>
> Se você tiver um servidor Exchange local, as salas do Microsoft Teams exigem o uso do Exchange Server 2013 SP1 ou posterior.

## <a name="hardware-requirements"></a>Requisitos de hardware

As salas do Microsoft Teams são dimensionadas para diferentes tamanhos de sala usando diferentes periféricos de áudio e vídeo com base no tamanho da sala. O hardware listado neste artigo é compatível com os modos de reunião do Skype e do teams. Os periféricos de áudio e vídeo se conectam a salas do Microsoft Team via conexão USB ou HDMI no dispositivo de encaixe. Você também precisa de:

- Um disco USB de 32 GB ou maior que você configura como mídia inicializável da instalação do Windows para Windows 10 Enterprise.
- Um dos seguintes tablets ou consoles:

  **Tablets compatíveis**

  |Sofrer|631|RAM|Disco|
  |:-----|:-----|:-----|:-----|
  |Surface pro 6| Core i5 |16 GB ou 8 GB |128 GB ou mais |
  |Surface pro </br>(quinta geração) |Core i5 |8 GB ou 4 GB |128 GB ou mais |
  |Surface Pro 4 |Core i5 |8 GB ou 4 GB |128 GB ou mais |

- Uma das opções de Docking Station a seguir para proteger um tablet para a tabela de salas de reunião.

  - [Logitech SmartDock](https://www.logitech.com/product/smartdock)
  - [Crestron SR](http://www.crestron.com/products/line/sr-for-skype-for-business-room-system )
  - [Série MSR Polycom](http://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.html)

- **Outros consoles de salas do Microsoft Teams com suporte**

  |Console|631|RAM|Disco|
  |:-----|:-----|:-----|:-----|
  |[Crestron Flex-M130-T](https://crestron.com/en-US/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M130-T)|Core i5|8 GB |128 GB |
  |[Crestron Flex-B130-T](https://crestron.com/en-US/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B130-T)|Core i5|8 GB |128 GB |
  |[Crestron Flex-B140-T](https://crestron.com/en-US/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B140-T)|Core i5|8 GB |128 GB |
  |[Crestron Flex-M150-T](https://crestron.com/en-US/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M150-T)|Core i7|8 GB |128 GB |
  [Crestron Flex-B160-T](https://crestron.com/en-US/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B160-T)|Core i7|8 GB |128 GB|
  |[Crestron Flex-C160-T](https://crestron.com/en-US/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C160-T)|Core i7|8 GB|128 GB|
  |[Fatia HP elite para salas de reunião G2](https://www8.hp.com/us/en/elite-family/elite-slice-for-meetings.html) |Core i5 |8 GB |128 GB |
  |[Áudio G2 da fatia HP elite pronto para salas do Microsoft Teams](https://store.hp.com/us/en/pdp/hp-elite-slice-for-meeting-rooms-g2-skype-room-systems-audio-ready?jumpid=cp_r12131_us/en/psg/elite_slice_for_meetings/product/shop-now-eliteslicemeeting-g2-audio) |Core i5 |8 GB |128 GB |
  |[Hub ThinkSmart Hub do Lenovo 500](https://www3.lenovo.com/us/en/hub500) |Core i5 |8 GB |128 GB |
  |[Logitech Tap](https://www.logitech.com/en-us/product/microsoft-rooms)|Core i5|8 GB |128 GB |
  |[Yealink MVC800](https://www.yealink.com/products_125.html)|Core i5|8 GB|128 GB|
  |[Yealink MVC500](https://www.yealink.com/products_126.html)|Core i5|8 GB |128 GB |
  |||||

  > [!NOTE]
  > Não há suporte para os processadores Core m3.

### <a name="certified-firmware-versions-for-usb-audio-and-video-peripherals"></a>Versões de firmware certificadas para periféricos de áudio e vídeo USB

Esses dispositivos estão disponíveis em [aka.ms/teamsdevices](https://aka.ms/teamsdevices).

|Salas do Microsoft Teams Peripheral|Versão do firmware certificado | Câmera compatível com uso de câmera de conteúdo|
|:--- |:--- | :--- |
|[IQ Huddly de Crestron](https://www.crestron.com/en-US/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Accessories/CCS-CAM-USB-F-400)   | 1.02.09.33901  | &#x2714; |
|[Logitech BRIO](https://www.logitech.com/en-us/product/brio)   |v240| &#x2714; |
|[Logitech 930e](http://www.logitech.com/en-us/product/c930e-webcam)   | 8.0.914   | &#x2714; |
|[Logitech Rally](https://www.logitech.com/en-us/product/rally-ultra-hd-conferencecam)   |1.2.4 |
|[Logitech MeetUp](http://www.logitech.com/en-us/product/meetup-conferencecam)   |Áudio — 1.0.172 <br/> Vídeo — 1.0.156  |
|[Conexão Logitech ConferenceCam](http://www.logitech.com/en-us/product/conferencecam-connect)   |1.1.248.0 <br/> 1.1.684   |
|[Grupo Logitech](http://www.logitech.com/en-us/product/conferencecam-group)   |8.5.778   |
|[Logitech PTZ pro](http://www.logitech.com/en-us/product/conferencecam-ptz-pro)   | 1.1.219   |
|[Logitech PTZ Pro 2](http://www.logitech.com/en-us/product/conferencecam-ptz-pro2)   |
|[Polycom EagleEye IV](http://www.polycom.com/products-services/hd-telepresence-video-conferencing/realpresence-accessories/eagleeye-cameras.mdl)   |1.0.0   |
|[Polycom CX5100 ](http://www.polycom.com/products-services/products-for-microsoft/lync-optimized/cx5100-unified-conference-station.mdl)   | 1.2.0,70232   |
|[Diretor de olhos Polycom Eagle II](https://www.polycom.com/hd-video-conferencing/peripherals/eagleeye-director-ii.html)|2.1.0.10|
|[Polycom trio 8500/8800](https://www.polycom.com/voice-conferencing-solutions/conference-phones/trio.html)   |5.7.2.3205|
|[Sennheiser SP 220 MS](http://no-no.sennheiser.com/dual-speakerphones-sp-220-ms-uc)   |2.0.12.0   |
|[Sennheiser SP20](http://en-us.sennheiser.com/sp-20-og-sp-20-ml)   |1.2.15   |
|[Sennheiser SP30](https://en-us.sennheiser.com/sp-30)   |2.1.52  |
|[Jabra 510](http://www.jabra.com/support/Jabra-SPEAK™-510_7510-209)   |2.10.0   |
|[Jabra 710](http://www.jabra.com/business/speakerphones/jabra-speak-series/jabra-speak-710)   |1.8.0   |
|[Jabra 810](http://www.jabra.com/supportpages/jabra-speak-810)   |1.2.23   |
|[Yamaha YVC-1000](http://www.yamaha.com/products/en/communication/usb_conference_speakerphones/yvc-1000/)   |100c   |
|[Biamp Tesira de primeiro plano AVB VT4 de áudio fixo](https://www.biamp.com/products/tesira-fixed-audio-dsp)+ &Dagger;</br></br> [Sennheiser TeamConnect teto 2](https://en-us.sennheiser.com/tcc2)+ &Dagger;</br></br> [TESIRA ex-UBT](https://www.biamp.com/products/tesira/tesira-expanders)&Dagger; |  DSP Biamp: 3.12.0.15  </br></br> TCC2: 1.3.3 </br></br> EX-UBT: 3.12.0.15 |  |
||||

&Dagger;Os clientes podem escolher a interface Dante ou o comutador de rede recomendado pelo Biamp/Sennheiser para este pacote.

#### <a name="usb-extenders"></a>Extensores USB

- Portas USB em cais de Tablet são compatíveis com USB 3,0. Você pode usar um Extender USB 2. x, mas isso o limita a velocidades USB 2. x na extremidade. Os extensores não são recomendados para periféricos USB 3,0.
- Um Extender deve atender às especificações USB 2,0 ou mais recente.
  - Os encaixes de Tablet dão suporte a pelo menos dois estágios de extensão de Hub USB externo. Se você conectar mais de dois hubs USB em série, verifique com o fabricante do Dock para confirmar se eles dão suporte à conexão de série.
  - Conexão GbE com fio na sala. Cabo Ethernet de comprimento adequado.
  - Até 2 1080-p é exibido com conexões HDMI. Cabos HDMI de tamanho apropriado.

> [!NOTE]
> A TV usada em uma sala de exibição precisa suportar/habilitar o recurso CEC (Controle Eletrônico do Consumidor) do HDMI para que possa alternar automaticamente do modo de espera para uma fonte de vídeo ativa.  Esse recurso não é suportado em todas as TVs.
>
> As salas do Microsoft Teams não usam um teclado. Se necessário, o administrador deve usar o teclado virtual. Um mouse ou teclado USB será necessário ao fazer o Imaging do dispositivo de salas do Microsoft Teams.

As tabelas a seguir fornecem recomendações para periféricos com base no tamanho da sala:

**Periféricos de áudio certificados de salas do Microsoft Teams**

|Tipo de sala|Número de pessoas|Distância máxima recomendada do microfone para o alto-falante|Dispositivo, de acordo com o tamanho máximo da sala|Comentários|
|:-----|:-----|:-----|:-----|:-----|
|**Foco** <br/> 10 ' x 9 '   |2 a 4  |1,5 m  |Logitech Connect  |Os dispositivos Logitech Connect incluem uma câmera que deve ser posicionada na frente da sala (não no centro da tabela) para capturar os participantes da reunião local. |
|**Pequena** <br/> 16 ' x 16 '  |4 a 6  |2,0 m  |Jabra 510 <br/> Sennheiser SP20  |O volume de reprodução pode ser limitado para salas maiores.  |
|**Médio** <br/> 18 ' x 20 '  |6 a 12  |2,4 m  |Jabra 710 <br/> Jabra 810 <br/> Logitech MeetUp <br/> Logitech Group <br/> Polycom Trio <br/> Polycom CX5100  <br/> Sennheiser SP 220 MS <br/> Yamaha YVC-1000MS  |O Logitech MeetUp inclui uma câmera para que ela deva ser posicionada na frente da sala (não no centro da tabela para capturar os participantes da reunião local). <br/> Em geral, as salas com tabelas retangulares ou em formato de u longos podem se beneficiar com microfones satélites. <br/> O SP 220 MS deve ser usado em configuração de corrente margarida.  |
|**Grande** <br/> 15 ' x 32 '  |de 12 a 16  |3 m <br/> Essa distância também se aplica à área coberta por cada microfone satélite conectado.  |Logitech Group + satélite duais <br/> Polycom trio + satélite duais <br/> Polycom CX5100 + satélite duais <br/> Sennheiser SP 220 MS <br/> Yamaha YVC-1000MS + satélite duais  |Todos os dispositivos de áudio listados nesta linha dão suporte a opções de microfones parabólicos. <br/> O CX5100 inclui uma câmera interna de 360 graus para que o dispositivo possa ser posicionado no centro da tabela. <br/> O SP 220 MS deve ser usado em configuração de corrente margarida.  |

**Periféricos de vídeo certificados para salas do Microsoft Teams**

|Tipo de sala|Número de pessoas|Dispositivo por tamanho ideal da sala|Comentários|
|:-----|:-----|:-----|:-----|
|**Foco** <br/> 10 ' x 9 '  |2 a 4  |Logitech Connect <br/> Logitech MeetUp <br/> Polycom CX5100   ||
|**Pequena** <br/> 16 ' x 16 '  |4 a 6  |Logitech C930e <br/> Logitech MeetUp <br/> Logitech BRIO <br/> Logitech PTZ pro <br/> Polycom MSR <br/> Polycom CX5100   |A Logitech PTZ pro geralmente acompanhada do Logitech Group  |
|**Médio** <br/> 18 ' x 20 '  |6 a 12  |Logitech MeetUp <br/> Logitech BRIO <br/> Logitech PTZ pro <br/> Polycom MSR <br/> Polycom CX5100   ||
|**Grande** <br/> 15 ' x 32 '  |de 12 a 16  |Logitech PTZ pro <br/> Polycom MSR <br/> Polycom CX5100   ||

 > [!NOTE]
 > A resolução de tela frontal da sala deve ser definida como não maior do que 1920x1080p.

## <a name="required-software-downloads"></a>Downloads de software necessários

Para criar sua própria imagem de salas do Microsoft Teams, siga as instruções em [configurar um console de salas do Microsoft Teams](console.md). Essas instruções o orientam pelo download de todo o software necessário para a instalação.

> [!NOTE]
> Os profissionais de ti precisarão acessar os arquivos ISO do Windows 10 Enterprise por meio do contrato de licenciamento por volume.

[SkypeRoomProvisioningScript. ps1](https://go.microsoft.com/fwlink/?linkid=870105) é um download opcional que você pode usar para configurar contas de salas do Microsoft Teams.

## <a name="see-also"></a>Confira também

[Procurar todos os pacotes](https://products.office.com/en-us/microsoft-teams/across-devices/devices)

[Plano para salas do Microsoft Teams](skype-room-systems-v2-0.md)

[Implantar salas do Microsoft Teams](room-systems-v2.md)

[Configurar um console de salas do Microsoft Teams](console.md)

[Gerenciar Salas do Microsoft Teams](skype-room-systems-v2.md)

[Licenciamento de complementos do Skype for Business](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)
