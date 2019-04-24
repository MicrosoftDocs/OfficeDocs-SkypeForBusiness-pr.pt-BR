---
title: Requisitos de salas de equipes da Microsoft
ms.author: jambirk
author: jambirk
ms.reviewer: davgroom
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6b2b2684-8e9e-49ea-8c46-1c690964f982
ms.collection: M365-voice
description: Este artigo resume os requisitos para dar suporte a salas de equipes da Microsoft.
ms.openlocfilehash: aff26f2f69b134569b8792df79c2afa4e4a18318
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214502"
---
# <a name="microsoft-teams-rooms-requirements"></a>Requisitos de salas de equipes da Microsoft

Este artigo resume os requisitos para dar suporte a salas de equipes da Microsoft. 

Sua implantação envolve a criação de conta, conforme descrito em [Salas de equipes Microsoft implantar](../../deploy/deploy-clients/room-systems-v2.md) e configurar um console de reunião, conforme descrito em [Configure um console de salas de equipes da Microsoft](../../deploy/deploy-clients/console.md). 

Você também pode precisar referir-se a:

- [Licenciamento do complemento Skype for Business](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing)
- [Opções com base no seu plano de licença: salas de equipes da Microsoft](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2)

> [!NOTE]
> Salas de equipes da Microsoft é destinada para uso com Skype para Business Server 2019, Skype para Business Server 2015, Microsoft Teams ou Skype para negócios Online. <br><br>Plataformas anteriores, como o Lync Server 2013 não são devem trabalhar com salas de equipes da Microsoft.

> [!NOTE]
> Se estiver usando um servidor do Exchange em prem, salas de equipes da Microsoft requer o uso do Exchange Server 2013 SP1 ou posterior.

## <a name="hardware-requirements"></a>Requisitos de hardware

Microsoft equipes salas pode ser dimensionado para tamanhos diferentes de sala por meio de Acessórios dependendo periféricos de áudio e vídeos. O hardware listado neste artigo suporta os modos de reunião de equipes e Skype.  Conectem periféricos de áudio e vídeos para salas de equipes da Microsoft por meio de uma conexão USB ou HDMI no dispositivo de encaixe. Também será necessário:

- Um 32GB ou disco maior de USB, que você irá configurar como inicializável mídia de instalação do Windows para Windows 10 Enterprise. 

- Uma das seguintes tablets ou consoles:

**Tablets com suporte**

|Tablet|Processador|RAM|Disco|
|:-----|:-----|:-----|:-----|
|Surface Pro 6          |Núcleo i5  |16GB ou 8GB |128GB ou mais  |
|Surface Pro (5º Ger)  |Núcleo i5  |8GB ou 4GB  |128GB ou mais  |
|Surface Pro 4          |Núcleo i5  |8GB ou 4GB  |128GB ou mais  |

> [!NOTE]
> Processadores de M3 Core não são suportados.

**Consoles com suporte**

