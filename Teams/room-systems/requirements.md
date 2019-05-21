---
title: Requisitos de salas do Microsoft Teams
ms.author: v-lanac
author: lanachin
ms.reviewer: davgroom
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6b2b2684-8e9e-49ea-8c46-1c690964f982
ms.collection: M365-voice
description: Este artigo resume os requisitos para dar suporte a salas do Microsoft Teams.
ms.openlocfilehash: 364ed7ee3027e05753dee65a896f50024e7572b8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34305466"
---
# <a name="microsoft-teams-rooms-requirements"></a>Requisitos de salas do Microsoft Teams

Este artigo resume os requisitos para dar suporte a salas do Microsoft Teams. 

Sua implantação envolverá a criação de conta, conforme descrito em [implantar salas do Microsoft Teams](room-systems-v2.md) e configurando um console de reunião conforme descrito em [configurar um console de salas do Microsoft Teams](console.md). 

Você também pode precisar consultar:

- [Licenciamento do complemento Skype for Business](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing)
- [Opções de licença com base em seu plano: salas do Microsoft Teams](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2)

> [!NOTE]
> As salas do Microsoft Teams devem ser usadas com o Microsoft Teams, o Skype for Business Server 2019, o Skype for Business Server 2015 ou o Skype for Business online. <br><br>Plataformas anteriores como o Lync Server 2013 não devem funcionar com salas do Microsoft Teams.

> [!NOTE]
> Se estiver usando um servidor Exchange local, as salas do Microsoft Teams exigem o uso do Exchange Server 2013 SP1 ou posterior.

## <a name="hardware-requirements"></a>Requisitos de hardware

As salas do Microsoft Teams podem ser dimensionadas para diferentes tamanhos de sala por meio de acessórios, dependendo de periféricos de áudio e vídeo. O hardware listado neste artigo é compatível com os modos de reunião do Skype e do teams.  Os periféricos de áudio e vídeo se conectam a salas do Microsoft Team via conexão USB ou HDMI no dispositivo de encaixe. Também será necessário:

- Um disco USB de 32 GB ou maior que você irá configurar como mídia inicializável de instalação do Windows para Windows 10 Enterprise. 

- Um dos seguintes tablets ou consoles:

**Tablets compatíveis**

|Sofrer|631|RAM|Disco|
|:-----|:-----|:-----|:-----|
|Surface pro 6          |Core i5  |16 GB ou 8 GB |128 GB ou mais  |
|Surface pro (5ª gen)  |Core i5  |8 GB ou 4 GB  |128 GB ou mais  |
|Surface Pro 4          |Core i5  |8 GB ou 4 GB  |128 GB ou mais  |

> [!NOTE]
> Não há suporte para os processadores Core m3.

**Consoles compatíveis**

