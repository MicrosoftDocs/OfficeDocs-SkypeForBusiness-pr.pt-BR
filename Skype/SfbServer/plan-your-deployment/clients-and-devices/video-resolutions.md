---
title: Resoluções de vídeo do cliente Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 'Resumo: revise os requisitos de vídeo do cliente durante o planejamento do Skype for Business Server.'
ms.openlocfilehash: 9be23512462781c55ef94b72b4dbbba60e15e5ba
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816051"
---
# <a name="skype-for-business-client-video-resolutions"></a>Resoluções de vídeo do cliente Skype for Business
 
**Resumo:** Revise os requisitos de vídeo do cliente ao planejar o Skype for Business Server.
  
Este artigo descreve o suporte de hardware de vídeo para chamadas de vídeo do Skype for Business e descreve como determinar a qualidade de vídeo esperada para várias configurações de computador, tablet e dispositivo móvel. 
  
Os profissionais de TI considerarão essas informações úteis para avaliar a adequação de laptops que já estão em uso em sua organização ou em consideração para uso. Eles também podem pesquisar no [Catálogo de Soluções](https://partnersolutions.skypeforbusiness.com/solutionscatalog) informações sobre dispositivos específicos.
  
## <a name="windows-desktop-mac-and-tablet-video-requirements-and-capabilities"></a>Recursos e requisitos de vídeo para área de trabalho do Windows, Mac e tablet

O Skype for Business usa aceleração de hardware para codificação e decodificação de vídeo com base no padrão H.264/MPEG-4 Part 10 Advanced Video Coding. Isso permite que computadores com velocidades de clock de CPU inferiores codifiquem e decodifiquem vídeo com maior resolução. Os requisitos de hardware de vídeo variam dependendo da configuração do computador e da resolução de vídeo que se quer.
  
Consulte também os [requisitos de hardware do Windows e do Mac.](https://products.office.com/office-system-requirements)
  
### <a name="video-hardware-requirements"></a>Requisitos de hardware de vídeo

|**Característica**|**Requisito**|
|:-----|:-----|
|Decodificação H.264 acelerada por hardware usando DirectX Video Acceleration (DXVA)  <br/> |• A placa gráfica deve dar suporte ao DirectX 9.0 e deve expor o modo de decodificação de DXVA2_ModeH264_VLD_NoFGT e a API do DirectX 9.  <br/> • O driver mais recente da placa gráfica deve estar instalado.  <br/> |
|Codificação H.264 acelerada por hardware: Requisitos de chipset  <br/> |Há suporte para as seguintes soluções de codificação de vídeo acelerada por hardware da Intel:  <br/> • Chipsets de segunda e terceira geração Intel HD Graphics 2000, 2500, 3000 e 4000 (ou versões posteriores) com codificadores de vídeo de hardware integrados. A instalação do driver Intel HD Graphics 15.28.9.2884 ou do driver mais recente contendo o seguinte é necessária:  <br/> • Driver de vídeo 9.17.10.2884 ou o driver mais recente  <br/> • HMFT (Hardware Media Foundation Transform) versão 3.12.10.31 ou HMFT mais recente  <br/> As seguintes soluções de codificação de vídeo acelerada por hardware da AMD são suportadas:  <br/> • Mecanismo de Codec de Vídeo AMD, que está disponível em várias placas gráficas discretas e em unidades de processamento aceleradas integradas de processadores acelerados AMD A-Series. O driver 9.12.0.0.0 ou superior do mecanismo de codec de vídeo AMD deve estar instalado.  <br/> |
|Codificação H.264 acelerada por hardware: Requisitos de câmera  <br/> |Câmeras de vídeo USB com codificador de hardware H.264 integrado que está em conformidade com a especificação USB Video Class (UVC) versão 1.5.  <br/> **Observação:** O Skype for Business dá suporte a câmeras UVC 1.5 com Windows 8 ou Windows 8.1, que inclui suporte para UVC 1.5. Como o Windows 7 não inclui suporte para UVC 1.5, o Skype for Business trata as câmeras UVC 1.5 como câmeras regulares sem suporte à codificação de hardware. <br/> |
   
### <a name="determining-h264-video-encoding-and-decoding-capabilities"></a>Determinando recursos de codificação e decodificação de vídeo H.264

Geralmente, há quatro fatores principais que determinam a capacidade máxima de codificação e decodificação de uma determinada configuração de computador:
  
- Suporte para decodificação acelerada por hardware usando DXVA
    
- Suporte para codificação acelerada por hardware
    
- Número de núcleos físicos
    
- Índice de Experiência do Windows (WEI)
    
A Ferramenta de Avaliação de Sistema do Windows (WinSAT) determina o WEI. Quando você executar a ferramenta WinSAT, ela gera um documento XML Formal.Assessment no computador no diretório %windir%\Performance\WinSAT\DataStore. Esse arquivo XML contém as duas pontuações a seguir que são particularmente importantes para determinar os recursos de codificação e decodificação:
  
- O VideoEncodeScore indica a capacidade de codificação de vídeo baseada em software do computador.
    
- O valor GraphicsScore indica a capacidade de codificação acelerada de hardware do computador.
    
As três tabelas a seguir explicam a capacidade máxima de codificação e decodificação para diferentes tipos de computador, dependendo da aceleração de hardware que eles suportam. Para resoluções de 640 x 360 e superiores, a taxa de quadros máxima suportada é de 30 quadros por segundo (fps). Para resoluções menores que 640 x 360, a taxa de quadros máxima suportada é de 15 fps.
  
**Computador sem DXVA e sem codificador acelerado por hardware**

|**Resolução do codificador de capacidade**|**Resolução de decodificador com capacidade**|**Requisito**|
|:-----|:-----|:-----|
|424x240  <br/> |424x240 (640x360 a 15fps para cenários somente de recebimento)  <br/> |1 Core e VideoEncodeScore ≥ 4.0  <br/> |
|640x360  <br/> |640x360  <br/> |2 Núcleos e VideoEncodeScore ≥ 4.5  <br/> |
|640x360  <br/> |1280x720  <br/> |2 Núcleos e VideoEncodeScore ≥ 4.5  <br/> |
|640x360  <br/> |1920x1080  <br/> |4 Núcleos e VideoEncodeScore ≥ 4.5  <br/> |
|1280x720  <br/> |1280x720  <br/> |4 Núcleos e VideoEncodeScore ≥ 7.3  <br/> |
|1280x720  <br/> |1920x1080  <br/> |4 Núcleos e VideoEncodeScore ≥ 7.3  <br/> |
|1920x1080  <br/> |1920x1080  <br/> |N/D  <br/> |
   
**Computador com DXVA, mas sem codificador acelerado por hardware**

|**Resolução do codificador de capacidade**|**Resolução de decodificador com capacidade**|**Requisito**|
|:-----|:-----|:-----|
|424x240  <br/> |1920x1080  <br/> |1 Core e VideoEncodeScore ≥ 3.0  <br/> |
|640x360  <br/> |1920x1080  <br/> |2 Núcleos e VideoEncodeScore ≥ 4.5  <br/> |
|960x540  <br/> |1920x1080  <br/> |2 Núcleos e VideoEncodeScore ≥ 6.0  <br/> |
|1280x720  <br/> |1920x1080  <br/> |4 Núcleos e VideoEncodeScore ≥ 6.7  <br/> |
|1920x1080  <br/> |1920x1080  <br/> |4 Núcleos e VideoEncodeScore ≥ 8.2  <br/> |
   
> [!NOTE]
> A pontuação WinSAT no Windows 7 está limitada a um máximo de 7,9. Portanto, a funcionalidade de codificação para um computador sem um codificador acelerado por hardware só pode ser atingida no Windows 8 ou no Windows 8.1, onde a pontuação máxima do WinSAT é 9,9. 
  
**Computador com DXVA e codificador acelerado por hardware intel HD Graphics**

|**Resolução do codificador de capacidade**|**Resolução de decodificador com capacidade**|**Requisito**|
|:-----|:-----|:-----|
|1280x720  <br/> |1920x1080  <br/> |Todos os gráficos Intel HD de 2 e 3ª geração  <br/> |
|1920x1080  <br/> |1920x1080  <br/> |Gráficos Intel HD e GraphicsScore de 2ª e 3ª geração ≥ 5.0  <br/> |
   
## <a name="mobile-device-video-capabilities"></a>Recursos de vídeo de dispositivo móvel

A tabela a seguir descreve o máximo de resoluções de vídeo disponíveis em dispositivos móveis compatíveis. Para obter mais informações sobre suporte a dispositivos móveis, comparação de recursos do cliente [móvel para o Skype for Business.](mobile-feature-comparison.md)
  
|**Característica**|**Windows Phone**|**iPhone**|**iPad**|**Android**|
|:-----|:-----|:-----|:-----|:-----|
|Resolução máxima de codificação H.264  <br/> |VGA  <br/> |QVGA: iPhone 4S  <br/> VGA: iPhone 5  <br/> 720p: iPhone 5S e posterior  <br/> |VGA: iPad 2 e posterior/iPad mini 1 e posterior  <br/> 720p: iPad Air/iPad mini 2/iPad Pro e posterior  <br/> |Até VGA, dependendo do modelo de dispositivo  <br/> |
|Resolução máxima de decodificação H.264  <br/> |VGA  <br/> |QVGA: iPhone 4S  <br/> VGA: iPhone 5  <br/> 720p: iPhone 5S e posterior  <br/> |VGA: iPad 2 e posterior/iPad mini 1 e posterior  <br/> 720p: iPad Air/iPad mini 2/iPad Pro e posterior  <br/> |Até VGA, dependendo do modelo de dispositivo  <br/> |
   

