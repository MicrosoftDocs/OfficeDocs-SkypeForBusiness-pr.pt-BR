---
title: Skype for Business de vídeo cliente
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 8f68f4c2-3194-487c-bd2f-fbe71ba8ad70
description: 'Resumo: revise os requisitos de vídeo do cliente durante o planejamento para Skype for Business Server.'
ms.openlocfilehash: 6a483a67b298f2d1ce9a32fbcd7e89882c0598aa
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60745877"
---
# <a name="skype-for-business-client-video-resolutions"></a>Skype for Business de vídeo cliente
 
**Resumo:** Revise os requisitos de vídeo do cliente durante o planejamento de Skype for Business Server.
  
Este artigo descreve o suporte ao hardware de vídeo para Skype for Business chamadas de vídeo e descreve como determinar a qualidade de vídeo esperada para várias configurações de computador, tablet e dispositivo móvel. 
  
Os profissionais de TI acharão essas informações úteis para avaliar a adequação de laptops já em uso em sua organização ou em consideração para uso. Eles também podem pesquisar em Microsoft Teams [para](https://www.microsoft.com/microsoft-teams/across-devices/device) obter informações sobre dispositivos específicos.
  
## <a name="windows-desktop-mac-and-tablet-video-requirements-and-capabilities"></a>Windows de desktop, mac e tablet de vídeo e recursos

Skype for Business usa aceleração de hardware para codificação e decodificação de vídeo com base no padrão H.264/MPEG-4 Part 10 Advanced Video Coding standard. Isso permite que computadores com velocidades de relógio de CPU inferiores codificam e decodificarem vídeo de resolução mais alta. Os requisitos de hardware de vídeo variam dependendo da configuração do computador e da resolução de vídeo procurada.
  
Consulte também [Windows e requisitos de hardware do Mac.](https://products.office.com/office-system-requirements)
  
### <a name="video-hardware-requirements"></a>Requisitos de hardware de vídeo

|**Característica**|**Requisito**|
|:-----|:-----|
|Decodificação H.264 acelerada pelo hardware usando a Aceleração de Vídeo DirectX (DXVA)  <br/> |• A placa gráfica deve dar suporte ao DirectX 9.0 e deve expor o modo DXVA2_ModeH264_VLD_NoFGT decodificação e a API DirectX 9.  <br/> • O driver de placa gráfica mais recente deve ser instalado.  <br/> |
|Codificação H.264 acelerada por hardware: Requisitos de chipset  <br/> |As seguintes soluções de codificação de vídeo aceleradas de hardware intel são suportadas:  <br/> • Chipsets Intel HD Graphics 2000, 2500, 3000 e 4000 de segunda e terceira geração (ou versões posteriores) com codificadores de vídeo de hardware integrados. A instalação do driver intel HD Graphics 15.28.9.2884 ou do driver mais recente que contém o seguinte é necessária:  <br/> • Exibir o driver 9.17.10.2884 ou o driver mais recente  <br/> • Transformação de base de mídia de hardware (HMFT) versão 3.12.10.31 ou o HMFT mais recente  <br/> As seguintes soluções de codificação de vídeo aceleradas de hardware AMD são suportadas:  <br/> • Mecanismo de Codec de Vídeo AMD, que está disponível em várias placas gráficas discretas e em unidades de processamento aceleradas integradas de processadores acelerados da série AMD. O driver do Mecanismo de Codec de Vídeo AMD 9.12.0.0 ou superior deve ser instalado.  <br/> |
|Codificação H.264 acelerada por hardware: Requisitos da câmera  <br/> |Câmeras de vídeo USB com codificador de hardware H.264 integrado que está em conformidade com a especificação da Classe de Vídeo USB (UVC) versão 1.5.  <br/> **Observação: Skype for Business** dá suporte a câmeras UVC 1.5 com Windows 8 ou Windows 8.1, que inclui suporte para UVC 1.5. Como o Windows 7 não inclui suporte para UVC 1.5, o Skype for Business trata as câmeras UVC 1.5 como câmeras regulares sem suporte a codificação de hardware. <br/> |
   
### <a name="determining-h264-video-encoding-and-decoding-capabilities"></a>Determinando recursos de codificação e decodificação de vídeo H.264

Geralmente, há quatro fatores principais que determinam a capacidade máxima de codificação e decodificação de uma configuração específica do computador:
  
- Suporte para decodificação acelerada de hardware usando DXVA
    
- Suporte para codificação acelerada de hardware
    
- Número de núcleos físicos
    
- Windows Índice de Experiência (WEI)
    
A Windows Ferramenta de Avaliação do Sistema (WinSAT) determina o WEI. Quando você executar a ferramenta WinSAT, ela gera um documento XML Formal.Assessment no computador no diretório %windir%\Performance\WinSAT\DataStore. Este arquivo XML contém as duas pontuações a seguir que são de particular importância para determinar recursos de codificação e decodificação:
  
- O VideoEncodeScore indica o recurso de codificação de vídeo baseado em software do computador.
    
- O valor GraphicsScore indica o recurso de codificação acelerada de hardware do computador.
    
As três tabelas a seguir explicam a capacidade máxima de codificação e decodificação para diferentes tipos de computador, dependendo da aceleração de hardware suportada. Para resoluções de 640x360 ou superior, a taxa máxima de quadros com suporte é de 30 quadros por segundo (fps). Para resoluções inferiores a 640 x 360, a taxa máxima de quadros com suporte é de 15 fps.
  
**Computador sem DXVA e sem codificador acelerado por hardware**

|**Resolução de codificador capaz**|**Resolução de decodificador capaz**|**Requisito**|
|:-----|:-----|:-----|
|424x240  <br/> |424x240 (640x360 a 15fps para apenas cenários de recebimento)  <br/> |1 Core e VideoEncodeScore ≥ 4.0  <br/> |
|640x360  <br/> |640x360  <br/> |2 Núcleos e VideoEncodeScore ≥ 4.5  <br/> |
|640x360  <br/> |1280x720  <br/> |2 Núcleos e VideoEncodeScore ≥ 4.5  <br/> |
|640x360  <br/> |1920x1080  <br/> |4 Núcleos e VideoEncodeScore ≥ 4.5  <br/> |
|1280x720  <br/> |1280x720  <br/> |4 Núcleos e VideoEncodeScore ≥ 7.3  <br/> |
|1280x720  <br/> |1920x1080  <br/> |4 Núcleos e VideoEncodeScore ≥ 7.3  <br/> |
|1920x1080  <br/> |1920x1080  <br/> |N/A  <br/> |
   
**Computador com DXVA, mas sem codificador acelerado por hardware**

|**Resolução de codificador capaz**|**Resolução de decodificador capaz**|**Requisito**|
|:-----|:-----|:-----|
|424x240  <br/> |1920x1080  <br/> |1 Core e VideoEncodeScore ≥ 3.0  <br/> |
|640x360  <br/> |1920x1080  <br/> |2 Núcleos e VideoEncodeScore ≥ 4.5  <br/> |
|960x540  <br/> |1920x1080  <br/> |2 Núcleos e VideoEncodeScore ≥ 6.0  <br/> |
|1280x720  <br/> |1920x1080  <br/> |4 Núcleos e VideoEncodeScore ≥ 6.7  <br/> |
|1920x1080  <br/> |1920x1080  <br/> |4 Núcleos e VideoEncodeScore ≥ 8.2  <br/> |
   
> [!NOTE]
> A pontuação winSAT no Windows 7 está limitada ao máximo de 7,9. Portanto, a funcionalidade de codificação para um computador sem um codificador acelerado de hardware só pode ser atingida no Windows 8 ou Windows 8.1, onde a pontuação máxima do WinSAT é 9,9. 
  
**Computador com DXVA e com codificador acelerado de hardware gráfico Intel HD**

|**Resolução de codificador capaz**|**Resolução de decodificador capaz**|**Requisito**|
|:-----|:-----|:-----|
|1280x720  <br/> |1920x1080  <br/> |Todos os gráficos Intel HD de 2ª e 3ª geração  <br/> |
|1920x1080  <br/> |1920x1080  <br/> |2nd e 3ª geração Intel HD Graphics and GraphicsScore ≥ 5.0  <br/> |
   
## <a name="mobile-device-video-capabilities"></a>Recursos de vídeo de dispositivo móvel

A tabela a seguir descreve as resoluções de vídeo máximas disponíveis em dispositivos móveis com suporte. Para obter mais informações sobre o suporte a dispositivos móveis, comparação de recursos do cliente [móvel para Skype for Business](mobile-feature-comparison.md).
  
|**Característica**|**Windows Phone**|**iPhone**|**iPad**|**Android**|
|:-----|:-----|:-----|:-----|:-----|
|Resolução máxima de codificação H.264  <br/> |VGA  <br/> |QVGA: iPhone 4S  <br/> VGA: iPhone 5  <br/> 720p: iPhone 5S e posteriores  <br/> |VGA: iPad 2 e posterior/iPad mini 1 e posterior  <br/> 720p: iPad Air/iPad mini 2/iPad Pro e posterior  <br/> |Até VGA, dependendo do modelo de dispositivo  <br/> |
|Resolução máxima de decodificação de H.264  <br/> |VGA  <br/> |QVGA: iPhone 4S  <br/> VGA: iPhone 5  <br/> 720p: iPhone 5S e posteriores  <br/> |VGA: iPad 2 e posterior/iPad mini 1 e posterior  <br/> 720p: iPad Air/iPad mini 2/iPad Pro e posterior  <br/> |Até VGA, dependendo do modelo de dispositivo  <br/> |
   

