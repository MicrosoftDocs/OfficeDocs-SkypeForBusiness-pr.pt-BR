---
title: Resoluções de vídeo do cliente Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 8f68f4c2-3194-487c-bd2f-fbe71ba8ad70
description: 'Resumo: revise os requisitos de vídeo do cliente durante o planejamento para o Skype for Business Server.'
ms.openlocfilehash: 15fd424f7ad2e11d473e49e271c7fbf1db83b45c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277276"
---
# <a name="skype-for-business-client-video-resolutions"></a>Resoluções de vídeo do cliente Skype for Business
 
**Resumo:** Examine os requisitos de vídeo do cliente ao planejar o Skype for Business Server.
  
Este artigo descreve o suporte de hardware de vídeo para chamadas com vídeo do Skype for Business e descreve como determinar a qualidade de vídeo esperada para várias configurações de computador, Tablet e dispositivo móvel. 
  
Os profissionais de ti encontrarão essas informações úteis para avaliar a adequação de laptops que já estão em uso na organização ou em consideração para uso. Eles também podem pesquisar o [Catálogo de soluções](https://partnersolutions.skypeforbusiness.com/solutionscatalog) para obter informações sobre dispositivos específicos.
  
## <a name="windows-desktop-mac-and-tablet-video-requirements-and-capabilities"></a>Recursos e requisitos de vídeo para área de trabalho do Windows, Mac e Tablet

O Skype for Business usa a aceleração de hardware para a codificação e decodificação de vídeo com base no padrão de codificação de vídeo avançado de H. 264/MPEG-4 Part 10. Isso permite que computadores com velocidades de clock de CPU menores sejam codificados e decodificados com vídeo de alta resolução. Os requisitos de hardware de vídeo variam de acordo com a configuração do computador e a resolução de vídeo desejada.
  
Consulte também [requisitos de hardware para Windows e Mac](https://products.office.com/en-us/office-system-requirements).
  
### <a name="video-hardware-requirements"></a>Requisitos de hardware de vídeo

|**Recurso**|**Requisito**|
|:-----|:-----|
|Decodificação H.264 acelerada por hardware usando DirectX Video Acceleration (DXVA)  <br/> |• A placa gráfica deve dar suporte ao DirectX 9,0 e deve expor o modo de decodificação de DXVA2_ModeH264_VLD_NoFGT e a API do DirectX 9.  <br/> • O driver da placa gráfica mais recente deve estar instalado.  <br/> |
|Codificação H.264 acelerada por hardware: requisitos de chipset  <br/> |As seguintes soluções de codificação de vídeo acelerada por hardware da Intel têm suporte:  <br/> • Chipsets Intel HD 2000, 2500, 3000 e 4000 de terceira geração (ou versões posteriores) com codificadores de vídeo de hardware integrados. A instalação do driver Intel HD Graphics 15.28.9.2884 ou driver mais recente contendo os seguintes itens é necessária:  <br/> • Display Driver 9.17.10.2884 ou o driver mais recente  <br/> • Hardware Media Foundation Transform (HMFT) Version 3.12.10.31 ou o HMFT mais recente  <br/> As seguintes soluções de codificação de vídeo acelerada por hardware da AMD têm suporte:  <br/> • Mecanismo de codec de vídeo AMD, que está disponível em vários cartões gráficos discretos e em unidades de processamento aceleradas integradas de processadores AMD de série A. O driver do Mecanismo de Codec de Vídeo AMD 9.12.0.0 ou superior deve ser instalado.  <br/> |
|Codificação H.264 acelerada por hardware: requisitos de câmera  <br/> |Câmera de vídeo USB com codificador de hardware H.264 integrado em conformidade com a especificação USB Video Class (UVC) versão 1.5.  <br/> **Observação:** O Skype for Business dá suporte a câmeras UVC 1,5 com Windows 8 ou Windows 8,1, que inclui suporte para UVC 1,5. Como o Windows 7 não inclui suporte para o UVC 1,5, o Skype for Business trata câmeras UVC 1,5 como câmeras normais sem suporte de codificação de hardware. <br/> |
   
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
  
**Computador sem DXVA e sem codificador acelerado por hardware**

|**Capacidade de resolução do codificador**|**Capacidade de resolução do decodificador**|**Requisito**|
|:-----|:-----|:-----|
|424x240  <br/> |424x240 (640x360 a 15fps para cenários apenas de recepção)  <br/> |1 Núcleo e VideoEncodeScore ≥ 4,0  <br/> |
|640x360  <br/> |640x360  <br/> |2 Núcleos e VideoEncodeScore ≥ 4,5  <br/> |
|640x360  <br/> |1280x720  <br/> |2 Núcleos e VideoEncodeScore ≥ 4,5  <br/> |
|640x360  <br/> |1920x1080  <br/> |4 Núcleos e VideoEncodeScore ≥ 4,5  <br/> |
|1280x720  <br/> |1280x720  <br/> |4 Núcleos e VideoEncodeScore ≥ 7.3  <br/> |
|1280x720  <br/> |1920x1080  <br/> |4 Núcleos e VideoEncodeScore ≥ 7.3  <br/> |
|1920x1080  <br/> |1920x1080  <br/> |N/D  <br/> |
   
**Computador com DXVA, mas sem codificador acelerado por hardware**

|**Capacidade de resolução do codificador**|**Capacidade de resolução do decodificador**|**Requisito**|
|:-----|:-----|:-----|
|424x240  <br/> |1920x1080  <br/> |1 Núcleo e VideoEncodeScore ≥ 3,0  <br/> |
|640x360  <br/> |1920x1080  <br/> |2 Núcleos e VideoEncodeScore ≥ 4,5  <br/> |
|960x540  <br/> |1920x1080  <br/> |2 Núcleos e VideoEncodeScore ≥ 6,0  <br/> |
|1280x720  <br/> |1920x1080  <br/> |4 Núcleos e VideoEncodeScore ≥ 6,7  <br/> |
|1920x1080  <br/> |1920x1080  <br/> |4 Núcleos e VideoEncodeScore ≥ 8,2  <br/> |
   
> [!NOTE]
> A pontuação WinSAT no Windows 7 está limitada ao máximo de 7,9. Dessa forma, a capacidade de codificação de um computador sem um codificador acelerado por hardware pode ser atingida somente no Windows 8 ou no Windows 8.1, onde a pontuação WinSAT máxima é 9,9. 
  
**Computador com DXVA e codificador acelerado por hardware Intel HD Graphics**

|**Capacidade de resolução do codificador**|**Capacidade de resolução do decodificador**|**Requisito**|
|:-----|:-----|:-----|
|1280x720  <br/> |1920x1080  <br/> |Toda a segunda e a terceira geração Intel HD Graphics  <br/> |
|1920x1080  <br/> |1920x1080  <br/> |Segunda e terceira geração Intel HD Graphics e GraphicsScore ≥ 5,0  <br/> |
   
## <a name="mobile-device-video-capabilities"></a>Capacidade de vídeo de dispositivos móveis

A tabela a seguir descreve o máximo de resoluções de vídeo disponíveis em dispositivos móveis compatíveis. Para obter mais informações sobre suporte a dispositivos móveis, [comparação de recursos de cliente móvel para o Skype for Business](mobile-feature-comparison.md).
  
|**Recurso**|**Windows Phone**|**iPhone**|**iPad**|**Android**|
|:-----|:-----|:-----|:-----|:-----|
|Resolução máxima de codificação H.264  <br/> |VGA  <br/> |QVGA: iPhone 4S  <br/> VGA: iPhone 5  <br/> 720p: iPhone 5S e posterior  <br/> |VGA: iPad 2 e posterior/iPad mini 1 e posterior  <br/> 720P: iPad Air/iPad mini 2/iPad Pro e posterior  <br/> |Até VGA, dependendo do modelo do dispositivo  <br/> |
|Resolução máxima de decodificação H.264  <br/> |VGA  <br/> |QVGA: iPhone 4S  <br/> VGA: iPhone 5  <br/> 720p: iPhone 5S e posterior  <br/> |VGA: iPad 2 e posterior/iPad mini 1 e posterior  <br/> 720P: iPad Air/iPad mini 2/iPad Pro e posterior  <br/> |Até VGA, dependendo do modelo do dispositivo  <br/> |
   

