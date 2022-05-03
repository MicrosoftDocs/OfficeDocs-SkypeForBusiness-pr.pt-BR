---
title: Requisitos das Salas Microsoft Teams
ms.author: czawideh
author: cazawideh
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 6b2b2684-8e9e-49ea-8c46-1c690964f982
ms.collection:
- M365-collaboration
description: Saiba mais sobre os requisitos de suporte Salas do Microsoft Teams, incluindo a escolha do dispositivo, microfones, alto-falantes, câmeras e monitores apropriados.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 56d2eca675a4f7ce092b15c66f9f79b8c28be17f
ms.sourcegitcommit: 9f7372f7568b4275169590510d2b7a0c0ad7577b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2022
ms.locfileid: "65171737"
---
# <a name="microsoft-teams-rooms-requirements"></a>Requisitos das Salas Microsoft Teams

Salas do Microsoft Teams dimensionar para tamanhos de sala diferentes. Salas do Teams uma ampla variedade de periféricos de áudio e vídeo certificados com base no tamanho e no uso da sala. Ao selecionar o dispositivo principal e o console corretos, combinados com microfones, alto-falantes, câmeras e telas apropriadas para o espaço, você pode implantar o Salas do Microsoft Teams em espaços de qualquer tamanho, desde pequenos espaços de grupo até espaços de conferência grandes e salas de reuniões.  O conjunto completo de todos os periféricos de áudio e vídeo certificados disponíveis que podem ser usados para configurar a sua sala está disponível [Mostruário do dispositivo](https://products.office.com/microsoft-teams/across-devices).

Este artigo resume a implantação e os requisitos de configuração do dispositivo para dar suporte às Salas do Microsoft Teams.

Sua implantação envolve a criação e a configuração da conta de Salas do Teams conforme descrito em [Implantar Salas do Microsoft Teams](rooms-deploy.md).

Consulte:

- [Opções de licença baseadas em seu plano: Salas do Microsoft Teams](rooms-licensing.md)

> [!NOTE]
> Salas do Microsoft Teams entrar no Microsoft Teams, Skype for Business Server 2019 ou Skype for Business Server 2015 e pode ingressar em reuniões hospedadas por qualquer um desses serviços.
>
> As plataformas anteriores, como o Lync Server 2013, não são compatíveis com as Salas do Microsoft Teams. Salas do Microsoft Teams não tem suporte em ambientes Microsoft 365 ou Office 365 operados por ambientes 21Vianet ou DoD.
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
  |[Crestron Flex UC-M150-T com Intel NUC](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M150-T) +  [CCS-UCA-MIC](https://www.crestron.com/Products/Audio/Microphones/Wired-Microphones/CCS-UCA-MIC-KIT)|I7 principais|8 GB |128 GB |
  |[Crestron Flex UC-MX150-T com Intel NUC](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-MX150-T)|Core i5|8 GB |128 GB |
   [Crestron Flex UC-B160-T com Intel NUC](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B160-T)|I7 principais|8 GB |128 GB|
  |[Crestron Flex UC-C160-T com Intel NUC](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C160-T)|I7 principais|8 GB|128 GB|
  |[Crestron Flex UC-MMX30-T com Transmissor de Apresentação UC (UC-PR) e PC ASUS](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-MMX30-T)|Core i5/i7|8 GB |128 GB |
  |[Crestron Flex UC-BX30-T com Transmissor de Apresentação UC (UC-PR) e PC ASUS](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-BX30-T)|Core i5/i7|8 GB |128 GB |
  |[Crestron Flex UC-CX100-T com Transmissor de Apresentação UC (UC-PR) e PC ASUS](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-CX100-T)|Core i5/i7|8 GB |128 GB |
  |[Crestron Flex UC-B30-T com PC ASUS](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B30-T)|Core i5/i7|8 GB |128 GB |
   |[Crestron Flex UC-C100-T com PC ASUS](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C100-T)|Core i5/i7|8 GB |128 GB |
   |[Crestron Flex UC-M50-T com PC ASUS](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M50-T)|Core i5/i7|8 GB |128 GB |
   |[Crestron Flex UC-M70-T com PC ASUS](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M70-T)|Core i5/i7|8 GB |128 GB |
   |[Crestron Flex UC-MX50-T com PC ASUS](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-MX50-T)|Core i5/i7|8 GB |128 GB |
   |[Crestron Flex UC-MX70-T com PC ASUS](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-MX70-T)|Core i5/i7|8 GB |128 GB |
   |Crestron FLEX UC-B30-T com Dell OPTIPLEX|Core i5|8 GB|128 GB|
   |Crestron FLEX UC-Bx30-T com Dell OPTIPLEX|Core i5|8 GB|128 GB|
   |Crestron FLEX UC-MM30-T com Dell OPTIPLEX|Core i5|8 GB|128 GB|
   |Crestron FLEX UC-MMX30-T com Dell OPTIPLEX|Core i5|8 GB|128 GB|
   |Crestron FLEX UC-M50-T com Dell OPTIPLEX|Core i5|8 GB|128 GB|
   |Crestron FLEX UC-MX50-T com Dell OPTIPLEX|Core i5|8 GB|128 GB|
   |Crestron FLEX UC-M70-T com Dell OPTIPLEX|Core i5|8 GB|128 GB|
   |Crestron FLEX UC-MX70-T com Dell OPTIPLEX|Core i5|8 GB|128 GB|
   |Crestron FLEX UC-C100-T com Dell OPTIPLEX|Core i5|8 GB|128 GB|
   |Crestron FLEX UC-CX100-T com Dell OPTIPLEX|Core i5|8 GB|128 GB|
  |[Crestron Mercury Mini UC-MM30-T](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-MM30-T)|Core i5|8 GB |128 GB |
  |[Dell OptiPlex 7080 com Logitech TAP](https://www.dell.com/en-us/work/shop/cty/pdp/spd/optiplex-7080-xe-teams) | I7 principais |16 GB |128 GB|
  |[HP Elite Slice para Salas de Reunião G2](https://www8.hp.com/us/en/elite-family/elite-slice-for-meetings.html) |Core i5 |8 GB |128 GB |
  |[HP Elite Slice G2 Audio Ready com Salas do Microsoft Teams](https://store.hp.com/us/en/pdp/hp-elite-slice-for-meeting-rooms-g2-skype-room-systems-audio-ready?jumpid=cp_r12131_us/en/psg/elite_slice_for_meetings/product/shop-now-eliteslicemeeting-g2-audio) |Core i5 |8 GB |128 GB |
  |[HP Slice Partner Ready with Logitech TAP]( https://www.logitech.com/video-collaboration/partners/hp.html)|Core i5|8 GB|128 GB| 
  | Hub Lenovo ThinkSmart 500 |Core i5 |8 GB |128 GB |
  |[Lenovo ThinkSmart Hub](https://news.lenovo.com/pressroom/press-releases/new-thinksmart-hub-collaboration-solution-from-lenovo-helps-organizations-embrace-hybrid-working-model/) |Core i5 |8 GB |128 GB|
  |Lenovo ThinkSmart Core Kit |Core i5|8 GB|128 GB|
  |[Logitech Tap com Intel NUC](https://www.logitech.com/product/microsoft-rooms)|Core i5|8 GB |128 GB |
  |Logitech Tap e Intel Tiger Canyon NUC PC |Core i5|8 GB|128 GB|
  |Logitech TAP Console with Lenovo Core Compute |Core i5|8 GB|128 GB|
  |[Logitech Tap e Lenovo ThinkSmart Tiny](https://www.logitech.com/video-collaboration/partners/lenovo.html)|Core i5|8 GB |128 GB|
  |[Poly G10-T com Lenovo ThinkSmart Tiny](https://www.poly.com/us/en/products/video-conferencing/g/g10) |Core i5| 8 GB | 128 GB|
  |Console do Poly GC8 com Lenovo Thinksmart Core|Core i5|8 GB|128 GB|
  |Console do Poly GC8 com Dell Optiplex 7080|Core i5|8 GB|128 GB|
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
  |Yealink MVC340|Core i5|8 GB | 128 GB|
  
  
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
|[Aver VC520 Pro Câmera + Viva-voz](https://www.averusa.com/products/conference-camera/vc520pro) |1004.35|
|[Sistema de Conferência Aver VC520 PRO2](https://www.averusa.com/products/conference-camera/vc520pro2) | 00.0.7200.79 |
|[Barra de Som da Câmera do Aver VB342+](https://www.averusa.com/products/conference-camera/vb342plus) | Soundbar: 0.0.0000.97|
|[Aver CAM 540](https://www.averusa.com/products/conference-camera/cam540) |0.0.6002.83 |
|[Aver CAM 520 Pro](https://www.averusa.com/products/conference-camera/cam520pro) |0.0.1000.73 |
|[Aver CAM 520 Pro 2](https://www.averusa.com/products/conference-camera/cam520pro2) |0.0.7200.3 |
|[Aver CAM 130](https://www.averusa.com/products/conference-camera/cam130) |0.0.7450.02 | &#x2714; |
|[Barra de Som da Câmera VB130 do Aver](https://www.averusa.com/products/conference-camera/vb130) |0.0.7300.71 |
|[Bose Video Bar VB1](https://pro.bose.com/en_us/products/conferencing/videobars/bose-videobar-vb1.html?mc=25_PS_VB_BO_00_BI_&&msclkid=fc99b79880f714727a63e86ea0e5642a&utm_source=bing&utm_medium=cpc&utm_campaign=US%20-%20Brand_Videobar%20VB1_Exact&utm_term=bose%20videobar%20vb1&utm_content=Bose%20Videobar%20VB1&gclid=fc99b79880f714727a63e86ea0e5642a&gclsrc=3p.ds) |19.2|
|[Biamp Devio SCR-20CX Web-Based Hub de Conferência com Microfone de Teto](https://www.biamp.com/products/product-families/devio/huddle-room-solutions) |2.2.0.9|
|[Biamp Devio SCR-20TX Web-Based Hub de Conferência com Microfone tabletop](https://www.biamp.com/products/product-families/devio/huddle-room-solutions) |2.2.0.9 |
|[Crestron Huddly IQ](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Accessories/CCS-CAM-USB-F-400)   | 1.02.09.33901  | 
|[Tela de Huddly](https://www.huddly.com/blog/say-hello-to-huddly-canvas-our-latest-ai-technology-for-content-capture-and-enhancement/) | 1.3.25 |  &#x2714; |
|[Huddly IQ](https://www.huddly.com/conference-cameras/iq/) |1.3.22|
|[Huddly IQ Lite](https://www.huddly.com/conference-cameras/iq/) |1.3.29|
|[Câmera do Huddly IQ](https://www.huddly.com/conference-cameras/iq/) |1.3.27|
|Câmera Huddly L1 com [kit Crestron UC-C100-T MTR](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C100-T) | Câmera de Huddly L1: 1.2.1 </br> Crestron UC-C100-T com computação ASUS Tek Computer INC 9934 1.0.20.246 ou superior |
|Câmera Huddly L1 com [kit Crestron UC-CX100-T](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-CX100-T) MTR-W | Huddly L1 Camera: 1.2.9 </br> Crestron UC-CX100-T com ASUS Tek Computer INC 9934 1.00.20.246 ou superior |
|Câmera Huddly L1 com kit Crestron UC-M70-T MTR | Câmera de Huddly L1: 1.2.1 </br> Crestron UC-M70-T com a computação 1.0.20.246 ou superior do ASUS Tek Computer INC 9934 |
|Câmera Huddly L1 com kit Crestron UC-MX70-T MTR | Câmera de Huddly L1: 1.2.1 </br> Crestron UC-MX70-T com computação ASUS Tek Computer INC 9934 1.0.20.246 ou superior |
|[Câmera Jabra Panacast3](https://www.jabra.com/business/video-conferencing/jabra-panacast)|1.3.9.12|
|[Barra de Vídeo do Jabra Panacast 50](https://www.jabra.com/business/video-conferencing/jabra-panacast-50)|1.13.7| &#x2714; |
|[Lenovo ThinkSmart Câmera de Câmera](https://www.lenovo.com/us/en/accessories-and-monitors/webcams-and-video/webcams/SMARTOF-BO-ThinkSmart-Cam/p/4Y71C41660)|1.0.111.4|
|[Lenovo ThinkSmart Bar](https://www.lenovo.com/us/en/virtual-reality-and-smart-devices/smart-collaboration/thinksmart/ThinkSmart-Bar/p/11SP1TSSDBR)|0.9.3|
|Lenovo ThinkSmart Bar Expand XL|5.9.5|
|[Logitech brio](https://www.logitech.com/product/brio)   |V 2.2.50| &#x2714; |
|[Logitech 930e](https://www.logitech.com/product/c930e-webcam)   | 8.0.914   | &#x2714; |
|[Logitech Rally](https://www.logitech.com/product/rally-ultra-hd-conferencecam)   |1.2.4 |
|[Logitech Rally Bar](https://www.logitech.com/products/video-conferencing/room-solutions/rallybar.960-001308.html)   |10.3.82|
|[Logitech Rally Bar Mini](https://www.logitech.com/en-us/products/video-conferencing/room-solutions/rallybarmini.960-001336.html) |10.5.880|
|[Logitech MeetUp](https://www.logitech.com/product/meetup-conferencecam)   |Audio — 1.0.172 <br/> Video — 1.0.156  |
|[Logitech ConferenceCam Connect](https://www.logitech.com/product/conferencecam-connect)   |1.1.248.0 <br/> 1.1.684   |
|[Logitech Group ](https://www.logitech.com/product/conferencecam-group)   |8.5.778   |
|[Logitech PTZ pro](https://www.logitech.com/product/conferencecam-ptz-pro)   | 1.1.219   |
|[Logitech PTZ Pro 2](https://www.logitech.com/product/conferencecam-ptz-pro2)   |
|[Logitech Scribe](https://www.logitech.com/en-us/products/video-conferencing/room-solutions/scribe.960-001332.html) | 1.1.1 | &#x2714; |
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
|[Barra de Vídeo do Poly Studio P15](https://www.poly.com/us/en/products/video-conferencing/studio-p/studio-p15)|1.2.0.000287 |
|[Câmera poly Studio E70](https://www.poly.com/us/en/products/video-conferencing/studio/studio-e70)|1.1|
|[EPOS SP 220 MS](http://no-no.sennheiser.com/dual-speakerphones-sp-220-ms-uc)   |2.0.12.0   |
|[EPOS SP20](https://www.eposaudio.com/en/us/enterprise/products/sp-20-ml-142ee5ca-speakerphone-1000226)   |1.2.15   |
|[EPOS SP30](https://www.eposaudio.com/en/us/enterprise/products/sp-30-78c0cecc-bluetooth-speakerphone-1000223)   |2.1.52  |
|[EPOS SP30T](https://www.eposaudio.com/en/us/enterprise/products/sp-30t-b949fe9a-bluetooth-speakerphone-1000225)  |3.2.63  |
|[EPOS Expanda 80T + 2 microfones de extensão](https://www.eposaudio.com/en/us/enterprise/products/expand-80t-bluetooth-speakerphone-1000203) |Viva-voz — 4.6.55 <br/> Microfone de extensão — 0.2.314|
|[EPOS Expand Capture 5](https://www.eposaudio.com/en/us/enterprise/products/expand-capture-5-speakerphone-1000895)  |1.0.1|
|[Extron DMP128 PLUS C V AT DSP System (DMP 128 Plus C V AT, DMP 128 Plus C AT, DMP 128 Plus C V, DMP 128 Plus C, DMP 128 Plus AT, DMP 128 Plus, DMP 128 FlexPlus C AT, DMP 128 FlexPlus C V AT)](https://www.extron.com/product/dmp128plus) | 1.08 |
|[Extron DMP 64 PLUS C V AT DSP System (DMP 64 Plus C V AT, DMP 64 Plus C AT, DMP 64 Plus C V, DMP 64 Plus C)](https://www.extron.com/product/dmp64plus) | 1.08|
|[Jabra 510](http://www.jabra.com/support/Jabra-SPEAK&trade;-510_7510-209)   |2.10.0   |
|[Jabra 710](http://www.jabra.com/business/speakerphones/jabra-speak-series/jabra-speak-710)   |1.8.0   |
|[Jabra 810](http://www.jabra.com/supportpages/jabra-speak-810)   |1.2.23   |
|[Yamaha YVC-1000](http://www.yamaha.com/products/en/communication/usb_conference_speakerphones/yvc-1000/)   |100c   |
|[Yamaha YVC-1000MS](https://uc.yamaha.com/products/conference-phones/usb-bluetooth/) |1.0.0 |
|[Solução de teto ADECIA yamaha](https://uc.yamaha.com/products/microphone-systems/adecia/)|1.2.0|
|[Solução Yamaha ADECIA Tabletop](https://uc.yamaha.com/products/adecia/adecia-tabletop/)|E1.2.0 para microfone de tabela, D1.2.0 para processador (tanto o mesmo conteúdo da V1.5.1)|
|[Yealink CP900](https://www.yealink.com/products_150.html) |100.20.0.29 |
|[Yealink UVC30](https://www.yealink.com/product/microsoft-teams-room-system-uvc30)| 105.420.0.11 |  &#x2714; |
|[Barra de vídeo Yealink UVC34 All-in-One](https://www.yealink.com/product/usb-videobar-uvc34) | 265.410.0.9 |
|[Yealink UVC40 Barra de vídeo tudo em um](https://www.yealink.com/product/usb-videobar-uvc40) |128.410.0.10|  
|[Yealink UVC84](https://www.yealink.com/product/camera-uvc84) |262.410.0.10|
|[Yealink UVC86]( https://www.yealink.com/product/camera-uvc86) |151.410.0.5|
|[Processador de Audioconferência Shure Intellimix P300](https://www.shure.com/products/mixers/p300)+</br></br> [Shure MXA 310 ](https://www.shure.com/products/microphones/mxa310) | 4.1 |
|[Processador de Audioconferência Shure Intellimix P300](https://www.shure.com/products/mixers/p300) + </br></br> [Shure MXA 910 com Intellimix Ceiling Array Mic](https://www.shure.com/products/microphones/mxa910) | 4.1|
|[Processador de Audioconferência Shure Intellimix P300](https://www.shure.com/products/mixers/p300)+</br></br> [Shure MXA 310 Table Array Mic ](https://www.shure.com/products/microphones/mxa310) +</br></br> [Alto-falante do Teto MXN5W-C](https://www.shure.com/en-US/products/loudspeakers/mxn5)| P300 DSP: 4.1.11 </br> Microfone MXA310 Table Array: 4.1.41 </br> Alto-falante MXN5W-C: 1.0.4 |
|[Processador de Audioconferência Shure Intellimix P300](https://www.shure.com/products/mixers/p300) + </br></br> [Shure MXA 910 com microfone de matriz de teto Intellimix](https://www.shure.com/products/microphones/mxa910) +</br></br> [Alto-falante do Teto MXN5W-C](https://www.shure.com/en-US/products/loudspeakers/mxn5)| P300 DSP: 4.1.11 </br> Microfone MXA910 Ceiling Array: 4.1.41 </br> Alto-falante MXN5W-C: 1.0.4 |
|[Shure MXA 710 2ft Table Linear Array Microphone](https://www.shure.com/products/microphones/mxa710) + </br></br> [Processador de Audioconferência Shure Intellimix P300](https://www.shure.com/products/mixers/p300) +</br></br> [Alto-falante de teto MXN5-C](https://www.shure.com/en-US/products/loudspeakers/mxn5)| MXA710 2ft Table Linear Array Mic: 1.2.0 </br> P300 DSP: 4.4.8 </br> Alto-falante MXN5-C: 1.1.1 |
|[Shure MXA 710 4ft Wall Linear Array Microphone](https://www.shure.com/products/microphones/mxa710) + </br></br> [Processador de Audioconferência Shure Intellimix P300](https://www.shure.com/products/mixers/p300) +</br></br> [Alto-falante de teto MXN5-C](https://www.shure.com/en-US/products/loudspeakers/mxn5)| MXA710 4ft Wall Linear Array Mic: 1.2.0 </br> P300 DSP: 4.4.8 </br> Alto-falante MXN5-C: 1.1.1 |
|[Shure MXA 910 com microfone intellimix ceiling array](https://www.shure.com/products/microphones/mxa910) + </br> [Shure Intellimix Room Software](https://www.shure.com/products/software/intellimix_room) +</br> [Crestron UC-C100-T](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C100-T)| Shure Intellimix Room Software: 3.0.4.14 </br> Shure MXA 910 com microfone da matriz de teto Intellimix: 4.4.11 </br> Alto-falantes Shure MXN5-C: 1.2.1 </br> Crestron UC-C100-T com computação ASUS Tek Computer INC 9934 | 
|[Shure MXA 910 com microfone intellimix ceiling array](https://www.shure.com/products/microphones/mxa910) + </br> [Shure Intellimix Room Software](https://www.shure.com/products/software/intellimix_room) +</br>Lenovo ThinkSmart Core | Shure Intellimix Room Software: 3.2.0.52 </br> Shure MXA 910 com microfone da matriz de teto Intellimix: 4.4.11 </br> Alto-falantes Shure MXN5-C: 1.2.1 </br> Lenovo ThinkSmart Core: Windows ioT 19h2/20h2 versão do sistema operacional |
|[Sennheiser TeamConnect Intelligent Speaker/TC ISP (T-Rock)](https://en-us.sennheiser.com/tcisp)|1.0.2|
|[Biamp Tesira Fore AVB VT4 Fixed audio DSP](https://www.biamp.com/products/tesira-fixed-audio-dsp)+ &Dagger;</br></br> [Sennheiser TeamConnect Ceiling 2 Microphone](https://sennheiser.com/tcc2)+ &Dagger;</br></br> [Tesira EX-UBT](https://www.biamp.com/products/tesira/tesira-expanders) &Dagger; |  DSP Biamp: 3.12.0.15  </br></br> TCC2: 1.3.3 </br></br> EX-UBT: 3.12.0.15 |
|[Biamp Tesira FORTÉ AVB VT4 Audio DSP](https://www.biamp.com/products/tesira-fixed-audio-dsp)+ </br></br>[Biamp Parlé TCM-XA Ceiling Microphone](https://www.biamp.com/products/product-families/parle/parle-microphones)+</br></br> [Alto-falante montado no teto biamp Desono C-IC6](https://www.biamp.com/products/tesira-speakers)| Versão do FW de áudio: 3.15|
|[Biamp TesiraFORTE AVB VT4](https://www.biamp.com/products/tesira-fixed-audio-dsp)+ </br></br>[Parle TTM-X(Table Mic)](https://www.biamp.com/products/product-families/parle/parle-microphones)+</br></br>[Ex-UBT]() |Versão do FW de áudio: 3.15|
|Biamp Tesira FORTE X Series +</br></br>[Série Devio SCX](https://www.biamp.com/products/product-families/devio/medium-large-room-solutions#devio-scx-400)|Tesira FORTE X Series: 4.2.5 </br> Série Devio SCX: 4.2.5|
|[Bose ControlSpace EX-440C DSP + </br>Bose P2600A AmpLink Amplifier +</br> Sennheiser TCC2 Ceiling Microphone + </br> Bose EdgeMax EM180 Ceiling Speaker](https://pro.bose.com/en_us/solutions/bose-work/es1-ceiling-audio-solution.html)|  Bose DSP: 2,290  </br> P2600A: 1,160  </br> TCC2:1.4.2  |  |
|[Bose ControlSpace EX-440C DSP + </br>Amplificador AmpLink Bose P2600A + Microfone de Teto Sennheiser TCC2 + </br> Alto-falante de Teto Bose DesignMax DM2C-P](https://pro.bose.com/en_us/solutions/bose-work/es1-ceiling-audio-solution.html)|  Bose DSP: 2,290  </br> P2600A: 1,160  </br> TCC2:1.4.2  |  |
|[Bose ControlSpace EX-1280C DSP](https://pro.bose.com/en_us/products/signal_processing_and_networking/controlspace_ex/cs_ex_1280c.html#v=cs_ex_1280c_black) +</br>Amplificador AmpLink Bose P2600A +</br> [Microfone de teto Sennheiser TCC2](https://pro.bose.com/en_us/solutions/bose-work/es1-ceiling-audio-solution.html) +</br> [Alto-falante de teto DesignMax DM2C -LP](https://pro.bose.com/en_us/products/loudspeakers/background_foreground/designmax/designmax_dm2c_lp.html#v=designmax_dm2c_lp_black) | Bose DSP: 2,290  </br> P2600A: 1,160  </br> TCC2:1.4.2  | 
|[Bose ControlSpace EX-1280C DSP](https://pro.bose.com/en_us/products/signal_processing_and_networking/controlspace_ex/cs_ex_1280c.html#v=cs_ex_1280c_black) +</br>Amplificador AmpLink Bose P2600A+</br> [Microfone de teto Sennheiser TCC2](https://pro.bose.com/en_us/solutions/bose-work/es1-ceiling-audio-solution.html) +</br> [Alto-falante do Teto EDGEMax EM180](https://pro.bose.com/en_us/products/loudspeakers/background_foreground/edgemax/edgemax_em180.html#v=edgemax_em180_white) | Bose DSP: 2,290  </br> P2600A: 1,160  </br> TCC2:1.4.2  |
|QSC Q-SYS Core ([110f](https://www.qsc.com/solutions-products/q-sys-ecosystem/processing/core-110f/), [8 Flex](https://www.qsc.com/solutions-products/q-sys-ecosystem/processing/core-8-flex/), [Nano](https://www.qsc.com/solutions-products/q-sys-ecosystem/processing/core-nano/) ou [NV-32-H](https://www.qsc.com/solutions-products/q-sys-ecosystem/processing/nv-32-h-core-capable/)) + </br> [Microfone de teto Sennheiser TCC2](https://en-us.sennheiser.com/tcc2) + </br> Amplificador QSC ([série SPA](https://www.qsc.com/solutions-products/power-amplifiers/installed/non-network/low-power-applications/spa-series/) ou [série CX-Q](https://www.qsc.com/solutions-products/power-amplifiers/installed/network/cx-q-series/)) + </br> [Alto-falantes da série AcousticDesign do QSC](https://www.qsc.com/solutions-products/loudspeakers/installed/passive/solutions/acousticdesigntm-series-solutions/) + </br> QSC IP Camera ([PTZ-IP 20x60](https://www.qsc.com/solutions-products/q-sys-ecosystem/video/ptz-ip-conference-cameras/), [PTZ-IP 12x72](https://www.qsc.com/solutions-products/q-sys-ecosystem/video/ptz-ip-conference-cameras/)) opcional + </br> [QSC Q-SYS E/S USB Bridge](https://www.qsc.com/solutions-products/q-sys-ecosystem/audio-io-peripherals/io-usb-bridge/) optional | QSC Q-SYS Core, Câmera PTZ-IP e Ponte USB de E/S: QSC Q-SYS Designer 9.0.1-2104.022 </br> Sennheiser TCC2 Ceiling Microphone: TCC2 - 1.5.1, Dante 1.2.0 </br> Amplificadores QSC: N/A </br> Alto-falantes da série QSC AcousticDesign: N/A | 


&Dagger; Os clientes podem escolher a interface Dante ou a opção de rede recomendada por Biamp/Sennheiser para esse pacote.

#### <a name="usb-extenders"></a>Extensores USB

- As portas USB em docking stations são compatíveis com USB 3.0. Você pode usar um extensor USB 2.x, mas estará limitado a velocidades USB 2.x na extremidade distante. Os extensores não são recomendados para periféricos USB 3.0.
- Um extensor deve atender a especificações USB 2,0 ou mais recentes.
  - As estações para tablet suportam pelo menos dois estágios da extensão do hub USB externo. Se você conectar mais de dois hubs USB na série, verifique com o fabricante da estação se eles são compatíveis com a conexão de série.
  - Conexão GbE com fio na sala. Cabo Ethernet de comprimento adequado.
  - Até duas exibições de 1080p com conexões HDMI. Cabos HDMI de comprimento adequado.

> [!NOTE]
> A TV usada em uma sala de exibição precisa suportar/habilitar o recurso CEC (Controle Eletrônico do Consumidor) do HDMI para que possa alternar automaticamente do modo de espera para uma fonte de vídeo ativa.  Esse recurso não é suportado em todas as TVs.
>
> Salas do Microsoft Teams não usa um teclado. Se necessário, o administrador deve usar o teclado virtual. O teclado ou o mouse USB serão necessários ao criar Imagens no dispositivo Salas do Microsoft Teams.

A tabela a seguir fornece recomendações de periféricos de acordo com o tamanho da sala:

**Periféricos de áudio certificados das Salas do Microsoft Teams**

|Tipo de sala|Número de pessoas|Distância máxima recomendada entre o microfone e a pessoa que está falando|
|:-----|:-----|:-----|
|**Foco** <br/> 10' x 9'   |2 a 4  |1,5 m  |
|**Small** <br/> 16 "x 16"  |4 a 6  |2.0 m  |
|**Médio** <br/> 18' x 20'  |6 a 12  |2.4 m  |
|**Large** <br/> 15' x 32'  |12 a 16  |3 m <br/> Essa distância também se aplica à área coberta por cada microfone de satélite conectado.  |

**Periféricos de vídeo certificados das salas do Microsoft Teams**

|Tipo de sala|Número de pessoas|
|:-----|:-----|
|**Foco** <br/> 10' x 9'  |2 a 4  |
|**Small** <br/> 16 "x 16"  |4 a 6  |
|**Médio** <br/> 18' x 20'  |6 a 12  |
|**Large** <br/> 15' x 32'  |12 a 16  |

 > [!NOTE]
 > A resolução de tela frontal não deve ser definida como menor do que 1920x1080p.


## <a name="see-also"></a>Confira também

[Procurar todos os pacotes](https://products.office.com/microsoft-teams/across-devices/devices)

[Planejar as Salas do Microsoft Teams](rooms-plan.md)

[Implantar Salas do Microsoft Teams](rooms-deploy.md)

[Configurar um console de Salas do Microsoft Teams](console.md)

[Gerenciar Salas do Microsoft Teams](rooms-manage.md)
