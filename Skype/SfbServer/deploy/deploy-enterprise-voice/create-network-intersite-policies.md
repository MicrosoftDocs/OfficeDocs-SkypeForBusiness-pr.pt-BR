---
title: Criar políticas de intersite de rede no Skype for Business Server
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
ms.assetid: b0714aae-55dc-4587-b718-34a03f596b22
description: Crie políticas entre sites de rede, que são usadas Enterprise Voice controle de admissão de chamadas no Skype for Business Server.
ms.openlocfilehash: 7c0ca45c691ab1ef70d3660c3d49a08c40bdd40d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093079"
---
# <a name="create-network-intersite-policies-in-skype-for-business-server"></a>Criar políticas de intersite de rede no Skype for Business Server
 
Crie políticas entre sites de rede, que são usadas Enterprise Voice controle de admissão de chamadas no Skype for Business Server. 
  
Uma política entre sites de rede define limitações de largura de banda entre sites que têm links wan diretos entre eles.
  
> [!IMPORTANT]
> Uma política entre sites de rede é necessária  *somente*  se houver um link cruzado direto entre dois sites de rede.
  
Na região América do Norte da topologia de exemplo, existe um link direto entre os sites Reno e Albuquerque. Esses dois sites exigem uma política entre sites que aplique um perfil de política de largura de banda apropriado. O exemplo a seguir aplica o perfil 20Mb_Link.
  
### <a name="to-create-a-network-inter-site-policy"></a>Para criar uma política entre sites de rede

1. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar,** em Todos os **Programas,** em **Skype for Business 2015** e em Shell de Gerenciamento do **Skype for Business Server.**
    
2. Execute o cmdlet New-CsNetworkInterSitePolicy para criar políticas entre sites de rede e aplicar um perfil de política de largura de banda apropriado para dois sites que tenham um link cruzado direto. Por exemplo, execute:
    
   ```powershell
   New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link
   ```

3. Repita a etapa 2 conforme necessário para criar políticas entre sites de rede para todos os pares de sites de rede que tenham um link cruzado direto.
    
## <a name="see-also"></a>Confira também

[New-CsNetworkInterSitePolicy](/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps)
  
[Get-CsNetworkInterSitePolicy](/powershell/module/skype/get-csnetworkintersitepolicy?view=skype-ps)
  
[Set-CsNetworkInterSitePolicy](/powershell/module/skype/set-csnetworkintersitepolicy?view=skype-ps)
  
[Remove-CsNetworkInterSitePolicy](/powershell/module/skype/remove-csnetworkintersitepolicy?view=skype-ps)