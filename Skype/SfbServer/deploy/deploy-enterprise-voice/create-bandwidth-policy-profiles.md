---
title: Criar largura de banda perfis de política no Skype para Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a71881ef-b04a-465e-9abb-0577bfd182f3
description: Criar ou modificar políticas de largura de banda, que são usadas pelo controle de admissão de chamada do Enterprise Voice no Skype para Business Server.
ms.openlocfilehash: 26f0e81d4f148888b9c8f61b774dcd476bd102d5
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30887782"
---
# <a name="create-bandwidth-policy-profiles-in-skype-for-business-server"></a>Criar largura de banda perfis de política no Skype para Business Server 
 
Criar ou modificar políticas de largura de banda, que são usadas pelo controle de admissão de chamada do Enterprise Voice no Skype para Business Server. 
  
Políticas de largura de banda definem limitações de uso de largura de banda para modalidades de áudio e vídeo em tempo real. Políticas de largura de banda são aplicados tobandwidth perfis de política, que podem ser aplicados a vários sites de rede para controle de admissão de chamada.
  
Para diretrizes sobre os limites de largura de banda que você deve definido em sua implantação do CAC, consulte [Planejar o controle de admissão de chamada no Skype para Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).
  
As políticas de exemplo criadas no procedimento a seguir definem limites para o tráfego de áudio geral, sessões de áudio individuais, tráfego de vídeo geral e sessões de vídeo individuais. Por exemplo, o perfil de política de largura de banda 5Mb_Link define os seguintes limites: 
  
- Limite de Áudio: 2.000 kbps
    
- Limite de Sessão de Áudio: 200 kbps
    
- Limite de Vídeo: 1.400 kbps
    
- Limite de Sessão de Vídeo: 700 kbps
    
> [!NOTE]
> O valor mínio para o Limite de Sessão de Áudio é 40 kbps. O valor mínimo para o Limite de Sessão de Vídeo é 100 kbps. 
  
### <a name="to-create-bandwidth-policy-profiles-by-using-skype-for-business-server-management-shell"></a>Para criar perfis de política de largura de banda usando Skype do Shell de gerenciamento do servidor de negócios

1. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.
    
2. Para cada perfil de política de largura de banda que desejar criar, execute o cmdlet New-CsNetworkBandwidthPolicyProfile. Por exemplo, execute:
    
   ```
   New-CsNetworkBandwidthPolicyProfile -Identity 5Mb_Link -Description "BW profile for 5Mb links" -AudioBWLimit 2000 -AudioBWSessionLimit 200 -VideoBWLimit 1400   -VideoBWSessionLimit 700
   ```

   ```
   New-CsNetworkBandwidthPolicyProfile -Identity 10Mb_Link -Description "BW profile for 10Mb links" -AudioBWLimit 4000 -AudioBWSessionLimit 200 -VideoBWLimit 2800 -VideoBWSessionLimit 700
   ```

   ```
   New-CsNetworkBandwidthPolicyProfile -Identity 50Mb_Link -Description "BW profile for 50Mb links" -AudioBWLimit 20000 -AudioBWSessionLimit 200 -VideoBWLimit 14000 -VideoBWSessionLimit 700
   ```

   ```
   New-CsNetworkBandwidthPolicyProfile -Identity 25Mb_Link -Description "BW profile for 25Mb links" -AudioBWLimit 10000 -AudioBWSessionLimit 200 -VideoBWLimit 7000 -VideoBWSessionLimit 700
   ```

### <a name="to-create-bandwidth-policy-profiles-by-using-skype-for-business-server-control-panel"></a>Para criar perfis de política de largura de banda usando Skype para o painel de controle do Business Server

1. Abra o Skype para painel de controle do servidor de negócios.
    
2. Na barra de navegação esquerda, clique em **Configuração de rede**.
    
3. Clique no botão de navegação **Perfil da Política**.
    
4. Clique em **Novo**.
    
5. Na página **Novo Perfil de Política**, clique em **Nome** e digite um nome para o perfil de política de largura de banda.
    
6. Clique em **Limite de áudio** e digite o número máximo de kbps a ser permitido para todas as sessões de áudio combinadas.
    
7. Clique em **Limite de sessão de áudio** e digite o número máximo de kbps a ser permitido para cada sessão de áudio individual.
    
8. Clique em **Limite de vídeo** e digite o número máximo de kbps a ser permitido para todas as sessões de vídeo combinadas.
    
9. Clique em **Limite de sessão de vídeo** e digite o número máximo de kbps a ser permitido para cada sessão de vídeo individual.
    
10. Opcionalmente, clique em **Descrição** e digite informações adicionais para descrever este perfil de política de largura de banda.
    
11. Clique em **Confirmar**.
    
12. Para concluir a criação de perfis de política de largura de banda para a sua topologia, repita as etapas de 4 a 11 com as configurações para outros perfis de política de largura de banda.
    
## <a name="see-also"></a>Consulte Também

[New-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/new-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/get-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[Set-CsNetworkBandwidthPolicyProfile.](https://docs.microsoft.com/powershell/module/skype/set-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[Remove-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkbandwidthpolicyprofile?view=skype-ps)
