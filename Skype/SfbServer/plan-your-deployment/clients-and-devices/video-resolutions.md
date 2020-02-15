---
title: Resoluções de vídeo de cliente do Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 8f68f4c2-3194-487c-bd2f-fbe71ba8ad70
description: 'Resumo: revise os requisitos de vídeo do cliente ao planejar o Skype for Business Server.'
ms.openlocfilehash: 126c19d817a2cd656b7d581e0d467db80e4969e5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42027972"
---
# <a name="skype-for-business-client-video-resolutions"></a>Resoluções de vídeo de cliente do Skype for Business
 
**Resumo:** Examine os requisitos de vídeo do cliente ao planejar o Skype for Business Server.
  
Este artigo descreve o suporte de hardware de vídeo para chamadas de vídeo do Skype for Business e descreve como determinar a qualidade de vídeo esperada para várias configurações de computador, Tablet e dispositivo móvel. 
  
Os profissionais de ti encontrarão essas informações úteis na avaliação da adequação de laptops já em uso na organização ou em consideração para uso. Eles também podem pesquisar no [Catálogo de soluções](https://partnersolutions.skypeforbusiness.com/solutionscatalog) informações sobre dispositivos específicos.
  
## <a name="windows-desktop-mac-and-tablet-video-requirements-and-capabilities"></a>Recursos e requisitos de vídeo e de área de trabalho do Windows, Mac e Tablet

O Skype for Business usa aceleração de hardware para codificação e decodificação de vídeo com base no padrão de codificação de vídeo avançado H. 264/MPEG-4 parte 10. Isso permite que computadores com velocidades de relógio de CPU mais baixas codifiquem e decodifiquem um vídeo de resolução mais alta. Os requisitos de hardware de vídeo variam dependendo da configuração do computador e da resolução de vídeo desejada.
  
Consulte também [requisitos de hardware do Windows e Mac](https://products.office.com/office-system-requirements).
  
### <a name="video-hardware-requirements"></a>Requisitos de hardware de vídeo

|**Recurso**|**Requisito**|
|:-----|:-----|
|Decodificação H. 264 acelerada por hardware usando o DirectX Video Acceleration (DXVA)  <br/> |• A placa gráfica deve suportar o DirectX 9,0 e deve expor o modo de decodificação DXVA2_ModeH264_VLD_NoFGT e a API DirectX 9.  <br/> • O driver mais recente da placa gráfica deve estar instalado.  <br/> |
|Codificação H. 264 acelerada por hardware: requisitos de chipset  <br/> |As seguintes soluções de codificação de vídeo aceleradas por hardware Intel têm suporte:  <br/> • Chipsets de segunda e terceira geração Intel HD Graphics 2000, 2500, 3000 e 4000 (ou versões posteriores) com codificadores de vídeo de hardware integrados. É necessário instalar o driver Intel HD Graphics 15.28.9.2884 ou o driver mais recente que contém o seguinte:  <br/> • Exibir o driver de 9.17.10.2884 ou o driver mais recente  <br/> • Hardware Media Foundation Transform (HMFT) versão 3.12.10.31 ou o HMFT mais recente  <br/> As seguintes soluções de codificação de vídeo aceleradas para hardware AMD são compatíveis:  <br/> • Mecanismo de codec de vídeo AMD, disponível em várias placas gráficas distintas e em unidades de processamento aceleradas integradas de processadores AMD A-Series Accelerated. O driver do mecanismo do codec de vídeo AMD 9.12.0.0 ou superior deve estar instalado.  <br/> |
|Codificação H. 264 acelerada por hardware: requisitos de câmera  <br/> |Câmeras de vídeo USB com o codificador de hardware H. 264 integrado que está em conformidade com a especificação de classe de vídeo USB (UVC) versão 1,5.  <br/> **Observação:** O Skype for Business suporta câmeras UVC 1,5 com Windows 8 ou Windows 8,1, que inclui suporte para o UVC 1,5. Como o Windows 7 não inclui suporte para o UVC 1,5, o Skype for Business trata as câmeras do UVC 1,5 como câmeras normais sem suporte de codificação de hardware. <br/> |
   
### <a name="determining-h264-video-encoding-and-decoding-capabilities"></a>Determinação de recursos de codificação e decodificação de vídeo H. 264

Geralmente, há quatro fatores principais que determinam a capacidade máxima de codificação e decodificação de uma configuração de computador específica:
  
- Suporte para decodificação acelerada por hardware usando DXVA
    
- Suporte para codificação acelerada por hardware
    
- Número de núcleos físicos
    
- Índice de experiência do Windows (WEI)
    
A ferramenta de avaliação de sistema do Windows (WinSAT) determina o WEI. Quando você executa a ferramenta WinSAT, ela gera um documento XML formal de avaliação no computador no diretório%windir%\Performance\WinSAT\DataStore Este arquivo XML contém as duas pontuações a seguir de importância específica para determinar as funcionalidades de codificação e decodificação:
  
- O VideoEncodeScore indica a capacidade de codificação de vídeo baseada em software do computador.
    
- O valor GraphicsScore indica a capacidade de codificação acelerada por hardware do computador.
    
As três tabelas a seguir explicam a capacidade máxima de codificação e decodificação para diferentes tipos de computador, dependendo da aceleração de hardware que eles suportam. Para resoluções do 640x360 e superior, a taxa de quadros máxima com suporte é de 30 quadros por segundo (FPS). Para resoluções inferiores a 640x360, a taxa de quadros máxima compatível é de 15 fps.
  
**Computador sem DXVA e codificador acelerado por hardware**

|**Resolução de codificador compatível**|**Resolução de decodificador compatível**|**Requisito**|
|:-----|:-----|:-----|
|424x240  <br/> |424x240 (640x360 em 15fps para cenários de recebimento apenas)  <br/> |1 núcleo e VideoEncodeScore ≥ 4,0  <br/> |
|640x360  <br/> |640x360  <br/> |2 núcleos e VideoEncodeScore ≥ 4,5  <br/> |
|640x360  <br/> |1280 x 720  <br/> |2 núcleos e VideoEncodeScore ≥ 4,5  <br/> |
|640x360  <br/> |1920 x 1080  <br/> |4 núcleos e VideoEncodeScore ≥ 4,5  <br/> |
|1280 x 720  <br/> |1280 x 720  <br/> |4 núcleos e VideoEncodeScore ≥ 7,3  <br/> |
|1280 x 720  <br/> |1920 x 1080  <br/> |4 núcleos e VideoEncodeScore ≥ 7,3  <br/> |
|1920 x 1080  <br/> |1920 x 1080  <br/> |Não disponível  <br/> |
   
**Computador com DXVA, mas sem codificador acelerado por hardware**

|**Resolução de codificador compatível**|**Resolução de decodificador compatível**|**Requisito**|
|:-----|:-----|:-----|
|424x240  <br/> |1920 x 1080  <br/> |1 núcleo e VideoEncodeScore ≥ 3,0  <br/> |
|640x360  <br/> |1920 x 1080  <br/> |2 núcleos e VideoEncodeScore ≥ 4,5  <br/> |
|960x540  <br/> |1920 x 1080  <br/> |2 núcleos e VideoEncodeScore ≥ 6,0  <br/> |
|1280 x 720  <br/> |1920 x 1080  <br/> |4 núcleos e VideoEncodeScore ≥ 6,7  <br/> |
|1920 x 1080  <br/> |1920 x 1080  <br/> |4 núcleos e VideoEncodeScore ≥ 8,2  <br/> |
   
> [!NOTE]
> A Pontuação do WinSAT no Windows 7 está limitada a um máximo de 7,9. Portanto, o recurso de codificação para um computador sem um codificador acelerado de hardware só pode ser alcançado no Windows 8 ou no Windows 8,1, onde a pontuação de WinSAT máxima é 9,9. 
  
**Computador com DXVA e com codificador acelerado por hardware Intel HD Graphics**

|**Resolução de codificador compatível**|**Resolução de decodificador compatível**|**Requisito**|
|:-----|:-----|:-----|
|1280 x 720  <br/> |1920 x 1080  <br/> |Todos os gráficos Intel HD de segunda e 3ª geração  <br/> |
|1920 x 1080  <br/> |1920 x 1080  <br/> |2ª e 3ª geração Intel HD Graphics e GraphicsScore ≥ 5,0  <br/> |
   
## <a name="mobile-device-video-capabilities"></a>Recursos de vídeo do dispositivo móvel

A tabela a seguir descreve as resoluções de vídeo máximas disponíveis em dispositivos móveis compatíveis. Para obter mais informações sobre suporte a dispositivos móveis, [comparação de recursos do cliente móvel para o Skype for Business](mobile-feature-comparison.md).
  
|**Recurso**|**Windows Phone**|**iPhone**|**iPad**|**Android**|
|:-----|:-----|:-----|:-----|:-----|
|Resolução máxima de codificação H. 264  <br/> |VGA  <br/> |QVGA: iPhone 4S  <br/> VGA: iPhone 5  <br/> 720p: iPhone 5S e posterior  <br/> |VGA: iPad 2 e posterior/iPad mini 1 e posterior  <br/> 720p: iPad Air/iPad mini 2/iPad pro e posterior  <br/> |Até VGA, dependendo do modelo do dispositivo  <br/> |
|Resolução máxima de decodificação H. 264  <br/> |VGA  <br/> |QVGA: iPhone 4S  <br/> VGA: iPhone 5  <br/> 720p: iPhone 5S e posterior  <br/> |VGA: iPad 2 e posterior/iPad mini 1 e posterior  <br/> 720p: iPad Air/iPad mini 2/iPad pro e posterior  <br/> |Até VGA, dependendo do modelo do dispositivo  <br/> |
   

