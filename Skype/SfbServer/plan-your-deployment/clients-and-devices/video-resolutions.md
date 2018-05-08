---
title: Skype para resoluções de vídeo de cliente de negócios
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 8f68f4c2-3194-487c-bd2f-fbe71ba8ad70
description: 'Resumo: Revise os requisitos de vídeo do cliente durante o planejamento de Skype para Business Server 2015.'
ms.openlocfilehash: ea4c7e1cf9e0e1df24b00e817cac22128df1d0b8
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
---
# <a name="skype-for-business-client-video-resolutions"></a>Skype para resoluções de vídeo de cliente de negócios
 
**Resumo:** Examine os requisitos de vídeo do cliente durante o planejamento de Skype para Business Server 2015.
  
Este artigo descreve o suporte de hardware de vídeo para Skype para chamadas de vídeo de negócios e descreve como determinar a qualidade de vídeo esperada para várias configurações de dispositivo móvel, tablet e computador. 
  
Profissionais de TI encontrará essas informações úteis para avaliar a viabilidade da laptops já em uso na sua organização ou em consideração para uso. Eles também podem pesquisar o [Catálogo de soluções](https://partnersolutions.skypeforbusiness.com/solutionscatalog) para obter informações sobre dispositivos específicos.
  
## <a name="windows-desktop-mac-and-tablet-video-requirements-and-capabilities"></a>Área de trabalho do Windows, Mac e tablet requisitos de vídeo e recursos

Skype para negócios usa aceleração de hardware de vídeo de codificação e decodificação baseado no h. 264/MPEG-4 parte 10 avançadas vídeo codificação padrão. Isso permite que os computadores com menores velocidades de clock de CPU para codificar e decodificar vídeo de resolução superior. Os requisitos de hardware de vídeo variam de acordo com a configuração do computador e a resolução de vídeo desejada.
  
Consulte também [os requisitos de hardware do Windows e Mac](https://products.office.com/en-us/office-system-requirements).
  
### <a name="video-hardware-requirements"></a>Requisitos de hardware de vídeo

|**Recurso**|**Requisito**|
|:-----|:-----|
|Decodificação H.264 acelerada por hardware usando DirectX Video Acceleration (DXVA)  <br/> |• Placa deve suportar DirectX 9.0 e deve expor o modo de decodificação DXVA2_ModeH264_VLD_NoFGT e a API do DirectX 9.  <br/> • O driver mais recente da placa gráficos deve ser instalado.  <br/> |
|Codificação H.264 acelerada por hardware: requisitos de chipset  <br/> |As seguintes soluções de codificação de vídeo acelerada por hardware da Intel têm suporte:  <br/> • Segunda e terceira geração Intel HD Graphics 2000, 2500, 3000 e 4000 chipsets (ou versões posteriores) com codificadores de vídeo de hardware integrados. A instalação do driver Intel HD Graphics 15.28.9.2884 ou driver mais recente contendo os seguintes itens é necessária:  <br/> • Display driver 9.17.10.2884 ou do mais recente  <br/> • Foundation de mídia de hardware transformar versão (HMFT) 3.12.10.31 ou o HMFT mais recente  <br/> As seguintes soluções de codificação de vídeo acelerada por hardware da AMD têm suporte:  <br/> • O mecanismo de Codec de vídeo AMD, que está disponível em vários cartões de gráficos discretos e em integrada acelerado unidades de processamento de processadores AMD acelerado de uma série. O driver do Mecanismo de Codec de Vídeo AMD 9.12.0.0 ou superior deve ser instalado.  <br/> |
|Codificação H.264 acelerada por hardware: requisitos de câmera  <br/> |Câmera de vídeo USB com codificador de hardware H.264 integrado em conformidade com a especificação USB Video Class (UVC) versão 1.5.  <br/> **Observação:** Skype para a empresa oferece suporte a câmeras de 1,5 UVC com Windows 8 ou Windows 8.1, que inclui o suporte para UVC 1.5. Porque o Windows 7 não inclui suporte para UVC 1.5, o Skype para negócios trata UVC 1,5 câmeras como câmeras regulares sem codificação suporte de hardware. <br/> |
   
### <a name="determining-h264-video-encoding-and-decoding-capabilities"></a>Determinar a capacidade de codificação e decodificação de vídeo H.264

Geralmente, há quatro fatores principais que determinam a capacidade máxima de codificação e decodificação de determinada configuração de computador:
  
- Suporte para decodificação acelerada por hardware usando DXVA
    
- Suporte para codificação acelerada por hardware
    
- Número de núcleos físicos
    
- Índice de Experiência do Windows (WEI)
    
A Ferramenta de Avaliação de Sistema do Windows (WinSAT) determina o WEI. Quando você executa a ferramenta WinSAT, ela gera um documento XML Formal.Assessment no diretório %windir%\Performance\WinSAT\DataStore do computador. Esse arquivo XML contém as duas pontuações a seguir que são particularmente importantes para determinar as capacidades de codificação e decodificação:
  
- O VideoEncodeScore indica a capacidade de codificação de vídeo baseada em software do computador.
    
- O valor de GraphicsScore indica a capacidade de codificação acelerada por hardware do computador.
    
As três tabelas a seguir explicam a capacidade máxima de codificação e decodificação de diferentes tipos de PC, dependendo da aceleração de hardware que eles suportam. Para resoluções iguais ou maiores que 640x360, a taxa de quadros máxima suportada é de 30 quadros por segundo (fps). Para resoluções menores que 640x360, a taxa de quadros máxima suportada é de 15 fps.
  
**Codificação acelerada por computador sem DXVA e Hardware**

|**Resolução do codificador capaz**|**Resolução do decodificador capaz**|**Requisito**|
|:-----|:-----|:-----|
|424 x 240  <br/> |424x240 (640x360 a 15fps para cenários apenas de recepção)  <br/> |1 Núcleo e VideoEncodeScore ≥ 4,0  <br/> |
|640 x 360  <br/> |640 x 360  <br/> |2 Núcleos e VideoEncodeScore ≥ 4,5  <br/> |
|640 x 360  <br/> |1280 x 720  <br/> |2 Núcleos e VideoEncodeScore ≥ 4,5  <br/> |
|640 x 360  <br/> |1920 x 1080  <br/> |4 Núcleos e VideoEncodeScore ≥ 4,5  <br/> |
|1280 x 720  <br/> |1280 x 720  <br/> |4 Núcleos e VideoEncodeScore ≥ 7.3  <br/> |
|1280 x 720  <br/> |1920 x 1080  <br/> |4 Núcleos e VideoEncodeScore ≥ 7.3  <br/> |
|1920 x 1080  <br/> |1920 x 1080  <br/> |N/D  <br/> |
   
**Codificação acelerada por computador com DXVA, mas sem Hardware**

|**Resolução do codificador capaz**|**Resolução do decodificador capaz**|**Requisito**|
|:-----|:-----|:-----|
|424 x 240  <br/> |1920 x 1080  <br/> |1 Núcleo e VideoEncodeScore ≥ 3,0  <br/> |
|640 x 360  <br/> |1920 x 1080  <br/> |2 Núcleos e VideoEncodeScore ≥ 4,5  <br/> |
|960 x 540  <br/> |1920 x 1080  <br/> |2 Núcleos e VideoEncodeScore ≥ 6,0  <br/> |
|1280 x 720  <br/> |1920 x 1080  <br/> |4 Núcleos e VideoEncodeScore ≥ 6,7  <br/> |
|1920 x 1080  <br/> |1920 x 1080  <br/> |4 Núcleos e VideoEncodeScore ≥ 8,2  <br/> |
   
> [!NOTE]
> A pontuação WinSAT no Windows 7 está limitada ao máximo de 7,9. Dessa forma, a capacidade de codificação de um computador sem um codificador acelerado por hardware pode ser atingida somente no Windows 8 ou no Windows 8.1, onde a pontuação WinSAT máxima é 9,9. 
  
**Codificação acelerada por computador com DXVA e com Hardware Intel HD Graphics**

|**Resolução do codificador capaz**|**Resolução do decodificador capaz**|**Requisito**|
|:-----|:-----|:-----|
|1280 x 720  <br/> |1920 x 1080  <br/> |Toda a segunda e a terceira geração Intel HD Graphics  <br/> |
|1920 x 1080  <br/> |1920 x 1080  <br/> |Segunda e terceira geração Intel HD Graphics e GraphicsScore ≥ 5,0  <br/> |
   
## <a name="mobile-device-video-capabilities"></a>Capacidade de vídeo de dispositivos móveis

A tabela a seguir descreve as resoluções de vídeos máxima disponíveis em dispositivos móveis suportados. Para obter mais informações sobre o suporte a dispositivos móveis, [comparação de recursos do cliente móvel para Skype para negócios](mobile-feature-comparison.md).
  
|**Recurso**|**Windows Phone**|**iPhone**|**iPad**|**Android**|
|:-----|:-----|:-----|:-----|:-----|
|Resolução máxima de codificação H.264  <br/> |VGA  <br/> |QVGA: iPhone 4S  <br/> VGA: iPhone 5  <br/> 720p: iPhone 5S e posterior  <br/> |VGA: iPad 2 e posterior/iPad mini 1 e posterior  <br/> 720P: iPad Air/iPad mini 2/iPad Pro e posterior  <br/> |Até VGA, dependendo do modelo de dispositivo  <br/> |
|Resolução máxima de decodificação H.264  <br/> |VGA  <br/> |QVGA: iPhone 4S  <br/> VGA: iPhone 5  <br/> 720p: iPhone 5S e posterior  <br/> |VGA: iPad 2 e posterior/iPad mini 1 e posterior  <br/> 720P: iPad Air/iPad mini 2/iPad Pro e posterior  <br/> |Até VGA, dependendo do modelo de dispositivo  <br/> |
   

