---
title: Habilitar ou desabilitar conferência discada no Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1f7cf91-8434-42ec-b09d-7d9d01e0b357
description: 'Resumo: Saiba como usar o painel de controle ou o Shell de gerenciamento para habilitar ou desabilitar conferência discada no Skype para Business Server.'
ms.openlocfilehash: 1392c67e2b432a6acc9bca805367083d311fd7d1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33919798"
---
# <a name="enable-or-disable-dial-in-conferencing-in-skype-for-business-server"></a>Habilitar ou desabilitar conferência discada no Skype para Business Server
 
**Resumo:** Saiba como usar o painel de controle ou o Shell de gerenciamento para habilitar ou desabilitar conferência discada no Skype para Business Server.
  
Você pode habilitar a conferência discada usando Skype para o painel de controle do Business Server ou usando o Skype do Shell de gerenciamento do servidor de negócios.
  
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-control-panel"></a>Habilitar ou desabilitar conferência discada usando Skype para o painel de controle do servidor de negócios

1. Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.
    
2.  Abra o Skype para painel de controle do servidor de negócios.
    
3. Na barra de navegação esquerda, clique em **Conferência** e, então, clique em **Política de Conferência**.
    
4. Na lista de políticas de conferência, selecione a política que deseja ativar na conferência discada, clique em **Editar** e, então, em **Exibir detalhes**. 
    
5. Para permitir que os usuários participem por conexão discada, marque a caixa de verificação **Ativar a conferência via conexão discada PSTN**. Por padrão, os usuários podem discar para reuniões utilizando a Rede Telefônica Pública Comutada (PSTN).
    
6. Clique em **Confirmar**. 
    
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-management-shell"></a>Habilitar ou desabilitar conferência discada usando Skype do Shell de gerenciamento do servidor de negócios

Para ativar ou desativar a conferência discada, use o cmdlet **Set-Cs ConferencingPolicy** com o parâmetro EnableDialInConferencing da seguinte maneira:
  
```
Set-CsConferencingPolicy  [-EnableDialInConferencing <$true | $false>] 
```

Para obter mais informações, consulte [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
  

