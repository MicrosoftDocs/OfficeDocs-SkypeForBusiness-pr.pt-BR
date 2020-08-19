---
title: Requisitos das Salas Microsoft Teams
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6b2b2684-8e9e-49ea-8c46-1c690964f982
ms.collection:
- M365-collaboration
description: Saiba mais sobre os requisitos de suporte a salas do Microsoft Teams, incluindo a escolha do dispositivo apropriado, microfones, alto-falantes, câmeras e monitores.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: cc5db49a105d113240d29b9f139993e8dd2bd99f
ms.sourcegitcommit: bd13aecbb25c14e17d1b64343df6d80c90b2aa45
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/19/2020
ms.locfileid: "46803913"
---
# <a name="microsoft-teams-rooms-requirements"></a>Requisitos das Salas Microsoft Teams

As Salas do Microsoft Teams são dimensionadas para tamanhos de sala diferentes usando uma ampla variedade de periféricos de áudio e vídeo com base no tamanho e no uso da sala. Selecionando o principal dispositivo e console, combinado com microfones, alto-falantes, câmeras e vídeos apropriados para o espaço, você pode implantar as Salas do Microsoft Teams em espaços de qualquer tamanho, desde pequenos espaços de reunião até grandes espaços de conferência e salas de reuniões.  O conjunto completo de todos os periféricos de áudio e vídeo certificados disponíveis que podem ser usados para configurar a sua sala está disponível [Mostruário do dispositivo](https://products.office.com/microsoft-teams/across-devices).

Este artigo resume a implantação e os requisitos de configuração do dispositivo para dar suporte às Salas do Microsoft Teams.

Sua implantação envolve a criação de contas conforme descrito em [Implantar Salas do Microsoft Teams](rooms-deploy.md) e a configuração dos consoles de reunião conforme descrito em [Configurar um console de Salas do Microsoft Teams](console.md).

Além disso, confira:

- [Licenciamento do complemento Skype for Business](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing)
- [Opções de licença baseadas em seu plano: Salas do Microsoft Teams](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2)

> [!NOTE]
> As Salas do Microsoft Teams entram no Microsoft Teams, no Skype for Business Server 2019, no Skype for Business Server 2015 ou no Skype for Business Online, e podem participar de reuniões hospedadas por qualquer um desses serviços.
>
> As plataformas anteriores, como o Lync Server 2013, não são compatíveis com as Salas do Microsoft Teams. Não há suporte para salas do Microsoft Teams no Microsoft 365 ou no Office 365 operado pela 21Vianet ou em ambientes GCC-High ou DoD.
>
> Se você tiver um Exchange Server local, as salas do Microsoft Teams exigirá o uso do Exchange Server 2013 SP1 ou posterior.

## <a name="hardware-requirements"></a>Requisitos de hardware
Uma implantação de hardware inclui uma seleção de um sistema de Sala do Microsoft Teams, combinada com periféricos de áudio e vídeo certificados e uma solução de cabeamento para integrar esses dispositivos.  Essas opções estão descritas aqui.

**Sistemas compatíveis com a Sala do Microsoft Teams **

Todos os pacotes e dispositivos da Sala do Microsoft Teams estão disponíveis em [Mostra de produtos dos Sistemas de Sala](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=20&page=1&filterIds=).

  |Console|Processador|RAM|Disco|
  |:-----|:-----|:-----|:-----|
  |[Crestron Flex UC-M130-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M130-T)|Core i5|8 GB |128 GB |
  |[Crestron Flex UC-B130-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B130-T)|Core i5|8 GB |128 GB |
  |[Crestron Flex UC-B140-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B140-T)|Core i5|8 GB |128 GB |
  [Crestron Flex-C140-T](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C140-T)|I7 principais|8 GB |128 GB|
  |[Crestron Flex UC-M150-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M150-T) + [CCS-UCA-MIC](https://www.crestron.com/en-US/Products/Audio/Microphones/Wired-Microphones/CCS-UCA-MIC-KIT)|I7 principais|8 GB |128 GB |
  |[Crestron Flex-MX150-T](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-MX150-T)|Core i5|8 GB |128 GB |
   [Crestron Flex UC-B160-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B160-T)|I7 principais|8 GB |128 GB|
  |[Crestron Flex UC-C160-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C160-T)|I7 principais|8 GB|128 GB|
  |[HP Elite Slice para Salas de Reunião G2](https://www8.hp.com/us/en/elite-family/elite-slice-for-meetings.html) |Core i5 |8 GB |128 GB |
  |[HP Elite Slice G2 Audio Ready com Salas do Microsoft Teams](https://store.hp.com/us/en/pdp/hp-elite-slice-for-meeting-rooms-g2-skype-room-systems-audio-ready?jumpid=cp_r12131_us/en/psg/elite_slice_for_meetings/product/shop-now-eliteslicemeeting-g2-audio) |Core i5 |8 GB |128 GB |
  |[Parceiro de fatia HP pronto para o Logitech TAP]( https://www.logitech.com/en-us/video-collaboration/partners/hp.html)|Core i5|8 GB|128 GB|
  |[Hub Lenovo ThinkSmart 500](https://www3.lenovo.com/us/en/hub500) |Core i5 |8 GB |128 GB |
  |[Logitech Tap with Intel NUC](https://www.logitech.com/product/microsoft-rooms)|Core i5|8 GB |128 GB |
  |[Logitech TAP e Lenovo do centro de raciocínio M920 Tiny](https://www.logitech.com/en-us/video-collaboration/partners/lenovo.html)|Core i5|8 GB |128 GB|
  |[Yealink MVC300 com Intel NUC](https://www.yealink.com/products_154.html)|Core i5|8 GB |128 GB |
  |[Yealink MVC500 com Intel NUC](https://www.yealink.com/products_126.html)|Core i5|8 GB |128 GB |
  |[Yealink MVC800 com Intel NUC](https://www.yealink.com/products_125.html)|Core i5|8 GB|128 GB|
  |[Yealink MVC900 com Intel NUC](https://www.yealink.com/product/microsoft-teams-room-system-mvc900)|Core i5|8 GB|128 GB|
  |[Yealink MVC 300 II ](https://www.yealink.com/product/microsoft-teams-room-system-mvc300II) |Core i5|8 GB | 128 GB|
  [Yealink MVC 500 II ](https://www.yealink.com/product/microsoft-teams-room-system-mvc500II) |Core i5|8 GB | 128 GB|
  [Yealink MVC 800 II ](https://www.yealink.com/product/microsoft-teams-room-system-mvc800II) |Core i5|8 GB | 128 GB|
  [Yealink MVC 900 II ](https://www.yealink.com/product/microsoft-teams-room-system-mvc900II) |Core i5|8 GB | 128 GB|
  ||||||

> [!NOTE]
> - Os processadores Core M3 não são compatíveis.
> - É necessário ter uma unidade USB de 32 GB ou maior configurada como mídia de instalação inicializável do Windows para Windows 10 Enterprise.

**Tablet Surface Pro com suporte para sistemas de encaixe**

  |Tablet|Processador|RAM|Disco|
  |:-----|:-----|:-----|:-----|
  |Surface Pro 6| Core i5 |16 GB ou 8 GB |128 GB ou mais |
  |Surface Pro </br>(quinta geração) |Core i5 |8 GB ou 4 GB |128 GB ou mais |
  |Surface Pro 4 |Core i5 |8 GB ou 4 GB |128 GB ou mais |

- Os dispositivos Surface pro exigem uma das seguintes opções de Docking Station:

  - [Logitech SmartDock](https://www.logitech.com/product/smartdock)
  - [Crestron SR](https://www.crestron.com/products/line/sr-for-skype-for-business-room-system )
  - [Polycom MSR](https://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.html)

### <a name="certified-firmware-versions-for-usb-audio-and-video-peripherals"></a>Versões de firmware certificadas para periféricos USB e de áudio

Esses dispositivos estão disponíveis na [Mostruário de produtos de acessórios para Sistemas de Salas](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=73&page=1&filterIds=)[https://office.com/teamsdevices](https://office.com/teamsdevices).

|Periférico das Salas do Microsoft Teams|Versão de firmware certificado | A câmera compatível com o uso da câmera de conteúdo|
|:--- |:--- | :--- |
|[Aver CAM 540](https://www.averusa.com/products/conference-camera/cam540) |0.0.6002.83 |
|[Aver CAM 520 pro](https://www.averusa.com/products/conference-camera/cam520pro) |0.0.1000.73 |
|[Crestron Huddly IQ](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Accessories/CCS-CAM-USB-F-400)   | 1.02.09.33901  | 
|[Tela Huddly](https://www.huddly.com/blog/say-hello-to-huddly-canvas-our-latest-ai-technology-for-content-capture-and-enhancement/) | 1.3.25 |  &#x2714; |
|[IQ Huddly](https://www.huddly.com/conference-cameras/iq/) |1.3.22|
|[Câmera Panacast Jabra](https://www.jabra.com/business/video-conferencing/jabra-panacast)|3.8.22|
|[Logitech brio](https://www.logitech.com/product/brio)   |V 2.2.50| &#x2714; |
|[Logitech 930e](https://www.logitech.com/product/c930e-webcam)   | 8.0.914   | &#x2714; |
|[Logitech Rally](https://www.logitech.com/product/rally-ultra-hd-conferencecam)   |1.2.4 |
|[Logitech MeetUp](https://www.logitech.com/product/meetup-conferencecam)   |Audio — 1.0.172 <br/> Video — 1.0.156  |
|[Logitech ConferenceCam Connect](https://www.logitech.com/product/conferencecam-connect)   |1.1.248.0 <br/> 1.1.684   |
|[Logitech Group ](https://www.logitech.com/product/conferencecam-group)   |8.5.778   |
|[Logitech PTZ pro](https://www.logitech.com/product/conferencecam-ptz-pro)   | 1.1.219   |
|[Logitech PTZ Pro 2](https://www.logitech.com/product/conferencecam-ptz-pro2)   |
|[Câmera Poly Eagle Eye Cube](https://www.polycom.com/products-services/hd-telepresence-video-conferencing/realpresence-accessories/eagleeye-cameras.html)  |1.2.0 |
|[Polycom EagleEye IV](https://www.polycom.com/products-services/hd-telepresence-video-conferencing/realpresence-accessories/eagleeye-cameras.mdl)   |1.0.0   |
|[Polycom CX5100](https://www.polycom.com/products-services/products-for-microsoft/lync-optimized/cx5100-unified-conference-station.mdl)   | 1.2.0.70232   |
|[Diretor de olho Polycom Eagle II](https://www.polycom.com/hd-video-conferencing/peripherals/eagleeye-director-ii.html)|2.1.0.10|
|[Polycom Studio](https://www.polycom.com/hd-video-conferencing/room-video-systems/polycom-studio.html)|1.1.2.000570|
|[Polycom trio 8500/8800](https://www.polycom.com/voice-conferencing-solutions/conference-phones/trio.html)   |5.7.2.3205|
|[EPOS SP 220 MS](http://no-no.sennheiser.com/dual-speakerphones-sp-220-ms-uc)   |2.0.12.0   |
|[EPOS SP20](https://www.eposaudio.com/en/us/enterprise/products/sp-20-ml-142ee5ca-speakerphone-1000226)   |1.2.15   |
|[EPOS SP30](https://www.eposaudio.com/en/us/enterprise/products/sp-30-78c0cecc-bluetooth-speakerphone-1000223)   |2.1.52  |
|[EPOS SP30T](https://www.eposaudio.com/en/us/enterprise/products/sp-30t-b949fe9a-bluetooth-speakerphone-1000225)  |3.2.63  |
|[Jabra 510](http://www.jabra.com/support/Jabra-SPEAK&trade;-510_7510-209)   |2.10.0   |
|[Jabra 710](http://www.jabra.com/business/speakerphones/jabra-speak-series/jabra-speak-710)   |1.8.0   |
|[Jabra 810](http://www.jabra.com/supportpages/jabra-speak-810)   |1.2.23   |
|[Yamaha YVC-1000](http://www.yamaha.com/products/en/communication/usb_conference_speakerphones/yvc-1000/)   |100c   |
|[Yealink CP900](https://www.yealink.com/products_150.html) |100.20.0.29 |
|[Processador de Audioconferência Shure Intellimix P300](https://www.shure.com/en-US/products/mixers/p300)+</br></br> [Shure MXA 310 ](https://www.shure.com/en-US/products/microphones/mxa310) | 4.1 |
|[Processador de Audioconferência Shure Intellimix P300](https://www.shure.com/en-US/products/mixers/p300) + </br></br> [Shure MXA 910 com Intellimix Ceiling Array Mic](https://www.shure.com/en-US/products/microphones/mxa910) | 4.1|
|[Biamp Tesira Fore AVB VT4 Fixed audio DSP](https://www.biamp.com/products/tesira-fixed-audio-dsp)+ &Dagger;</br></br> [Sennheiser TeamConnect Ceiling 2 Microphone](https://en-us.sennheiser.com/tcc2)+ &Dagger;</br></br> [Tesira EX-UBT](https://www.biamp.com/products/tesira/tesira-expanders) &Dagger; |  DSP Biamp: 3.12.0.15  </br></br> TCC2: 1.3.3 </br></br> EX-UBT: 3.12.0.15 |
|[Biamp Tesira FORTÉ AVB VT4 áudio DSP](https://www.biamp.com/products/tesira-fixed-audio-dsp)+ </br></br>[Biamp parlé TCM-microfone de teto XA](https://www.biamp.com/products/product-families/parle/parle-microphones)+</br></br> [Biamp Desono C-IC6-montado no teto de alto-falante](https://www.biamp.com/products/tesira-speakers)| Versão do firmware de áudio: 3,15|
|[Biamp TesiraFORTE AVB VT4](https://www.biamp.com/products/tesira-fixed-audio-dsp)+ </br></br>[Parle TTM-X (tabela MIC)](https://www.biamp.com/products/product-families/parle/parle-microphones)+</br></br>[Ex-UBT]() |Versão do firmware de áudio: 3,15|
|[Bose ControlSpace EX-440C DSP + </br>Bose P2600A AmpLink Amplifier +</br> Sennheiser TCC2 Ceiling Microphone + </br> Bose EdgeMax EM180 Ceiling Speaker](https://pro.bose.com/en_us/solutions/bose-work/es1-ceiling-audio-solution.html)|  Bose DSP: 2,290  </br> P2600A: 1,160  </br> TCC2:1.4.2  |  |
|[Bose ControlSpace EX-440C DSP + </br> Bose P2600A AmpLink amplificador + Sennheiser TCC2 teto microfone + </br> Bose DesignMax DM2C-P alto-falante teto](https://pro.bose.com/en_us/solutions/bose-work/es1-ceiling-audio-solution.html)|  Bose DSP: 2,290  </br> P2600A: 1,160  </br> TCC2:1.4.2  |  |
||||||



&Dagger; Os clientes podem escolher a interface Dante ou a opção de rede recomendada por Biamp/Sennheiser para esse pacote.

#### <a name="usb-extenders"></a>Extensores USB

- As portas USB em docking stations são compatíveis com USB 3.0. Você pode usar um extensor USB 2.x, mas isso limita as velocidades do USB 2.x na extremidade oposta. Os extensores não são recomendados para periféricos USB 3.0.
- Um extensor deve atender a especificações USB 2,0 ou mais recentes.
  - As estações para tablet suportam pelo menos dois estágios da extensão do hub USB externo. Se você conectar mais de dois hubs USB na série, verifique com o fabricante da estação se eles são compatíveis com a conexão de série.
  - Conexão GbE com fio na sala. Cabo Ethernet de comprimento adequado.
  - Até dois monitores de 1080 p com conexões HDMI. Cabos HDMI de comprimento adequado.

> [!NOTE]
> A TV usada em uma sala de exibição precisa suportar/habilitar o recurso CEC (Controle Eletrônico do Consumidor) do HDMI para que possa alternar automaticamente do modo de espera para uma fonte de vídeo ativa.  Esse recurso não é suportado em todas as TVs.
>
> Salas do Microsoft Teams não usa um teclado. Se necessário, o administrador deve usar o teclado virtual. O teclado ou o mouse USB serão necessários ao criar Imagens no dispositivo Salas do Microsoft Teams.

A tabela a seguir fornece recomendações de periféricos de acordo com o tamanho da sala:

**Periféricos de áudio certificados das Salas do Microsoft Teams**

|Tipo de sala|Número de pessoas|Distância máxima recomendada entre o microfone e a pessoa que está falando|Dispositivo, de acordo com o tamanho máximo da sala|Comentários|
|:-----|:-----|:-----|:-----|:-----|
|**Foco** <br/> 10' x 9'   |2 a 4  |1,5 m  |Logitech Connect  |Os dispositivos Logitech Connect incluem câmeras; por isso, devem ser posicionados na frente da sala (não no centro da mesa) para que possam capturar os participantes locais da reunião. |
|**Small** <br/> 16 "x 16"  |4 a 6  |2.0 m  |Jabra 510 <br/> Sennheiser SP20  |O volume de reprodução pode ser limitado em salas maiores.  |
|**Médio** <br/> 18' x 20'  |6 a 12  |2.4 m  |Jabra 710 <br/> Jabra 810 <br/> Logitech MeetUp <br/> Logitech Group <br/> Polycom Trio <br/> Polycom CX5100 <br/> Sennheiser SP 220 MS <br/> Yamaha YVC-1000MS  |Os dispositivos Logitech MeetUp incluem câmeras; por isso, devem ser posicionados na frente da sala (não no centro da mesa) para que possam capturar os participantes locais da reunião. <br/> Em geral, as salas com tabelas retangulares longas ou em formato de u podem se beneficiar de telefones satélite. <br/> O SP 220 MS deve ser usado na configuração de correntes.  |
|**Large** <br/> 15' x 32'  |12 a 16  |3 m <br/> Essa distância também se aplica à área coberta por cada microfone de satélite conectado.  |Logitech Group + microfones satélite  <br/> Polycom trio + microfones satélite  <br/> Polycom CX5100 + microfones satélite  <br/> Sennheiser SP 220 MS <br/> Yamaha YVC-1000MS + microfones satélite   |Todos os dispositivos de áudio listados nesta linha são compatíveis com opções de microfone satélite. <br/> O CX5100 inclui uma câmera interna de 360 graus; assim, o dispositivo pode ser posicionado no centro da mesa. <br/> O SP 220 MS deve ser usado na configuração de correntes.  |

**Periféricos de vídeo certificados das salas do Microsoft Teams**

|Tipo de sala|Número de pessoas|Dispositivo por tamanho ideal de sala|Comentários|
|:-----|:-----|:-----|:-----|
|**Foco** <br/> 10' x 9'  |2 a 4  |Logitech Connect <br/> Logitech MeetUp <br/> Polycom CX5100  ||
|**Small** <br/> 16 "x 16"  |4 a 6  |Logitech C930e <br/> Logitech MeetUp <br/> Logitech BRIO <br/> Logitech PTZ pro <br/> Polycom MSR <br/> Polycom CX5100  |Logitech PTZ Pro frequentemente combinado com Logitech Group  |
|**Médio** <br/> 18' x 20'  |6 a 12  |Logitech MeetUp <br/> Logitech BRIO <br/> Logitech PTZ pro <br/> Polycom MSR <br/> Polycom CX5100  ||
|**Large** <br/> 15' x 32'  |12 a 16  |Logitech PTZ pro <br/> Polycom MSR <br/> Polycom CX5100  ||

 > [!NOTE]
 > A resolução de tela frontal não deve ser definida como menor do que 1920x1080p.

## <a name="required-software-downloads"></a>Downloads de software necessários

Para criar sua própria imagem de Salas do Microsoft Teams, siga as instruções em [Configurar um console de Salas do Microsoft Teams](console.md). Essas instruções orientarão você durante o download de todo o software necessário para a instalação.

> [!NOTE]
> Os profissionais de TI precisarão acessar os arquivos ISO do Windows 10 Enterprise por meio de um contrato de licenciamento por volume.

[SkypeRoomProvisioningScript ps1](https://go.microsoft.com/fwlink/?linkid=870105) é um download opcional que você pode usar para provisionar contas das Salas do Microsoft Teams.

## <a name="see-also"></a>Confira também

[Procurar todos os pacotes](https://products.office.com/microsoft-teams/across-devices/devices)

[Planejar as Salas do Microsoft Teams](rooms-plan.md)

[Implantar Salas do Microsoft Teams](rooms-deploy.md)

[Configurar um console de Salas do Microsoft Teams](console.md)

[Gerenciar Salas do Microsoft Teams](rooms-manage.md)

[Licenciamento do complemento Skype for Business](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)