|Console|631|RAM|Disco|
|:-----|:-----|:-----|:-----|
|[Hub ThinkSmart Hub do Lenovo 500](https://www3.lenovo.com/us/en/hub500) |Core i5  |DIMM  |GB  |  
|[Fatia HP elite para salas de reunião G2](https://www8.hp.com/us/en/elite-family/elite-slice-for-meetings.html) |Core i5  |DIMM  |GB  |  

- Uma das opções de Docking Station a seguir para proteger um tablet para a tabela de salas de reunião. 

  - [Logitech SmartDock](https://partnersolutions.skypeforbusiness.com/solutionscatalog/all/logitech-smart-dock)

  - [Crestron SR](http://www.crestron.com/products/line/sr-for-skype-for-business-room-system )

  - [Série MSR Polycom](http://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.html)



**Versões de firmware certificadas para periféricos de áudio e vídeo USB**

|Periféricos de salas do Microsoft Teams|Versão do firmware certificado para salas do Microsoft Teams|
|:-----|:-----|
|[Logitech BRIO](https://www.logitech.com/en-us/product/brio) <br/> |v240|
|[Logitech MeetUp](http://www.logitech.com/en-us/product/meetup-conferencecam) <br/> |Áudio-1.0.172  <br/> Vídeo-1.0.156  <br/> |
|[Conexão Logitech ConferenceCam](http://www.logitech.com/en-us/product/conferencecam-connect) <br/> |1.1.248.0  <br/> 1.1.684  <br/> |
|[Grupo Logitech](http://www.logitech.com/en-us/product/conferencecam-group) <br/> |8.5.778  <br/> |
|[Logitech 930e](http://www.logitech.com/en-us/product/c930e-webcam) <br/> | 8.0.914 <br/> |
|[Logitech PTZ pro](http://www.logitech.com/en-us/product/conferencecam-ptz-pro) <br/> | 1.1.219 <br/> |
|[Logitech PTZ Pro 2](http://www.logitech.com/en-us/product/conferencecam-ptz-pro2) <br/> |
|[Trio de Polycom RealPresence](http://www.polycom.com/voice-conferencing-solutions/conference-phones/realpresence-trio.mdl) <br/> |5.4.4,7511  <br/> |
|[Polycom EagleEye IV](http://www.polycom.com/products-services/hd-telepresence-video-conferencing/realpresence-accessories/eagleeye-cameras.mdl) <br/> |1.0.0  <br/> |
|[Polycom CX5100 ](http://www.polycom.com/products-services/products-for-microsoft/lync-optimized/cx5100-unified-conference-station.mdl) <br/> | 1.2.0,70232 <br/> |
|[Sennheiser SP 220 MS](http://no-no.sennheiser.com/dual-speakerphones-sp-220-ms-uc) <br/> |2.0.12.0  <br/> |
|[Sennheiser SP20](http://en-us.sennheiser.com/sp-20-og-sp-20-ml) <br/> |1.2.15  <br/> |
|[Jabra 510](http://www.jabra.com/support/Jabra-SPEAK™-510_7510-209) <br/> |2.10.0  <br/> |
|[Jabra 710](http://www.jabra.com/business/speakerphones/jabra-speak-series/jabra-speak-710) <br/> |1.8.0  <br/> |
|[Jabra 810](http://www.jabra.com/supportpages/jabra-speak-810) <br/> |1.2.23  <br/> |
|[Yamaha YVC-1000](http://www.yamaha.com/products/en/communication/usb_conference_speakerphones/yvc-1000/) <br/> |100c  <br/> |

- **Extensores USB**:

  - Portas USB em cais de Tablet são compatíveis com USB 3,0. Você pode usar um extensor USB 2. x, mas isso o limitará às velocidades USB 2. x na extremidade oposta e fazer isso não será recomendado para periféricos USB 3,0.

  - Um Extender deve atender às especificações USB 2,0 ou mais recente.

  - Os encaixes de Tablet dão suporte a pelo menos dois estágios de extensão de Hub USB externo. Se for necessário conectar mais de dois hubs USB em série, será necessário verificar com o fabricante do Dock para confirmar se isso é suportado.

- Conexão GbE com fio na sala. Cabo Ethernet de comprimento adequado.

- Até dois monitores de 1080p com conexões HDMI. Cabos HDMI de tamanho apropriado.

    > [!NOTE]
    > A TV usada em uma sala de exibição precisa suportar/habilitar o recurso CEC (Controle Eletrônico do Consumidor) do HDMI para que possa alternar automaticamente do modo de espera para uma fonte de vídeo ativa.  Esse recurso não é suportado em todas as TVs. 

> [!NOTE]
> As salas do Microsoft Teams não usam um teclado. Se necessário, o administrador deve usar o teclado virtual. Um mouse ou teclado USB será necessário ao fazer o Imaging do dispositivo de salas do Microsoft Teams. 

As tabelas a seguir fornecem recomendações para periféricos com base no tamanho da sala:

**Periféricos de áudio certificados de salas do Microsoft Teams**

|Tipo de sala|Número de pessoas|Distância máxima recomendada entre o microfone e a pessoa que está falando|Dispositivo, de acordo com o tamanho máximo da sala|Comentários|
|:-----|:-----|:-----|:-----|:-----|
|**Foco** <br/> 10 ' x 9 '  <br/> |2-4  <br/> |1.5m   <br/> |Logitech Connect  <br/> |Os dispositivos Logitech Connect incluem uma câmera para que ela deva ser posicionada na frente da sala (não no centro da tabela) para capturar os participantes da reunião local.  <br/> |
|**Pequena** <br/> 16 ' x 16 '  <br/> |4-6  <br/> |2.0m  <br/> |Jabra 510  <br/> Sennheiser SP20  <br/> |O volume de reprodução pode ser limitado em salas maiores.  <br/> |
|**Médio** <br/> 18 ' x 20 '  <br/> |6-12  <br/> |2.4m  <br/> |Jabra 710  <br/> Jabra 810  <br/> Logitech MeetUp  <br/> Logitech Group  <br/> Polycom Trio  <br/> Polycom CX5100   <br/> Sennheiser SP 220 MS  <br/> Yamaha YVC-1000MS  <br/> |O Logitech MeetUp inclui uma câmera para que ela deva ser posicionada na frente da sala (não no centro da tabela para capturar os participantes da reunião local).  <br/> Em geral, as salas com tabelas retangulares ou em formato de u longos podem se beneficiar com microfones adicionais do satélite.  <br/> O SP 220 MS deve ser usado em configuração de corrente margarida.  <br/> |
|**Grande** <br/> 15 ' x 32 '  <br/> |12-16  <br/> |3m  <br/> Essa distância também se aplica à área coberta por cada microfone parabólico adicional conectado ao dispositivo de áudio em questão.   <br/> |Logitech Group + satélite duais  <br/> Polycom trio + satélite duais  <br/> Polycom CX5100 + satélite duais  <br/> Sennheiser SP 220 MS  <br/> Yamaha YVC-1000MS + satélite duais  <br/> |Todos os dispositivos de áudio listados nesta linha dão suporte a opções de microfones parabólicos.  <br/> O CX5100 inclui uma câmera interna de 360 graus; assim, o dispositivo pode ser posicionado no centro da mesa.  <br/> O SP 220 MS deve ser usado em configuração de corrente margarida.  <br/> |

**Periféricos de vídeo certificados para salas do Microsoft Teams**

|Tipo de sala|Número de pessoas|Dispositivo por tamanho ideal da sala|Comentários|
|:-----|:-----|:-----|:-----|
|**Foco** <br/> 10 ' x 9 '  <br/> |2-4  <br/> |Logitech Connect  <br/> Logitech MeetUp  <br/> Polycom CX5100   <br/> ||
|**Pequena** <br/> 16 ' x 16 '  <br/> |4-6  <br/> |Logitech C930e  <br/> Logitech MeetUp  <br/> Logitech BRIO  <br/> Logitech PTZ pro  <br/> Polycom MSR  <br/> Polycom CX5100   <br/> |A Logitech PTZ pro geralmente acompanhada do Logitech Group  <br/> |
|**Médio** <br/> 18 ' x 20 '  <br/> |6-12  <br/> |Logitech MeetUp  <br/> Logitech BRIO  <br/> Logitech PTZ pro  <br/> Polycom MSR  <br/> Polycom CX5100   <br/> ||
|**Grande** <br/> 15 ' x 32 '  <br/> |12-16  <br/> |Logitech PTZ pro  <br/> Polycom MSR  <br/> Polycom CX5100   <br/> ||

 > [!NOTE]
 > A resolução de tela frontal da sala deve ser definida como não maior do que 1920x1080p.

## <a name="required-software-downloads"></a>Downloads de software necessários

Para criar sua própria imagem de salas do Microsoft Teams, siga as instruções em [configurar um console de salas do Microsoft Teams](console.md). Essas instruções orientarão você no download de todo o software necessário para o processo de instalação. 

> [!NOTE]
> Os profissionais de ti precisarão acessar os arquivos ISO do Windows 10 Enterprise por meio do contrato de licenciamento por volume.

Além disso, você provavelmente vai querer uma cópia de [SkypeRoomProvisioningScript. ps1](https://go.microsoft.com/fwlink/?linkid=870105), que pode ser usada para configurar contas de salas do Microsoft Teams.

## <a name="see-also"></a>Confira também

[Plano para salas do Microsoft Teams](skype-room-systems-v2-0.md)

[Implantar salas do Microsoft Teams](room-systems-v2.md)

[Configurar um console de salas do Microsoft Teams](console.md)

[Gerenciar Salas do Microsoft Teams](skype-room-systems-v2.md)

[Licenciamento de complementos do Skype for Business](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)