|Console|Processador|RAM|Disco|
|:-----|:-----|:-----|:-----|
|[Hub de ThinkSmart Lenovo 500](https://www3.lenovo.com/us/en/hub500) |Núcleo i5  |8GB  |128GB  |  
|[Fatia de Elite HP para G2 salas de reunião](https://www8.hp.com/us/en/elite-family/elite-slice-for-meetings.html) |Núcleo i5  |8GB  |128GB  |  

- Uma das seguintes opções de estação de encaixe para proteger um tablet à reunião sala tabela. 

  - [Logitech SmartDock](https://partnersolutions.skypeforbusiness.com/solutionscatalog/all/logitech-smart-dock)

  - [Crestron SR](http://www.crestron.com/products/line/sr-for-skype-for-business-room-system )

  - [Série de Polycom MSR](http://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.html)



**Versões de firmware para periféricos USB de áudio e vídeos de certificado**

|Periféricos de salas de equipes da Microsoft|Versão de firmware certificada para salas de equipes da Microsoft|
|:-----|:-----|
|[Logitech BRIO](https://www.logitech.com/en-us/product/brio) <br/> |v240|
|[Logitech MeetUp](http://www.logitech.com/en-us/product/meetup-conferencecam) <br/> |Áudio - 1.0.172  <br/> Vídeo - 1.0.156  <br/> |
|[Conectar Logitech ConferenceCam](http://www.logitech.com/en-us/product/conferencecam-connect) <br/> |1.1.248.0  <br/> 1.1.684  <br/> |
|[Grupo Logitech](http://www.logitech.com/en-us/product/conferencecam-group) <br/> |8.5.778  <br/> |
|[Logitech 930e](http://www.logitech.com/en-us/product/c930e-webcam) <br/> | 8.0.914 <br/> |
|[Logitech PTZ Pro](http://www.logitech.com/en-us/product/conferencecam-ptz-pro) <br/> | 1.1.219 <br/> |
|[Logitech PTZ Pro 2](http://www.logitech.com/en-us/product/conferencecam-ptz-pro2) <br/> |
|[Polycom RealPresence Trio](http://www.polycom.com/voice-conferencing-solutions/conference-phones/realpresence-trio.mdl) <br/> |5.4.4,7511  <br/> |
|[Polycom EagleEye IV](http://www.polycom.com/products-services/hd-telepresence-video-conferencing/realpresence-accessories/eagleeye-cameras.mdl) <br/> |1.0.0  <br/> |
|[Polycom CX5100 ](http://www.polycom.com/products-services/products-for-microsoft/lync-optimized/cx5100-unified-conference-station.mdl) <br/> | 1.2.0,70232 <br/> |
|[Sennheiser SP 220 MS](http://no-no.sennheiser.com/dual-speakerphones-sp-220-ms-uc) <br/> |2.0.12.0  <br/> |
|[Sennheiser SP20](http://en-us.sennheiser.com/sp-20-og-sp-20-ml) <br/> |1.2.15  <br/> |
|[Jabra 510](http://www.jabra.com/support/Jabra-SPEAK™-510_7510-209) <br/> |2.10.0  <br/> |
|[Jabra 710](http://www.jabra.com/business/speakerphones/jabra-speak-series/jabra-speak-710) <br/> |1.8.0  <br/> |
|[Jabra 810](http://www.jabra.com/supportpages/jabra-speak-810) <br/> |1.2.23  <br/> |
|[Yamaha YVC 1000](http://www.yamaha.com/products/en/communication/usb_conference_speakerphones/yvc-1000/) <br/> |100c  <br/> |

- **Extensores USB**:

  - Portas USB na módulos de ancoragem de tablet são USB 3.0 compatível. Você pode usar um extensor de 2. x USB, mas fazer isso limitará você para USB velocidades de 2. x na extremidade distante e fazer isso não é recomendado para periféricos USB 3.0.

  - Um extensor deve atender a USB 2.0 ou especificações mais recentes.

  - Módulos de ancoragem de Tablet oferecem suporte a pelo menos dois estágios da extensão de hub USB externo. Se a necessidade para conectar-se mais de dois hubs USB em série, você precisará verificar com o fabricante de encaixe para confirmar a fazer isso é suportado.

- Conexão com fio de GbE na sala. Cabo Ethernet de comprimento adequado.

- Até dois vídeos de 1080p com conexões de HDMI. Cabos HDMI de tamanho apropriado.

    > [!NOTE]
    > A TV usada em uma sala de exibição precisa suportar/habilitar o recurso CEC (Controle Eletrônico do Consumidor) do HDMI para que possa alternar automaticamente do modo de espera para uma fonte de vídeo ativa.  Esse recurso não é suportado em todas as TVs. 

> [!NOTE]
> Salas de equipes da Microsoft não usa um teclado. Se necessário, o administrador deve usar o teclado virtual. Um mouse ou teclado USB serão necessária quando o dispositivo Microsoft equipes salas de geração de imagens. 

As tabelas a seguir fornecem recomendações para periféricos com base no tamanho de sala:

**Salas de equipes da Microsoft certificadas periféricos de áudio**

|Tipo de sala|Número de pessoas|Distância máxima recomendada entre o microfone e a pessoa que está falando|Dispositivo, de acordo com o tamanho máximo da sala|Comentários|
|:-----|:-----|:-----|:-----|:-----|
|**Foco** <br/> 10' x 9'  <br/> |2-4  <br/> |1.5m   <br/> |Logitech Connect  <br/> |Os dispositivos Logitech conectar incluem uma câmera, portanto, ele deve ser posicionado à frente da sala (não o centro da tabela) para capturar os participantes da reunião local.  <br/> |
|**Pequena** <br/> 16' x 16'  <br/> |4 a 6  <br/> |2.0m  <br/> |Jabra 510  <br/> Sennheiser SP20  <br/> |O volume de reprodução pode ser limitado em salas maiores.  <br/> |
|**Médio** <br/> 18' x 20'  <br/> |6-12  <br/> |2.4m  <br/> |Jabra 710  <br/> Jabra 810  <br/> Logitech MeetUp  <br/> Logitech Group  <br/> Polycom Trio  <br/> Polycom CX5100   <br/> Sennheiser SP 220 MS  <br/> Yamaha YVC-1000 msegs  <br/> |O Logitech MeetUp inclui uma câmera de forma que ele deve ser posicionado à frente da sala (não o centro da tabela para capturar participantes da reunião local).  <br/> Em geral, salas com longos retangulares ou em forma de u tabelas podem se beneficiar de microfones de satélite adicionais.  <br/> O SP 220 MS deve ser usado em configuração de corrente margarida.  <br/> |
|**Grande** <br/> 15' x 32 °  <br/> |16 de 12  <br/> |3m  <br/> Essa distância também se aplica à área coberta por cada microfone parabólico adicional conectado ao dispositivo de áudio em questão.   <br/> |Grupo Logitech + microfones de satélite  <br/> Microfones de satélite Polycom Trio +  <br/> Polycom CX5100 + microfones de satélite  <br/> Sennheiser SP 220 MS  <br/> Yamaha YVC-1000 msegs + microfones de satélite  <br/> |Todos os dispositivos de áudio listados nesta linha dão suporte a opções de microfones parabólicos.  <br/> O CX5100 inclui uma câmera interna de 360 graus; assim, o dispositivo pode ser posicionado no centro da mesa.  <br/> O SP 220 MS deve ser usado em configuração de corrente margarida.  <br/> |

**Salas de equipes da Microsoft certificadas periféricos de vídeo**

|Tipo de sala|Número de pessoas|Dispositivo pelo tamanho ideal de sala|Comentários|
|:-----|:-----|:-----|:-----|
|**Foco** <br/> 10' x 9'  <br/> |2-4  <br/> |Logitech Connect  <br/> Logitech MeetUp  <br/> Polycom CX5100   <br/> ||
|**Pequena** <br/> 16' x 16'  <br/> |4 a 6  <br/> |Logitech C930e  <br/> Logitech MeetUp  <br/> Logitech BRIO  <br/> Logitech PTZ Pro  <br/> Polycom MSR  <br/> Polycom CX5100   <br/> |Logitech PTZ Pro geralmente vem com grupo Logitech  <br/> |
|**Médio** <br/> 18' x 20'  <br/> |6-12  <br/> |Logitech MeetUp  <br/> Logitech BRIO  <br/> Logitech PTZ Pro  <br/> Polycom MSR  <br/> Polycom CX5100   <br/> ||
|**Grande** <br/> 15' x 32 °  <br/> |16 de 12  <br/> |Logitech PTZ Pro  <br/> Polycom MSR  <br/> Polycom CX5100   <br/> ||

 > [!NOTE]
 > Parte frontal da resolução de vídeo de sala deve ser definido como não maior do que 1920x1080p.

## <a name="required-software-downloads"></a>Downloads de software necessárias

Para criar sua própria imagem de salas de equipes da Microsoft, siga as instruções em [Configure um console de salas de equipes da Microsoft](../../deploy/deploy-clients/console.md). Essas instruções vão orientá-lo por meio de baixar todo o software necessário para o processo de instalação. 

> [!NOTE]
> Profissionais de TI precisará ter acesso aos arquivos do Windows 10 Enterprise ISO por meio de seu contrato de licenciamento por volume.

Além disso, você pode querer uma cópia do [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), que pode ser usada para provisionar contas de salas de equipes da Microsoft.

## <a name="see-also"></a>Confira também

[Planejar para salas de equipes da Microsoft](skype-room-systems-v2-0.md)

[Implantar salas de equipes da Microsoft](../../deploy/deploy-clients/room-systems-v2.md)

[Configurar um console de salas de equipes da Microsoft](../../deploy/deploy-clients/console.md)

[Gerenciar Salas do Microsoft Teams](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

[Licenciamento de complementos do Skype for Business](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)
