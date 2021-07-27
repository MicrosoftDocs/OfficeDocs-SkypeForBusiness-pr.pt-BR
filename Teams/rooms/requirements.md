---
title: Requisitos das Salas Microsoft Teams
ms.author: dstrome
author: dstrome
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
description: Saiba mais sobre os requisitos de suporte Salas do Microsoft Teams, incluindo a escolha do dispositivo apropriado, microfones, alto-falantes, câmeras e exibições.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3aac58ab2290672217443b539ae26329214b1895
ms.sourcegitcommit: 9879bc587382755d9a5cd63a75b0e7dc4e15574c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/21/2021
ms.locfileid: "53509742"
---
# <a name="microsoft-teams-rooms-requirements"></a>Requisitos das Salas Microsoft Teams

Salas do Microsoft Teams dimensionar para tamanhos de sala diferentes. Salas do Teams usar uma ampla variedade de periféricos de áudio e vídeo certificados com base no tamanho e no uso da sala. Selecionando o dispositivo e o console principais da direita, combinados com microfones, alto-falantes, câmeras e exibições apropriadas para o espaço, você pode implantar o Salas do Microsoft Teams em espaços de qualquer tamanho de pequenos espaços de amontoamento por meio de grandes espaços de conferência e salas de tabuleiro.  O conjunto completo de todos os periféricos de áudio e vídeo certificados disponíveis que podem ser usados para configurar a sua sala está disponível [Mostruário do dispositivo](https://products.office.com/microsoft-teams/across-devices).

Este artigo resume a implantação e os requisitos de configuração do dispositivo para dar suporte às Salas do Microsoft Teams.

Sua implantação envolve a criação de contas conforme descrito em [Implantar Salas do Microsoft Teams](rooms-deploy.md) e a configuração dos consoles de reunião conforme descrito em [Configurar um console de Salas do Microsoft Teams](console.md).

Consulte:

- [Licenciamento do complemento Skype for Business](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing)
- [Opções de licença baseadas em seu plano: Salas do Microsoft Teams](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2)

> [!NOTE]
> As Salas do Microsoft Teams entram no Microsoft Teams, no Skype for Business Server 2019, no Skype for Business Server 2015 ou no Skype for Business Online, e podem participar de reuniões hospedadas por qualquer um desses serviços.
>
> As plataformas anteriores, como o Lync Server 2013, não são compatíveis com as Salas do Microsoft Teams. Salas do Microsoft Teams é suportado em ambientes Microsoft 365 ou Office 365 operados pela 21Vianet ou pelo DoD.
>
> Se você tiver um Exchange Server local, as salas do Microsoft Teams exigirá o uso do Exchange Server 2013 SP1 ou posterior.

## <a name="hardware-requirements"></a>Requisitos de hardware
Uma implantação de hardware inclui uma seleção de um sistema de Sala do Microsoft Teams, combinada com periféricos de áudio e vídeo certificados e uma solução de cabeamento para integrar esses dispositivos.  Essas opções estão descritas aqui.

**Sistemas compatíveis com a Sala do Microsoft Teams**

Todos os pacotes e dispositivos da Sala do Microsoft Teams estão disponíveis em [Mostra de produtos dos Sistemas de Sala](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=20&page=1&filterIds=).

  |Console|Processador|RAM|Disco|
  |:-----|:-----|:-----|:-----|
  |[Crestron Flex UC-M130-T com Intel NUC](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M130-T)|Core i5|8 GB |128 GB |
  |[Crestron Flex UC - B130-T com Intel NUC](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B130-T)|Core i5|8 GB |128 GB |
  |[Crestron Flex UC-B140-T com Intel NUC](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B140-T)|Core i5|8 GB |128 GB |
  [Crestron Flex UC-C140-T com Intel NUC](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C140-T)|I7 principais|8 GB |128 GB|
  |[Crestron Flex UC-M150-T com Intel NUC](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M150-T)  +  [CCS-UCA-MIC](https://www.crestron.com/Products/Audio/Microphones/Wired-Microphones/CCS-UCA-MIC-KIT)|I7 principais|8 GB |128 GB |
  |[Crestron Flex UC-MX150-T com Intel NUC](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-MX150-T)|Core i5|8 GB |128 GB |
   [Crestron Flex UC-B160-T com Intel NUC](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B160-T)|I7 principais|8 GB |128 GB|
  |[Crestron Flex UC-C160-T com Intel NUC](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C160-T)|I7 principais|8 GB|128 GB|
  |[Crestron Flex UC-MMX30-T com UC Presentation E PC ASUS](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-MMX30-T)|Core i5|8 GB |128 GB |
  |[Crestron Flex UC-BX30-T com Emissor de Apresentação de UC (UC-PR) e PC ASUS](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-BX30-T)|Core i5|8 GB |128 GB |
  |[Crestron Flex UC-CX100-T com UC Presentation E PC ASUS](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-CX100-T)|Core i5|8 GB |128 GB |
  |[Crestron Flex UC-B30-T com PC ASUS](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B30-T)|Core i5|8 GB |128 GB |
   |[Crestron Flex UC-C100-T com PC ASUS](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C100-T)|Core i5|8 GB |128 GB |
   |[Crestron Flex UC-M50-T com PC ASUS](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M50-T)|Core i5|8 GB |128 GB |
   |[Crestron Flex UC-M70-T com PC ASUS](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M70-T)|Core i5|8 GB |128 GB |
   |[Crestron Flex UC-MX50-T com PC ASUS](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-MX50-T)|Core i5|8 GB |128 GB |
   |[Crestron Flex UC-MX70-T com PC ASUS](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-MX70-T)|Core i5|8 GB |128 GB |
  |[Crestron Mercury Mini UC-MM30-T](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-MM30-T)|Core i5|8 GB |128 GB |
  |[Dell OptiPlex 7080 com Logitech TAP](https://www.dell.com/work/shop/cty/pdp/spd/optiplex-7080-xe-teams) | I7 principais |16 GB |128 GB|
  |[HP Elite Slice para Salas de Reunião G2](https://www8.hp.com/us/en/elite-family/elite-slice-for-meetings.html) |Core i5 |8 GB |128 GB |
  |[HP Elite Slice G2 Audio Ready com Salas do Microsoft Teams](https://store.hp.com/us/en/pdp/hp-elite-slice-for-meeting-rooms-g2-skype-room-systems-audio-ready?jumpid=cp_r12131_us/en/psg/elite_slice_for_meetings/product/shop-now-eliteslicemeeting-g2-audio) |Core i5 |8 GB |128 GB |
  |[Parceiro de Fatia HP Pronto com o TAP logitech]( https://www.logitech.com/video-collaboration/partners/hp.html)|Core i5|8 GB|128 GB| 
  |[Hub Lenovo ThinkSmart 500](https://www3.lenovo.com/us/en/hub500) |Core i5 |8 GB |128 GB |
  |[Lenovo ThinkSmart Hub](https://news.lenovo.com/pressroom/press-releases/new-thinksmart-hub-collaboration-solution-from-lenovo-helps-organizations-embrace-hybrid-working-model/) |Core i5 |8 GB |128 GB|
  |[Tocar logitech com o Intel NUC](https://www.logitech.com/product/microsoft-rooms)|Core i5|8 GB |128 GB |
  |Computador NUC do Tap logitech Tap e Intel Tiger Canyon |Core i5|8 GB|128 GB|
  |[Logitech Tap e Lenovo ThinkSmart Minúsculo](https://www.logitech.com/video-collaboration/partners/lenovo.html)|Core i5|8 GB |128 GB|
  |[Poly G10-T com Lenovo ThinkSmart Minúsculo](https://www.poly.com/us/en/products/video-conferencing/g/g10) |Core i5| 8 GB | 128 GB|
  |[Yealink MVC300 com Intel NUC](https://www.yealink.com/products_154.html)|Core i5|8 GB |128 GB |
  |[Yealink MVC500 com Intel NUC](https://www.yealink.com/products_126.html)|Core i5|8 GB |128 GB |
  |[Yealink MVC800 com Intel NUC](https://www.yealink.com/products_125.html)|Core i5|8 GB|128 GB|
  |[Yealink MVC900 com Intel NUC](https://www.yealink.com/product/microsoft-teams-room-system-mvc900)|Core i5|8 GB|128 GB|
  |[Yealink MVC 300 II](https://www.yealink.com/product/microsoft-teams-room-system-mvc300II) |Core i5|8 GB | 128 GB|
  |[Yealink MVC400](https://www.yealink.com/product/microsoft-teams-room-system-mvc400)        |Core i5|8 GB | 128 GB|
  |[Yealink MVC 500 II](https://www.yealink.com/product/microsoft-teams-room-system-mvc500II) |Core i5|8 GB | 128 GB|
  |[Yealink MVC 800 II](https://www.yealink.com/product/microsoft-teams-room-system-mvc800II) |Core i5|8 GB | 128 GB|
  |[Yealink MVC 900 II](https://www.yealink.com/product/microsoft-teams-room-system-mvc900II) |Core i5|8 GB | 128 GB|
  |[Yealink MVC840](https://www.yealink.com/product/microsoft-teams-room-system-mvc840) |Core i5|8 GB | 128 GB|
  |[Yealink MVC940](https://www.yealink.com/product/microsoft-teams-room-system-mvc940) |Core i5|8 GB | 128 GB|
  |Yealink MVC660|Core i5|8 GB | 128 GB|
  |Yealink MVC640|Core i5|8 GB | 128 GB|
  |Yealink MVC320|Core i5|8 GB | 128 GB|
  
  
> [!NOTE]
> - Os processadores Core M3 não são compatíveis.
> - É necessário ter uma unidade USB de 32 GB ou maior configurada como mídia de instalação inicializável do Windows para Windows 10 Enterprise.

**Tablet Surface Pro com suporte para sistemas de encaixe**

  |Tablet|Processador|RAM|Disco|
  |:-----|:-----|:-----|:-----|
  |Surface Pro 6| Core i5 |16 GB ou 8 GB |128 GB ou mais |
  |Surface Pro </br>(quinta geração) |Core i5 |8 GB ou 4 GB |128 GB ou mais |
  |Surface Pro 4 |Core i5 |8 GB ou 4 GB |128 GB ou mais |

- Surface Pro dispositivos exigem uma das seguintes opções de estação de encaixe:

  - [Logitech SmartDock](https://www.logitech.com/product/smartdock)
  - [Crestron SR](https://www.crestron.com/products/line/sr-for-skype-for-business-room-system )
  - [Polycom MSR](https://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.html)

### <a name="certified-firmware-versions-for-usb-audio-and-video-peripherals"></a>Versões de firmware certificadas para periféricos USB e de áudio

Esses dispositivos estão disponíveis na [Mostruário de produtos de acessórios para Sistemas de Salas](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=73&page=1&filterIds=)[https://office.com/teamsdevices](https://office.com/teamsdevices).

|Periférico das Salas do Microsoft Teams|Versão de firmware certificado | A câmera compatível com o uso da câmera de conteúdo|
|:--- |:--- | :--- |
|[Aver VC520 Pro Camera + Speakerphone](https://www.averusa.com/products/conference-camera/vc520pro) |1004.35|
|[Aver VB342+ Camera Soundbar](https://www.averusa.com/products/conference-camera/vb342plus) | Soundbar: 0.0.0000.97|
|[Aver CAM 540](https://www.averusa.com/products/conference-camera/cam540) |0.0.6002.83 |
|[Aver CAM 520 Pro](https://www.averusa.com/products/conference-camera/cam520pro) |0.0.1000.73 |
|[Aver CAM 520 Pro 2](https://www.averusa.com/products/conference-camera/cam520pro2) |0.0.7200.3 |
|[Aver CAM 130](https://www.averusa.com/products/conference-camera/cam130) |0.0.7400.03 |
|[Bose Video Bar VB1](https://pro.bose.com/en_us/products/conferencing/videobars/bose-videobar-vb1.html?mc=25_PS_VB_BO_00_BI_&&msclkid=fc99b79880f714727a63e86ea0e5642a&utm_source=bing&utm_medium=cpc&utm_campaign=US%20-%20Brand_Videobar%20VB1_Exact&utm_term=bose%20videobar%20vb1&utm_content=Bose%20Videobar%20VB1&gclid=fc99b79880f714727a63e86ea0e5642a&gclsrc=3p.ds) |19.2|
|[Biamp Devio SCR-20CX Web-Based de conferência com microfone de teto](https://www.biamp.com/products/product-families/devio/huddle-room-solutions) |2.2.0.9|
|[Biamp Devio SCR-20TX Web-Based Deconferência com Microfone de Mesa](https://www.biamp.com/products/product-families/devio/huddle-room-solutions) |2.2.0.9 |
|[Crestron Huddly IQ](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Accessories/CCS-CAM-USB-F-400)   | 1.02.09.33901  | 
|[Tela Huddly](https://www.huddly.com/blog/say-hello-to-huddly-canvas-our-latest-ai-technology-for-content-capture-and-enhancement/) | 1.3.25 |  &#x2714; |
|[Huddly IQ](https://www.huddly.com/conference-cameras/iq/) |1.3.22|
|[Huddly IQ Lite](https://www.huddly.com/conference-cameras/iq/) |1.3.29|
|[Câmera de IQ Huddly](https://www.huddly.com/conference-cameras/iq/) |1.3.27|
|[Câmera Jabra Panacast3](https://www.jabra.com/business/video-conferencing/jabra-panacast)|1.3.9.12|
|[Barra de vídeo do Jabra Panacast 50](https://www.jabra.com/business/video-conferencing/jabra-panacast-50)|1.9.3|
|[Câmera de câmera Lenovo ThinkSmart](https://www.lenovo.com/us/en/accessories-and-monitors/webcams-and-video/webcams/SMARTOF-BO-ThinkSmart-Cam/p/4Y71C41660)|1.0.111.4|
|[Barra Lenovo ThinkSmart](https://www.lenovo.com/us/en/virtual-reality-and-smart-devices/smart-collaboration/thinksmart/ThinkSmart-Bar/p/11SP1TSSDBR)|0.9.3|
|Lenovo ThinkSmart Bar Expand XL|5.9.5|
|[Logitech brio](https://www.logitech.com/product/brio)   |V 2.2.50| &#x2714; |
|[Logitech 930e](https://www.logitech.com/product/c930e-webcam)   | 8.0.914   | &#x2714; |
|[Logitech Rally](https://www.logitech.com/product/rally-ultra-hd-conferencecam)   |1.2.4 |
|[Barra de Rali logitech](https://www.logitech.com/products/video-conferencing/room-solutions/rallybar.960-001308.html)   |10.3.82|
|[Logitech MeetUp](https://www.logitech.com/product/meetup-conferencecam)   |Audio — 1.0.172 <br/> Video — 1.0.156  |
|[Logitech ConferenceCam Connect](https://www.logitech.com/product/conferencecam-connect)   |1.1.248.0 <br/> 1.1.684   |
|[Logitech Group ](https://www.logitech.com/product/conferencecam-group)   |8.5.778   |
|[Logitech PTZ pro](https://www.logitech.com/product/conferencecam-ptz-pro)   | 1.1.219   |
|[Logitech PTZ Pro 2](https://www.logitech.com/product/conferencecam-ptz-pro2)   |
|[Nureva HDL300](https://www.nureva.com/audio-conferencing/hdl300) |2.3.6|
|[Câmera Poly Eagle Eye Cube](https://www.polycom.com/products-services/hd-telepresence-video-conferencing/realpresence-accessories/eagleeye-cameras.html)  |1.2.0 |
|[Polycom EagleEye IV](https://www.poly.com/us/en/products/video-conferencing/eagleeye/eagleeye-iv)   |1.0.0   |
|[Polycom CX5100](https://www.polycom.com/products-services/products-for-microsoft/lync-optimized/cx5100-unified-conference-station.mdl)   | 1.2.0.70232   |
|[Diretor de olho Polycom Eagle II](https://www.polycom.com/hd-video-conferencing/peripherals/eagleeye-director-ii.html)|2.1.0.10|
|[Polycom Studio](https://www.polycom.com/hd-video-conferencing/room-video-systems/polycom-studio.html)|1.1.2.000570|
|[Poly Sync 40](https://www.poly.com/us/en/products/phones/sync/sync-40)|0.0.94.1461|
|[Poly Sync 60](https://www.poly.com/us/en/products/phones/sync/sync-60)|0.0.150.1671|
|[Polycom trio 8500/8800](https://www.polycom.com/voice-conferencing-solutions/conference-phones/trio.html)   |5.7.2.3205|
|[Poly Trio C60](https://www.poly.com/us/en/products/phones/trio/trio-c60)  |5.9.5.3066|
|[Barra de vídeo Poly Studio P15](https://www.poly.com/us/en/products/video-conferencing/studio-p/studio-p15)|1.2.0.000287 |
|[EPOS SP 220 MS](http://no-no.sennheiser.com/dual-speakerphones-sp-220-ms-uc)   |2.0.12.0   |
|[EPOS SP20](https://www.eposaudio.com/en/us/enterprise/products/sp-20-ml-142ee5ca-speakerphone-1000226)   |1.2.15   |
|[EPOS SP30](https://www.eposaudio.com/en/us/enterprise/products/sp-30-78c0cecc-bluetooth-speakerphone-1000223)   |2.1.52  |
|[EPOS SP30T](https://www.eposaudio.com/en/us/enterprise/products/sp-30t-b949fe9a-bluetooth-speakerphone-1000225)  |3.2.63  |
|[EPOS Expand 80T + 2 Extension Mics](https://www.eposaudio.com/en/us/enterprise/products/expand-80t-bluetooth-speakerphone-1000203) |Speakerphone — 4.6.55 <br/> Microfone de extensão — 0.2.314|
|[EPOS Expand Capture 5](https://www.eposaudio.com/en/us/enterprise/products/expand-capture-5-speakerphone-1000895)  |1.0.1|
|[Jabra 510](http://www.jabra.com/support/Jabra-SPEAK&trade;-510_7510-209)   |2.10.0   |
|[Jabra 710](http://www.jabra.com/business/speakerphones/jabra-speak-series/jabra-speak-710)   |1.8.0   |
|[Jabra 810](http://www.jabra.com/supportpages/jabra-speak-810)   |1.2.23   |
|[Yamaha YVC-1000](http://www.yamaha.com/products/en/communication/usb_conference_speakerphones/yvc-1000/)   |100c   |
|[Yealink CP900](https://www.yealink.com/products_150.html) |100.20.0.29 |
|[Yealink UVC30](https://www.yealink.com/product/microsoft-teams-room-system-uvc30)| 105.420.0.11 |  &#x2714; |
|[Yealink UVC40 Barra de vídeo all-in-one](https://www.yealink.com/product/usb-videobar-uvc40) |128.410.0.10|  
|[Processador de Audioconferência Shure Intellimix P300](https://www.shure.com/products/mixers/p300)+</br></br> [Shure MXA 310 ](https://www.shure.com/products/microphones/mxa310) | 4.1 |
|[Processador de Audioconferência Shure Intellimix P300](https://www.shure.com/products/mixers/p300) + </br></br> [Shure MXA 910 com Intellimix Ceiling Array Mic](https://www.shure.com/products/microphones/mxa910) | 4.1|
|[Processador de Audioconferência Shure Intellimix P300](https://www.shure.com/products/mixers/p300)+</br></br> [Microfone da matriz de tabelas do MXA 310 de Shure ](https://www.shure.com/products/microphones/mxa310) +</br></br> [Alto-falante de Teto MXN5W-C](https://www.shure.com/products/loudspeakers/mxn5)| P300 DSP: 4.1.11 </br> MXA310 Table Array mic: 4.1.41 </br> Alto-falante MXN5W-C: 1.0.4 |
|[Processador de Audioconferência Shure Intellimix P300](https://www.shure.com/products/mixers/p300) + </br></br> [Shure MXA 910 com Microfone de Matriz de Teto Intellimix](https://www.shure.com/products/microphones/mxa910) +</br></br> [Alto-falante de Teto MXN5W-C](https://www.shure.com/products/loudspeakers/mxn5)| P300 DSP: 4.1.11 </br> MXA910 Microfone da Matriz de Teto: 4.1.41 </br> Alto-falante MXN5W-C: 1.0.4 |
|[Microfone de Matriz Linear de Tabela de 710 2ft de Shure MXA](https://www.shure.com/products/microphones/mxa710) + </br></br> [Processador de Audioconferência Shure Intellimix P300](https://www.shure.com/products/mixers/p300) +</br></br> [Alto-falante de teto MXN5-C](https://www.shure.com/products/loudspeakers/mxn5)| MXA710 2ft Table Linear Array Mic: 1.2.0 </br> P300 DSP: 4.4.8 </br> Alto-falante MXN5-C: 1.1.1 |
|[Microfone de matriz linear de parede de 710 4ft de Shure MXA](https://www.shure.com/products/microphones/mxa710) + </br></br> [Processador de Audioconferência Shure Intellimix P300](https://www.shure.com/products/mixers/p300) +</br></br> [Alto-falante de teto MXN5-C](https://www.shure.com/products/loudspeakers/mxn5)| MXA710 4ft Wall Linear Array Mic: 1.2.0 </br> P300 DSP: 4.4.8 </br> Alto-falante MXN5-C: 1.1.1 |
|[Shure MXA 910 com Microfone da Matriz de Teto Intellimix](https://www.shure.com/products/microphones/mxa910) + </br> [Software de sala Dore Intellimix](https://www.shure.com/products/software/intellimix_room) +</br> [Crestron UC-C100-T](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C100-T)| Software de sala Dore Intellimix: 3.0.4.14 </br> Shure MXA 910 com Microfone da Matriz de Teto Intellimix: 4.4.11 </br> Alto-falantes do Shure MXN5-C: 1.2.1 </br> Crestron UC-C100-T: versão do sistema operacional windows IOT 19h2/20h2 com versão do aplicativo MTR 4.8.31.0 </br> BIOS: ASUS Tek Computer INC 9934 27/08/2020 </br> CPU: i5-9500TCPU </br> Memória Física: 8 GB de RAM |
|[Biamp Tesira Fore AVB VT4 Fixed audio DSP](https://www.biamp.com/products/tesira-fixed-audio-dsp)+ &Dagger;</br></br> [Sennheiser TeamConnect Ceiling 2 Microphone](https://sennheiser.com/tcc2)+ &Dagger;</br></br> [Tesira EX-UBT](https://www.biamp.com/products/tesira/tesira-expanders) &Dagger; |  DSP Biamp: 3.12.0.15  </br></br> TCC2: 1.3.3 </br></br> EX-UBT: 3.12.0.15 |
|[Biamp Tesira FORTÉ AVB VT4 Audio DSP](https://www.biamp.com/products/tesira-fixed-audio-dsp)+ </br></br>[Microfone de teto do Biamp Parlé TCM-XA](https://www.biamp.com/products/product-families/parle/parle-microphones)+</br></br> [Biamp Desono C-IC6 ceiling mounted loudspeaker](https://www.biamp.com/products/tesira-speakers)| Versão FW de áudio: 3.15|
|[Biamp TesiraFORTE AVB VT4](https://www.biamp.com/products/tesira-fixed-audio-dsp)+ </br></br>[Parle TTM-X(Table Mic)](https://www.biamp.com/products/product-families/parle/parle-microphones)+</br></br>[Ex-UBT]() |Versão FW de áudio: 3.15|
|[Bose ControlSpace EX-440C DSP + </br>Bose P2600A AmpLink Amplifier +</br> Sennheiser TCC2 Ceiling Microphone + </br> Bose EdgeMax EM180 Ceiling Speaker](https://pro.bose.com/en_us/solutions/bose-work/es1-ceiling-audio-solution.html)|  Bose DSP: 2,290  </br> P2600A: 1,160  </br> TCC2:1.4.2  |  |
|[Bose ControlSpace EX-440C DSP + </br> Bose P2600A AmpLink Amplificador + Microfone de Teto sennheiser TCC2 + Alto-falante de teto </br> Bose DesignMax DM2C-P](https://pro.bose.com/en_us/solutions/bose-work/es1-ceiling-audio-solution.html)|  Bose DSP: 2,290  </br> P2600A: 1,160  </br> TCC2:1.4.2  |  |
|[Bose ControlSpace EX-1280C DSP](https://pro.bose.com/en_us/products/signal_processing_and_networking/controlspace_ex/cs_ex_1280c.html#v=cs_ex_1280c_black) +</br>Bose P2600A AmpLink Amplificador +</br> [Microfone de teto TCC2 sennheiser](https://pro.bose.com/en_us/solutions/bose-work/es1-ceiling-audio-solution.html) +</br> [Alto-falante de teto DesignMax DM2C -LP](https://pro.bose.com/en_us/products/loudspeakers/background_foreground/designmax/designmax_dm2c_lp.html#v=designmax_dm2c_lp_black) | Bose DSP: 2,290  </br> P2600A: 1,160  </br> TCC2:1.4.2  | 
|[Bose ControlSpace EX-1280C DSP](https://pro.bose.com/en_us/products/signal_processing_and_networking/controlspace_ex/cs_ex_1280c.html#v=cs_ex_1280c_black) +</br>Bose P2600A AmpLink Amplificador+</br> [Microfone de teto TCC2 sennheiser](https://pro.bose.com/en_us/solutions/bose-work/es1-ceiling-audio-solution.html) +</br> [Alto-falante de teto EdgeMax EM180](https://pro.bose.com/en_us/products/loudspeakers/background_foreground/edgemax/edgemax_em180.html#v=edgemax_em180_white) | Bose DSP: 2,290  </br> P2600A: 1,160  </br> TCC2:1.4.2  |
|[QSC Q-SYS Core 110f](https://www.qsc.com/systems/products/q-sys-ecosystem/products-peripherals-accessories/q-sys-cores/core-110f/) +</br> [Microfone de teto TCC2 sennheiser]() +</br> [QSC EnergyStar Power Amplificador SPA2-60](https://www.qsc.com/systems/products/power-amplifiers/energystar-amplifiers/spa-series/spa2-60/) +</br> [P-SYS NS Series Network Switch NS-1108P](https://www.qsc.com/systems/products/q-sys-ecosystem/products-peripherals-accessories/network-switches/q-sys-ns-series-network-switches/) + </br> [Alto-falantes AD-S402T de montagem de superfície de coluna QSC](https://www.qsc.com/systems/products/loudspeakers/column-surface-mount-loudspeakers/acousticdesigntm-series-column-surface-mount/ad-s402t/) +</br> [Câmera QSC PTZ 20x60](https://www.qsc.com/systems/products/q-sys-ecosystem/products-peripherals-accessories/conference-room-integration/ptz-ip-conference-cameras/) |P-sys Designer: 8.4.0.1 </br> <br> TCC2 : 1.5.1 Dante 1.2.0 </br>  <br> Não disponível </br>  <br>N1100v6.4.2.8 </br> Não disponível </br> <br> 6.3.2.2|
|[QSC Q-SYS Core 110f](https://www.qsc.com/systems/products/q-sys-ecosystem/products-peripherals-accessories/q-sys-cores/core-110f/) +</br> [Microfone de teto TCC2 sennheiser]() +</br> [QSC EnergyStar Power Amplificador SPA2-60](https://www.qsc.com/systems/products/power-amplifiers/energystar-amplifiers/spa-series/spa2-60/) +</br> [P-SYS NS Series Network Switch NS-1108P](https://www.qsc.com/systems/products/q-sys-ecosystem/products-peripherals-accessories/network-switches/q-sys-ns-series-network-switches/) + </br> [Alto-falantes AD-C6T-LP de montagem de superfície de coluna QSC](https://www.qsc.com/systems/products/loudspeakers/ceiling-mount-loudspeakers/acousticdesigntm-series-ceiling-mount/ad-c6t-lp/?L=) +</br> [Câmera QSC PTZ 20x60](https://www.qsc.com/systems/products/q-sys-ecosystem/products-peripherals-accessories/conference-room-integration/ptz-ip-conference-cameras/) |P-sys Designer: 8.4.0.1 </br> <br> TCC2 : 1.5.1 Dante 1.2.0 </br>  <br> Não disponível </br>  <br>N1100v6.4.2.8 </br> Não disponível </br> <br> 6.3.2.2|
|[Processador QSC Q-SYS Core 8 Flex](https://www.qsc.com/solutions-products/q-sys-ecosystem/processing/core-8-flex/) +</br> [Câmera QSC PTZ 20x60](https://www.qsc.com/solutions-products/q-sys-ecosystem/video/ptz-ip-conference-cameras/) +</br> [Microfone de teto TCC2 sennheiser](https://sennheiser.com/tcc2) +</br> [QSC Ceiling Speaker AD-C6T-LP](https://www.qsc.com/solutions-products/loudspeakers/installed/passive/ceiling-mount/acousticdesign-series/ad-c6t-lp/) |QSC PTZ IP 20x60 Câmera: 9,0 </br> QSC Q-SYS Core 8-Flex: Q-SYS Designer 9.0.1-2104.002 </br> QSC Q-SYS Nano: Q-SYS Designer 9.0.1-2104.002 </br> Microfone de teto TCC2 sennheiser: TCC2 - 1.5.1 Dante 1.2.0 </br> Amplificadores EnergyStar da série SPA: N/A </br> Alto-falantes da série AcousticDesign: N/A|
|[Processador Nano QSC Q-SYS Core](https://www.qsc.com/solutions-products/q-sys-ecosystem/processing/core-nano/) +</br> [Câmera QSC PTZ 20x60](https://www.qsc.com/solutions-products/q-sys-ecosystem/video/ptz-ip-conference-cameras/) +</br> [Microfone de teto TCC2 sennheiser](https://sennheiser.com/tcc2) +</br> [QSC Ceiling Speaker AD-C6T-LP](https://www.qsc.com/solutions-products/loudspeakers/installed/passive/ceiling-mount/acousticdesign-series/ad-c6t-lp/) |QSC PTZ IP 20x60 Câmera: 9,0 </br> QSC Q-SYS Core 8-Flex: Q-SYS Designer 9.0.1-2104.002 </br> QSC Q-SYS Nano: Q-SYS Designer 9.0.1-2104.002 </br> Microfone de teto TCC2 sennheiser: TCC2 - 1.5.1 Dante 1.2.0 </br> Amplificadores EnergyStar da série SPA: N/A </br> Alto-falantes da série AcousticDesign: N/A|


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
