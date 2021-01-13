---
title: Criar perfis de política de largura de banda no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a71881ef-b04a-465e-9abb-0577bfd182f3
description: Criar ou modificar políticas de largura de banda, que são usadas pelo controle de admissão de chamadas do Enterprise Voice no Skype for Business Server.
ms.openlocfilehash: ac80ebb8b61a763efc0077f267a024a21a359b5d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824841"
---
# <a name="create-bandwidth-policy-profiles-in-skype-for-business-server"></a>Criar perfis de política de largura de banda no Skype for Business Server 
 
Criar ou modificar políticas de largura de banda, que são usadas pelo controle de admissão de chamadas do Enterprise Voice no Skype for Business Server. 
  
Políticas de largura de banda definem limitações de uso de largura de banda para modalidades de áudio e vídeo em tempo real. As políticas de largura de banda são aplicadas aos perfis de política de largura de banda, que podem ser aplicados a vários sites de rede para controle de admissão de chamada.
  
Para diretrizes sobre quais limites de largura de banda você deve definir em sua implantação do CAC, consulte Planejar o controle de admissão de chamadas [no Skype for Business Server.](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md)
  
As políticas de exemplo criadas no procedimento a seguir definem limites para o tráfego de áudio geral, sessões de áudio individuais, tráfego de vídeo geral e sessões de vídeo individuais. Por exemplo, o perfil de política de largura de banda 5Mb_Link define os seguintes limites: 
  
- Limite de Áudio: 2.000 kbps
    
- Limite de Sessão de Áudio: 200 kbps
    
- Limite de Vídeo: 1.400 kbps
    
- Limite de Sessão de Vídeo: 700 kbps
    
> [!NOTE]
> O valor mínio para o Limite de Sessão de Áudio é 40 kbps. O valor mínimo para o Limite de Sessão de Vídeo é 100 kbps. 
  
### <a name="to-create-bandwidth-policy-profiles-by-using-skype-for-business-server-management-shell"></a>Para criar perfis de política de largura de banda usando o Shell de Gerenciamento do Skype for Business Server

1. Inicie o Shell de Gerenciamento do Skype for Business Server: Clique em **Iniciar,** Em Todos os **Programas,** no **Skype for Business 2015** e, em seguida, clique no Shell de Gerenciamento do **Skype for Business Server.**
    
2. Para cada perfil de política de largura de banda que desejar criar, execute o cmdlet New-CsNetworkBandwidthPolicyProfile. Por exemplo, execute:
    
   ```powershell
   New-CsNetworkBandwidthPolicyProfile -Identity 5Mb_Link -Description "BW profile for 5Mb links" -AudioBWLimit 2000 -AudioBWSessionLimit 200 -VideoBWLimit 1400   -VideoBWSessionLimit 700
   ```

   ```powershell
   New-CsNetworkBandwidthPolicyProfile -Identity 10Mb_Link -Description "BW profile for 10Mb links" -AudioBWLimit 4000 -AudioBWSessionLimit 200 -VideoBWLimit 2800 -VideoBWSessionLimit 700
   ```

   ```powershell
   New-CsNetworkBandwidthPolicyProfile -Identity 50Mb_Link -Description "BW profile for 50Mb links" -AudioBWLimit 20000 -AudioBWSessionLimit 200 -VideoBWLimit 14000 -VideoBWSessionLimit 700
   ```

   ```powershell
   New-CsNetworkBandwidthPolicyProfile -Identity 25Mb_Link -Description "BW profile for 25Mb links" -AudioBWLimit 10000 -AudioBWSessionLimit 200 -VideoBWLimit 7000 -VideoBWSessionLimit 700
   ```

### <a name="to-create-bandwidth-policy-profiles-by-using-skype-for-business-server-control-panel"></a>Para criar perfis de política de largura de banda usando o Painel de Controle do Skype for Business Server

1. Abra o Painel de Controle do Skype for Business Server.
    
2. Na barra de navegação à esquerda, clique em **Configuração da Rede**.
    
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
    
## <a name="see-also"></a>Confira também

[New-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/new-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/get-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[Set-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/set-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[Remove-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkbandwidthpolicyprofile?view=skype-ps)
