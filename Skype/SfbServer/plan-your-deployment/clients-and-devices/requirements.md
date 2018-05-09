---
title: Requisitos do Skype Room Systems versão 2
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6b2b2684-8e9e-49ea-8c46-1c690964f982
description: Este artigo resume os requisitos para dar suporte a um v2 Skype sistemas de sala.
ms.openlocfilehash: 0fb1fbcde28c343787967485dd6cae36491311b7
ms.sourcegitcommit: 7ec95ea34422e635661f3659bbc43a7a3484ff99
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/09/2018
---
# <a name="skype-room-systems-v2-requirements"></a>Requisitos do Skype Room Systems versão 2
 
Este artigo resume os requisitos para dar suporte a um v2 Skype sistemas de sala. 
  
Sua implantação envolve a criação de conta, conforme descrito em [implantar sistemas de sala Skype v2](../../deploy/deploy-clients/room-systems-v2.md) e configurar um console de reunião, conforme descrito em [Configure um console do Skype sala sistemas v2](../../deploy/deploy-clients/console.md). Você também pode precisar fazer referência à [Skype para licenciamento de complemento de negócios](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7).
  
## <a name="hardware-requirements"></a>Requisitos de hardware

Sistemas de sala Skype v2 pode ser dimensionado para tamanhos diferentes de sala por meio de Acessórios dependendo periféricos de áudio e vídeos. Periféricos de áudio e vídeos conectem-se a sistemas de sala Skype v2 por meio de uma conexão USB ou HDMI no dispositivo de encaixe. Também será necessário:
  
- Um 32GB ou disco maior de USB, que você irá configurar como inicializável mídia de instalação do Windows para Windows 10 Enterprise. 
    
- Um dos tablets a seguir:
    
**Tablets com suporte**


|**Tablet**|**Processador**|**RAM**|**Disco**|
|:-----|:-----|:-----|:-----|
|Surface Pro 4 & sup1;  <br/> |Núcleo i5  <br/> |4GB  <br/> |128GB  <br/> |
|Surface Pro 4 & sup1;  <br/> |Núcleo i5  <br/> |8GB  <br/> |256GB  <br/> |
|Surface Pro & sup1; <br/> |Núcleo i5  <br/> |4GB  <br/> |128GB  <br/> |
|Surface Pro & sup1; <br/> |Núcleo i5  <br/> |8GB  <br/> |256GB  <br/> |
|Surface Pro & sup1; <br/> |Core i7  <br/> |8GB  <br/> |128GB  <br/> |
|Surface Pro & sup1; <br/> |Core i7  <br/> |16GB  <br/> |512GB  <br/> |
|Surface Pro & sup1; <br/> |Core i7  <br/> |16GB  <br/> |1TB  <br/> |
   
& sup1; — Processadores de M3 core não são suportados nesse modelo.
    
 
    
