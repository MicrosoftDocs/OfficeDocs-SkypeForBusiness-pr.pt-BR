---
title: Criar políticas entre sites da rede no Skype for Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b0714aae-55dc-4587-b718-34a03f596b22
description: Crie políticas entre sites, que são usadas pelo controle de admissão de chamada do Enterprise Voice no Skype para Business Server de rede.
ms.openlocfilehash: 6dc1469950bfac46110953c0e354cd50f4f89688
ms.sourcegitcommit: b14cfca231b618ec28cf9f4efe11cb3e8aceb34b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2018
ms.locfileid: "19500716"
---
# <a name="create-network-intersite-policies-in-skype-for-business-server-2015"></a>Criar políticas entre sites da rede no Skype for Business Server 2015
 
Crie políticas entre sites, que são usadas pelo controle de admissão de chamada do Enterprise Voice no Skype para Business Server de rede. 
  
Uma política entre sites de rede define limitações de largura de banda entre sites com links de WAN diretos entre eles.
  
> [!IMPORTANT]
> Uma política entre sites de rede é necessária *somente* se houver um link cruzado direto entre dois sites de rede.
  
Na região América do Norte da topologia de exemplo, existe um link direto entre os sites Reno e Albuquerque. Esses dois sites exigem uma política entre sites que aplique um perfil de política de largura de banda adequado. O exemplo a seguir aplica o perfil 20Mb_Link.
  
### <a name="to-create-a-network-inter-site-policy"></a>Para criar uma política entre sites da rede

1. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.
    
2. Execute o cmdlet New-CsNetworkInterSitePolicy para criar política entre sites de rede e aplicar um perfil de política de largura de banda apropriado para dois sites que possuem um link cruzado direto. Por exemplo, execute:
    
   ```
   New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link
   ```

3. Repita a etapa 2 conforme o necessário para criar políticas entre sites de rede para todos os pares de sites da rede que possuírem um link cruzado direto.
    
## <a name="see-also"></a>Consulte também

[New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps)
  
[Get-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/get-csnetworkintersitepolicy?view=skype-ps)
  
[Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/set-csnetworkintersitepolicy?view=skype-ps)
  
[Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkintersitepolicy?view=skype-ps)