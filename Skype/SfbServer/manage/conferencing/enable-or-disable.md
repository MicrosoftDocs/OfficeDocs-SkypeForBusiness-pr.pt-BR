---
title: Habilitar ou desabilitar a conferência discada no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1f7cf91-8434-42ec-b09d-7d9d01e0b357
description: 'Resumo: saiba como usar o painel de controle ou o Shell de gerenciamento para habilitar ou desabilitar a conferência discada no Skype for Business Server.'
ms.openlocfilehash: 6723c3501b226d11977ad176a804210540f1a2bc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294254"
---
# <a name="enable-or-disable-dial-in-conferencing-in-skype-for-business-server"></a>Habilitar ou desabilitar a conferência discada no Skype for Business Server
 
**Resumo:** Saiba como usar o painel de controle ou o Shell de gerenciamento para habilitar ou desabilitar a conferência discada no Skype for Business Server.
  
Você pode habilitar a conferência discada usando o painel de controle do Skype for Business Server ou usando o Shell de gerenciamento do Skype for Business Server.
  
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-control-panel"></a>Habilitar ou desabilitar a conferência discada usando o painel de controle do Skype for Business Server

1. Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.
    
2.  Abra o painel de controle do Skype for Business Server.
    
3. Na barra de navegação esquerda, clique em **Conferência** e, então, clique em **Política de Conferência**.
    
4. Na lista de políticas de conferência, selecione a política que deseja ativar na conferência discada, clique em **Editar** e, então, em **Exibir detalhes**. 
    
5. Para permitir que os usuários participem por conexão discada, marque a caixa de verificação **Ativar a conferência via conexão discada PSTN**. Por padrão, os usuários podem discar para reuniões utilizando a Rede Telefônica Pública Comutada (PSTN).
    
6. Clique em **Confirmar**. 
    
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-management-shell"></a>Habilitar ou desabilitar a conferência discada usando o Shell de gerenciamento do Skype for Business Server

Para ativar ou desativar a conferência discada, use o cmdlet **Set-Cs ConferencingPolicy** com o parâmetro EnableDialInConferencing da seguinte maneira:
  
```
Set-CsConferencingPolicy  [-EnableDialInConferencing <$true | $false>] 
```

Para obter mais informações, consulte [set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
  