- Uma das seguintes opções de estação de encaixe para proteger o tablet à reunião sala tabela. 
    
  - [Logitech SmartDock](https://www.logitech.com/en-us/product/smartdock)
    
  - [Crestron SR](http://www.crestron.com/products/line/sr-for-skype-for-business-room-system )
    
  - [Série de Polycom MSR](http://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.html)

  - [Hub de Lenovo 500](https://www3.lenovo.com/us/en/hub500)  
<!-- HP dock is still pending  -->  
 
**Versões de firmware para periféricos USB de áudio e vídeos de certificado**
|**Periféricos v2 de sistemas de sala do Skype**|**Versão de firmware certificada para sistemas de sala Skype v2**|
|:-----|:-----|
|[Logitech BRIO](https://www.logitech.com/en-us/product/brio) <br/> ||
|[Logitech MeetUp](http://www.logitech.com/en-us/product/meetup-conferencecam) <br/> |Áudio - 1.0.172  <br/> Vídeo - 1.0.156  <br/> |
|[Conectar Logitech ConferenceCam](http://www.logitech.com/en-us/product/conferencecam-connect) <br/> |1.1.248.0  <br/> 1.1.684  <br/> |
|[Grupo Logitech](http://www.logitech.com/en-us/product/conferencecam-group) <br/> |8.5.778  <br/> |
|[Logitech 930e](http://www.logitech.com/en-us/product/c930e-webcam) <br/> | 8.0.914 <br/> |
|[Logitech PTZ Pro](http://www.logitech.com/en-us/product/conferencecam-ptz-pro) <br/> | 1.1.219 <br/> |
|[Polycom RealPresence Trio](http://www.polycom.com/voice-conferencing-solutions/conference-phones/realpresence-trio.mdl) <br/> |5.4.4.7511  <br/> |
|[Polycom EagleEye IV](http://www.polycom.com/products-services/hd-telepresence-video-conferencing/realpresence-accessories/eagleeye-cameras.mdl) <br/> |1.0.0  <br/> |
|[Polycom CX5100](http://www.polycom.com/products-services/products-for-microsoft/lync-optimized/cx5100-unified-conference-station.mdl) <br/> | 1.2.0.70232 <br/> |
|[Sennheiser SP 220 MS](http://no-no.sennheiser.com/dual-speakerphones-sp-220-ms-uc) <br/> |2.0.12.0  <br/> |
|[Sennheiser SP20](http://en-us.sennheiser.com/sp-20-og-sp-20-ml) <br/> |1.2.15  <br/> |
|[510 Jabra](http://www.jabra.com/support/Jabra-SPEAK™-510_7510-209) <br/> |2.10.0  <br/> |
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
> Sistemas de sala Skype v2 não usa um teclado. Se necessário, o administrador deve usar o teclado virtual. Um mouse ou teclado USB serão necessária quando o dispositivo de v2 Skype sala sistemas de geração de imagens. 
  
As tabelas a seguir fornecem recomendações para periféricos com base no tamanho de sala:
  
**Skype sala sistemas v2 Certified periféricos de áudio**

|**Tipo de sala**|**Número de pessoas**|**Distância máxima recomendada de microfone para a pessoa que está falando**|**Dispositivo pelo tamanho máximo de sala**|**Comentários**|
|:-----|:-----|:-----|:-----|:-----|
|**Foco** <br/> 10' x 9'  <br/> |2-4  <br/> |1,5 m  <br/> |Logitech Connect  <br/> |Os dispositivos Logitech conectar incluem uma câmera, portanto, ele deve ser posicionado à frente da sala (não o centro da tabela) para capturar os participantes da reunião local.  <br/> |
|**Pequeno** <br/> 16' x 16'  <br/> |4 a 6  <br/> |m 2.0  <br/> |Jabra 510  <br/> Sennheiser SP20  <br/> |O volume de reprodução pode ser limitado em salas maiores.  <br/> |
|**Médio** <br/> 18' x 20'  <br/> |6-12  <br/> |2.4m  <br/> |Jabra 710  <br/> Jabra 810  <br/> Logitech MeetUp  <br/> Logitech Group  <br/> Polycom Trio  <br/> Polycom CX5100   <br/> Sennheiser SP 220 MS  <br/> Yamaha YVC-1000 msegs  <br/> |O Logitech MeetUp inclui uma câmera de forma que ele deve ser posicionado à frente da sala (não o centro da tabela para capturar participantes da reunião local).  <br/> Em geral, salas com longos retangulares ou em forma de u tabelas podem se beneficiar de microfones de satélite adicionais.  <br/> O SP 220 MS deve ser usado em configuração de corrente margarida.  <br/> |
|**Grande** <br/> 15' x 32 °  <br/> |16 de 12  <br/> |3C  <br/> Essa distância também se aplica à área coberta por cada microfone parabólico adicional conectado ao dispositivo de áudio em questão.   <br/> |Grupo Logitech + microfones de satélite  <br/> Microfones de satélite Polycom Trio +  <br/> Polycom CX5100 + microfones de satélite  <br/> Sennheiser SP 220 MS  <br/> Yamaha YVC-1000 msegs + microfones de satélite  <br/> |Todos os dispositivos de áudio listados nesta linha dão suporte a opções de microfones parabólicos.  <br/> O CX5100 inclui uma câmera interna de 360 graus; assim, o dispositivo pode ser posicionado no centro da mesa.  <br/> O SP 220 MS deve ser usado em configuração de corrente margarida.  <br/> |
   
**Skype sala sistemas v2 Certified periféricos de vídeo**

|Tipo de sala|Número de pessoas|Dispositivo pelo tamanho ideal de sala|Comentários|
|:-----|:-----|:-----|:-----|
|**Foco** <br/> 10' x 9'  <br/> |2-4  <br/> |Logitech Connect  <br/> Logitech MeetUp  <br/> Polycom CX5100   <br/> ||
|**Pequeno** <br/> 16' x 16'  <br/> |4 a 6  <br/> |Logitech C930e  <br/> Logitech MeetUp  <br/> Logitech BRIO  <br/> Logitech PTZ Pro  <br/> Polycom MSR  <br/> Polycom CX5100   <br/> |Logitech PTZ Pro geralmente vem com grupo Logitech  <br/> |
|**Médio** <br/> 18' x 20'  <br/> |6-12  <br/> |Logitech MeetUp  <br/> Logitech BRIO  <br/> Logitech PTZ Pro  <br/> Polycom MSR  <br/> Polycom CX5100   <br/> ||
|**Grande** <br/> 15' x 32 °  <br/> |16 de 12  <br/> |Logitech PTZ Pro  <br/> Polycom MSR  <br/> Polycom CX5100   <br/> ||
   
 > [!NOTE]
 > Parte frontal da resolução de vídeo de sala deve ser definido como não maior do que 1920x1080p.

## <a name="required-software-downloads"></a>Downloads de software necessários

Você precisará os seguintes downloads para construir sua própria imagem do Skype sala sistemas v2:
  
- O [pacote de instalação do Skype sala sistemas v2](https://go.microsoft.com/fwlink/?linkid=851168).
    
- Obtenha uma cópia da versão de 64 bits da atualização do criador do Windows 10 Enterprise (idioma inglês, compilação 1703). 
    
    > [!NOTE]
    > A versão de 64 bits do edition de aniversário no Windows 10 Enterprise (idioma inglês, versão 1607) não é mais suportada a partir de sistemas de sala Skype v2 versão 3.0.12.0 (atualização de 3). 
  
- O suportados [Surface Pro 4 de drivers](https://go.microsoft.com/fwlink/?linkid=856887) ou [drivers Surface Pro](https://go.microsoft.com/fwlink/?linkid=856888).
    
Esses downloads precisam ser combinados em um disco inicializável de mídia de instalação do Windows de uma forma específica, descrita posteriormente em [Configure um console do Skype sala sistemas v2](../../deploy/deploy-clients/console.md). 
  
Além disso, você pode querer uma cópia do [script do Powershell](https://go.microsoft.com/fwlink/?linkid=870105) usada para provisionar contas do Skype sala sistemas v2.
  
## <a name="see-also"></a>Consulte também

#### 

[Planejar a sala Skype v2 de sistemas](skype-room-systems-v2-0.md)
  
[Implantar Skype sala v2 de sistemas](../../deploy/deploy-clients/room-systems-v2.md)
  
[Configurar um console v2 de sistemas de sala do Skype](../../deploy/deploy-clients/console.md)
  
[Gerenciar Skype sala v2 de sistemas](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)
#### 

[Licenciamento de complementos do Skype for Business](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)

